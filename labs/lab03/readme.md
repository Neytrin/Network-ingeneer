## Практическое задание №3
### Часть 1

1. [Создание сети и настройка основных параметров устройств](https://github.com/Neytrin/Network-ingeneer/blob/b2fd1514d38af7efc84f9c17726639b0b8a388ff/labs/lab03/readme.md#L7)
2. [Настройка и проверка двух серверов DHCPv4 на маршрутизаторе R1.](https://github.com/Neytrin/Network-ingeneer/blob/b2fd1514d38af7efc84f9c17726639b0b8a388ff/labs/lab03/readme.md#L206)
3. [Настройка и проверка ретрансляции DHCPv4 на маршрутизаторе R2.]()

### 1. Создание сети и настройка основных параметров устройств

Разделим сеть 192.168.1.0/24 на подсети согласно требований:
1. Cеть A поддерживает 58 хостов (клиентский VLAN на маршрутизаторе R1)
что соответствует IP адресу подсети 192.168.1.0/26, что соответствует маске подсети 255.255.255.192.
2. Сеть B поддерживает 28 хостов (VLAN управления на маршрутизаторе R1)
  192.168.1.64/27, что соответствует маске подсети 255.255.255.224
3. Сеть C поддерживает 12 хостов (клиентский VLAN на маршрутизаторе R2)
   192.168.1.96/28, что соответствует маске подсети 255.255.255.240

В программе EVE-NG создаем сетевые элементы и соединения согласно с условиями задания 
![Shem-Net-LAB03.PNG](Shem-Net-LAB03.PNG)

Таблица адресации

| Устройство | Интерфейс | IP адрес     | Маска подсети   | Шлюз по умолчанию |
|------------|-----------|--------------|-----------------|-------------------|
| R1         | e0/1      | 10.0.0.1     | 255.255.255.252 | N/A               |
|            | e0/0      | N/A          | N/A             |                   |
|            | e0/0.100  | 192.168.1.1  | 255.255.255.192 |                   |
|            | e0/0.200  | 192.168.1.65 | 255.255.255.224 |                   |
|            | e0/0.1000 | N/A          | N/A             |                   |
| R2         | e0/1      | 10.0.0.2     | 255.255.255.252 | N/A               |
|            | e0/0      | 192.168.1.97 | 255.255.255.240 |                   |
| S1         | VLAN200   | 192.168.1.66 | 255.255.255.224 | 192.168.1.1       |
| S2         | VLAN1     | 192.168.1.98 | 255.255.255.240 | 192.168.1.97      |
| PC-A       | NIC       | DHCP         | DHCP            | DHCP              |
| PC-B       | NIC       | DHCP         | DHCP            | DHCP              |

Таблица VLAN

| VLAN | Name        | Interface Assigned |
|------|-------------|--------------------|
| 1    | N/A         | S2 e0/1            |
| 100  | Clients     | S1 e0/1            |
| 200  | Management  | S1 VLAN200         |
| 999  | Parking Lot | S1 e0/2-3          |
| 1000 | Native      | N/A                |

Производим первичную настройку маршрутизатроров R1 и R2. Ниже приведены команды для настройки R1

````
Router(config)#hostname R1
R1(config)#no ip domain-lookup
R1(config)#service password-encryption
R1(config)#enable secret class
R1(config)#line console 0
R1(config-line)#password 0 cisco
R1(config-line)#logging synchronous
R1(config-line)#login
R1(config-line)#exit
R1(config)#line vty 0 4
R1(config-line)#password 0 cisco
R1(config-line)#logging synchronous
R1(config-line)#login
R1(config-line)#exit
R1(config)#banner motd ' Unauthorized access is prohibited!!! '
R1(config)#clock timezone MSK 3
R1(config)#do copy running-config startup-config
````
Настраиваем маршрутизацию между VLAN на маршрутизаторе R1.
Для чего на интерфейсе e0/0 создаем три подинтерфейсы исходя из данных таблицы адресов.

````
R1(config)#interface e0/0
R1(config-if)#description to_S1
R1(config-if)#no shut
R1(config-if)#exit
R1(config)#interface e0/0.100
R1(config-subif)#encapsulation dot1Q 100
R1(config-subif)#description Clients
R1(config-subif)#ip address 192.168.1.1 255.255.255.192
R1(config-if)#exit
R1(config)#interface e0/0.200
R1(config-subif)#encapsulation dot1Q 200
R1(config-subif)#ip address 192.168.1.65 255.255.255.224
R1(config-subif)#description MANAGEMENT
R1(config-if)#exit
R1(config)#int e0/0.1000
R1(config-subif)#description Native
R1(config-subif)#encapsulation dot1Q 1000 native
````
Производим настройку интерфейса e0/1 на R1
````
R1(config)#int e0/1
R1(config-if)#no shut
R1(config-if)#ip address 10.0.0.1 255.255.255.252
R1(config-if)#description To_R2
````
Настраиваем интерфейс e0/1 на маршрутизаторе R2 с первым IP-адресом подсети C, который был вычислен ранее.
````
R2(config)#interface e0/0
R2(config-if)#no shut
R2(config-if)#ip address 192.168.1.97 255.255.255.240
R2(config-if)#description To_S2
````
Настраиваем интерфейс e0/1 для маршрутизаторов R1 и R2.
````
R1(config)#int e0/1
R1(config-if)#no shut
R1(config-if)#ip address 10.0.0.1 255.255.255.252
R1(config-if)#description To_R2

R2(config)#int e0/1
R2(config-if)#no shut
R2(config-if)#ip address 10.0.0.2 255.255.255.252
R2(config-if)#description To_R1
````
Создаем маршрут по умолчанию на каждом маршрутизаторе, указывающем на IP-адрес e0/1 на другом маршрутизаторе.
````
R1(config)#ip route 0.0.0.0 0.0.0.0 10.0.0.2

R2(config)#ip route 0.0.0.0 0.0.0.0 10.0.0.1
````
Убедимся, что статическая маршрутизация работает, пропинговав адрес e0/1 маршрутизатора R2 от маршрутизатора R1.
![PING R1 to R2.PNG](PING%20R1%20to%20R2.PNG)

Выполним первичные настройки коммутаторов S1 и S2 на примере команд в S1
````
Switch(config)#hostname S1
S1(config)#no ip domain-lookup
S1(config)#enable secret class
S1(config)#line console 0
S1(config-line)#password cisco
S1(config-line)#logging synchronous
S1(config-line)#login
S1(config-line)#exit
S1(config)#line vty 0 4
S1(config-line)#logging synchronous
S1(config-line)#login
S1(config-line)#exit
S1(config)#banner motd ' Unauthorized access is prohibited!!! '
S1(config)#clock timezone MSK 3
S1(config)#do copy running-config startup-config
````
Создаем сети VLAN на S1.
````
S1(config)#vlan 100
S1(config-vlan)#name Clients
S1(config-vlan)#exit
S1(config)#vlan 200
S1(config-vlan)#name MANAGEMENT
S1(config-vlan)#exit
S1(config)#vlan 1000
S1(config-vlan)#name Native
````
Настройка и активация интерфейса управления на S1 (VLAN 200), используя второй IP-адрес из рассчитанной ранее подсети.
````
S1(config)#interface vlan 200
S1(config-if)#ip address 192.168.1.66 255.255.255.192
S1(config-if)#exit
S1(config)#ip default-gateway 192.168.1.65
````
Настраиваем и активируем интерфейс управления на S2 (VLAN 1), используя второй IP-адрес из рассчитанной ранее подсети. Кроме того, установим шлюз по умолчанию на S2.
````
S2(config)#interface vlan 1
S2(config-if)#ip address 192.168.1.98 255.255.255.240
S2(config-if)#exit
S2(config)#ip default-gateway 192.168.1.97
````
Назначаем все неиспользуемые порты на S1 VLAN Parking_Lot, настраиваем для них статический режим доступа и административно деактивируем их.
````
S1(config)#vlan 999
S1(config-vlan)#name Parking_Lot
S1(config-if)#exit
S1(config)#interface range e0/2-3
S1(config-if-range)#switchport mode access
S1(config-if-range)#switchport access vlan 999
S1(config-if-range)#shut
````
На S2 административно деактивируем все неиспользуемые порты.
````
S2(config)#int range e0/2-3
S2(config-if-range)#shut
S2(config-if-range)#shutdown
````
Назначаем используемые порты соответствующей VLAN (указанной в таблице VLAN выше) и настраиваем для них режим статического доступа.
````
S1(config)#int e0/1
S1(config-if)#switchport mode access
S1(config-if)#switchport access vlan 100
S1(config-if)#exit
S1(config)#interface e0/0
S1(config-if)#switchport trunk encapsulation dot1q
S1(config-if)#switchport mode trunk
S1(config-if)#switchport trunk native vlan 1000


S2(config)#int e0/1
S2(config-if)#switchport mode access
````
Поскольку с интерфейса e0/0 R2 кадры ETH отправляются не тэгированными,
то для их приема на e0/0 S2 воспользовались VLAN1 являющимся defult native vlan.

Проверка статуса транкинга
![sh_trunk S1.PNG](sh_trunk%20S1.PNG)
На данный момент, какой IP-адрес был бы у ПК, если бы он был подключен к сети с помощью DHCP?
Поскольку DHCP сервер еще не настроен, то IP адрес будет 0.0.0.0/0 

### 2. Настройка и проверка двух серверов DHCPv4 на маршрутизаторе R1.

Производим последовательную настройку двух серверов DHCPv4 на маршрутизаторе R1
Настройка для подсети А
Исключаем первые пять доступных адресов из пула адресов сети А.
````
ip dhcp excluded-address 192.168.1.1 192.168.1.5
````
Создаем DHCP pool
````
R1(config)#ip dhcp pool NET_A
R1(dhcp-config)#network 192.168.1.0 255.255.255.192
R1(dhcp-config)#domain-name ccna-lab.com.
R1(dhcp-config)#default-router 192.168.1.1
R1(dhcp-config)#lease 2 12 30
````
Исключаем первые пять доступных адресов из пула адресов сети C и настраиваем 
DHCP pool по заданным параметрам
````
R1(config)#ip dhcp excluded-address 192.168.1.97 192.168.1.101
R1(config)#ip dhcp pool R2_Client_LAN
R1(dhcp-config)#domain-name ccna-lab.com.
R1(dhcp-config)#network 192.168.1.96 255.255.255.240
R1(dhcp-config)#default-router 192.168.1.97
R1(dhcp-config)#lease 2 12 30
R1(dhcp-config)#exit
R1(config)#do write
````
Проверяем настройку сервера DHCPv4.
````
R1#sh ip dhcp pool
````
![Sh_DHCP_1.PNG](Sh_DHCP_1.PNG)
````
R1#show ip dhcp binding
````
![Sh_DHCP_2.PNG](Sh_DHCP_2.PNG)
````
show ip dhcp server statistics
````
![Sh_DHCP_3.PNG](Sh_DHCP_3.PNG)
В момент проверки настроек PC-A произошел програмный сбой, до сбоя ему был назначен
IP address 192.168.1.6
После пересоздания VPC наблюдаем
![PC-A_1.PNG](PC-A_1.PNG)
Очевидно, что настройки от сервера DHCP еще не получены, поэтому делаем запрос и проверяем их получение
![PC-A_2.PNG](PC-A_2.PNG)
Осуществляем проверку подключения к сети командой Ping шлюза по умолчанию (IP адрес e0/1 R1)
![PC-A_3.PNG](PC-A_3.PNG)

### 3. Настройка и проверка ретрансляции DHCPv4 на маршрутизаторе R2.

Для ретрансляции широковещательных запросов в сторону сервера DHCP на интерфейсе e0/0 R2 задаем команду
ip helper-address с указанием адреса порта e0/1 R1.
````
R2(config)#interface e0/0
R2(config-if)#ip helper-address 192.168.1.1
````
![PC-B_1.PNG](PC-B_1.PNG)

Сетевые настройки получены.

Проверка подключения ping 192.168.1.1 адреса интерфейса e0/0 R1
![PC-B_2.PNG](PC-B_2.PNG)

Командой _show ip dhcp binding_
выводим список всех привязок адресов IPv4 к MAC-адресам,
предоставленных службой DHCPv4 на R1.

![Sh_DHCP_R1_1.PNG](Sh_DHCP_R1_1.PNG)

Командой _show ip dhcp server statistics_ проверяем, что сообщения DHCPv4
принимаются или
отправляются маршрутизатором

![Sh_DHCP_R1_2.PNG](Sh_DHCP_R1_2.PNG)

![Sh_DHCP_R2_1.PNG](Sh_DHCP_R2_1.PNG)

### Часть 2

1. [Создание сети и настройка основных параметров устройства
]()
2. [Проверка назначения адреса SLAAC от маршрутизатора R1.]()
3. [Настройка и проверка сервера DHCPv6 без отслеживания состояния на маршрутизаторе R1.]()
4. [Настройка и проверка сервера DHCPv6 с отслеживанием состояния на маршрутизаторе R1.]()
5. [Настройка и проверка ретраснсляции DHCPv6 на маршрутизаторе R2]()


### 1. Создание сети и настройка основных параметров устройства
 Продолжим использовать уже имеющуюся схему сети c выполненными настройками оборудования.

 ![Shem-Net-LAB03.PNG](Shem-Net-LAB03.PNG)

Таблица адресов

| Устройство | Интерфейс | IPv6 адрес             |
|------------|-----------|------------------------|
| R1         | e0/1      | 2001:db8:acad:2::1 /64 |
|            |           | fe80::1                |
|            | e0/0.100  | 2001:db8:acad:1::1/64  |
|            |           | fe80::1                |
| R2         | e0/1      | 2001:db8:acad:2::2/64  |
|            |           | fe80::2                |
|            | e0/0      | 2001:db8:acad:3::1 /64 |
|            |           | fe80::1                |
| PC-A       | NIC       | DHCP                   |
| PC-B       | NIC       | DHCP                   |

Выполним настройку интерфейсов e0/1.100 и e0/1 маршрутизатора R1
````
R1(config)#ipv6 unicast-routing
R1(config)#interface Ethernet0/0.100
R1(config-if)#ipv6 address FE80::1 link-local
R1(config-if)#ipv6 address 2001:DB8:ACAD:1::1/64
R1(config-if)#exit
R1(config)#interface Ethernet0/1
R1(config-if)#ipv6 address FE80::1 link-local
R1(config-if)#ipv6 address 2001:db8:acad:2::1/64
````
Назначим IPv6 адреса интерфейсам e0/0 и у0.1 R2 
````
R2(config)#ipv6 unicast-routing
R2(config)#interface Ethernet0/0
R2(config-if)#ipv6 address FE80::1 link-local
R2(config-if)#ipv6 address 2001:db8:acad:3::1/64
R2(config-if)#interface Ethernet0/1
R2(config-if)#ipv6 address FE80::2 link-local
R2(config-if)#ipv6 address 2001:db8:acad:2::2/64
````
Настроим на маршрутизаторах R1 и R2 маршруты по умолчанию
````
R1(config)#ipv6 route ::/0 2001:db8:acad:2::2
R2(config)#ipv6 route ::/0 2001:db8:acad:2::1
````
Проверим доступность порта e0/1 R2 от маршрутизатора R1
![IPv6 ping R2.PNG](IPv6%20ping%20R2.PNG)

Cохраняем текущие конфигурации


### 2. Проверка назначения адреса SLAAC от маршрутизатора R1

Проверяем назначил ли хост PC-A себе адрес SLAAC
![IPv6 conf PC-A.PNG](IPv6%20conf%20PC-A.PNG)

Очевидно, что от маршрутизатора был получен назначенный префикс сети от e0/1 R1 **2001:DB8:ACAD:1**, тогда как
оставшуюся часть адреса (префикс интерфейса) **2050:79ff:fe66:6805** получена на основе собственного MAC адреса
хоста **00:50:79:66:68:05** по методу EUI-64.

![IPv6 conf PC-B.PNG](IPv6%20conf%20PC-B.PNG)
Аналогично был присвоен адрес IPv6 хосту PC-B с помощью SLAAC от e0/0 R2

Проверка доступности адреса PC-B от PC-A
![IPv6 ping A to B.PNG](IPv6%20ping%20A%20to%20B.PNG)

### 3. Настройка и проверка сервера DHCPv6 без отслеживания состояния на маршрутизаторе R1.

![IPv6 conf PC-A_1.PNG](IPv6%20conf%20PC-A_1.PNG)

Из конфигурации PC-A видно, что не назначен адрес DNS сервера

Настроим маршрутизатор R1 для предоставления DHCPv6 без отслеживания состояния для PC-A. 
Создаем DHCPv6 pool
````
R1(config)#ipv6 dhcp pool R1-STATELESS
R1(config-dhcpv6)#dns-server 2001:db8:acad::254
R1(config-dhcpv6)#domain-name STATELESS.com
````
Настроим интерфейс e0/0.100 на маршрутизаторе R1, чтобы предоставить флаг конфигурации OTHER 
для локальной сети маршрутизатора R1, и укажем только что созданный пул DHCP в качестве ресурса DHCP
для этого интерфейса.
````
R1(config)#interface e0/0.100
R1(config-subif)#ipv6 nd other-config-flag
R1(config-subif)#ipv6 dhcp server R1-STATELESS
R1(config-subif)#do write
````
### 4. Настройка сервера DHCPv6 с отслеживанием состояния на маршрутизаторе R1.

Создаем пул DHCPv6 на маршрутизаторе R1 для сети 2001:db8:acad:3:aaaa::/80.
Это предоставит адреса локальной сети, подключенной к интерфейсу e0/0 на маршрутизаторе R2.
В составе пула установим DNS-сервер 2001:db8:acad::254 и установим имя домена STATEFUL.com.
````
R1(config)# ipv6 dhcp pool R2-STATEFUL
R1(config-dhcp)# address prefix 2001:db8:acad:3:aaa::/80
R1(config-dhcp)# dns-server 2001:db8:acad::254
R1(config-dhcp)# domain-name STATEFUL.com
````
Назначаем созданный пул интерфейсу  e0/0 R1.
````
R1(config)# interface e0/1
R1(config-if)# ipv6 dhcp server R2-STATEFUL
````

### 5. Настройка и проверка ретраснсляции DHCPv6 на маршрутизаторе R2

Проверим сетевые настройки PC-B
![IPv6 conf PC-B_1.PNG](IPv6%20conf%20PC-B_1.PNG)

IPv6 адрес по-прежнему получен с помощью SLAAC от e0/0 R2.

Производим настройку ретрансляции DHCPv6 на интерфейсе e0/0 R2.
В качестве IPv6 адреса сервера DHCP указываем адрес интерфейса e0/1 R1.
````
R2(config)#interface e0/0
R2(config-if)#ipv6 dhcp relay destination 2001:DB8:ACAD:2::1 e0/1
````
Установим значение флага M с 0 на 1 для сообщений RA.
````
R2(config-if)#ipv6 nd managed-config-flag
````
Проверяем сетевые настройки PC-B
![PC-B_2_1.PNG](PC-B_2_1.PNG)

Как видно настройки от сервера DHCPv6 не были получены. Для проверки добавим в схему 
маршрутизатор R7
![Shem-Net-LAB03_R7.PNG](Shem-Net-LAB03_R7.PNG)

Задаем для интерфейса e0/0 R7 команды
````
R7(config-if)# ip address dhcp
R7(config-if)# ipv6 enable
R7(config-if)# ipv6 address dhcp
````
После, проверяем результат командой
````
R7#sh ipv6 interface brief
````
![Sh_DHCP_R7.PNG](Sh_DHCP_R7.PNG)

Теперь видно, что был назначен адрес с префиксом сети 2001:db8:acad:3:aaa
полученном от сервера DHCPv6
