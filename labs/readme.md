## Проектная работа
## Построение сети оператора по предоставлению IP транзитных услуг

Постановка целей:

1. Повторение пройденных материалов и закрепление навыков.
2. Самостоятельно изучить принципы работы сетей с использованием технологии MPLS-TE.

Задачи:

1. Разработать схему лабораторного стенда, задокументировать адресное пространство.
2. Для всех сетевых элементов выполнить первичные настройки, интерфейсам присвоить IP адреса.
3. Настроить сеть офиса оператора.








1. Разработать схему лабораторного стенда, задокументировать адресное пространство.

Схема лабораторного стенда



Таблица адресов

| Hostname | Interface | Description | IPv4 address  | Subnet mask     | Gateway     | IPv6 address                  | IPV6 LLA  | Network             |
|----------|-----------|-------------|---------------|-----------------|-------------|-------------------------------|-----------|---------------------|
| R1       | e0/0      | to_R6       | 192.168.0.1   | 255.255.255.252 |             | 2022:a304:20bf::1:1:6/96      | FE80::1   | 99.13.77.0/24       |
|          | e0/1      | to_R3       | 192.168.0.21  | 255.255.255.252 |             | 2022:a304:20bf::6:1:3/96      | FE80::1   | 2022:a304:20bf::/48 |
|          | e0/2      | to_R2       | 192.168.0.17  | 255.255.255.252 |             | 2022:a304:20bf::5:1:2/96      | FE80::1   |                     |
|          | e0/3      | to_R14      | 99.13.77.0    | 255.255.255.254 |             | 2022:a304:20bf::1/112         | FE80::1   |                     |
|          | e1/0      | to_R5       | 192.168.0.9   | 255.255.255.252 |             | 2022:a304:20bf::3:1:5/96      | FE80::1   |                     |
|          | e1/1      | to_R4       | 192.168.0.25  | 255.255.255.252 |             | 2022:a304:20bf::7:1:4/96      | FE80::1   |                     |
|          | Loopback0 |             | 192.168.1.1   | 255.255.255.255 |             | 2022:a304:20bf:8::1/128       |           |                     |
| R2       | e0/0      | to_R5       | 192.168.0.5   | 255.255.255.252 |             | 2022:a304:20bf::2:2:5/96      | FE80::2   |                     |
|          | e0/1      | to_R4       | 192.168.0.29  | 255.255.255.252 |             | 2022:a304:20bf::8:2:4/96      | FE80::2   |                     |
|          | e0/2      | to_R1       | 192.168.0.18  | 255.255.255.252 |             | 2022:a304:20bf::5:2:1/96      | FE80::2   |                     |
|          | e0/3      | to_R36      | 110.1.22.8    | 255.255.255.254 |             | 2022:abcc:318:abab:18::41/112 | FE80::2   |                     |
|          | e1/0      | to_R6       | 192.168.0.13  | 255.255.255.252 |             | 2022:a304:20bf::4:2:6/96      | FE80::2   |                     |
|          | e1/1      | to_R3       | 192.168.0.33  | 255.255.255.252 |             | 2022:a304:20bf::9:2:3/96      | FE80::2   |                     |
|          | Loopback0 |             | 192.168.1.2   | 255.255.255.255 |             | 2022:a304:20bf:8::2/128       |           |                     |
| R3       | e0/0      | to_R1       | 192.168.0.22  | 255.255.255.252 |             | 2022:a304:20bf::6:3:1/96      | FE80::3   |                     |
|          | e0/1      | to_R4       | 192.168.0.37  | 255.255.255.252 |             | 2022:a304:20bf::a:3:4/96      | FE80::3   |                     |
|          | e0/2.21   | to_SW1      | 192.168.21.2  | 255.255.255.0   |             | 2022:a304:20bf:21::1/64       | FE80::1:3 |                     |
|          | e0/3.20   | to_SW2      | 192.168.20.2  | 255.255.255.0   |             | 2022:a304:20bf:20::1/64       | FE80::2:3 |                     |
|          | e1/0      | to_R2       | 192.168.0.34  | 255.255.255.252 |             | 2022:a304:20bf::9:3:2/96      | FE80::3   |                     |
|          | Loopback0 |             | 192.168.1.3   | 255.255.255.255 |             | 2022:a304:20bf:8::3/128       |           |                     |
| R4       | e0/0      | to_R2       | 192.168.0.30  | 255.255.255.252 |             | 2022:a304:20bf::8:4:2/96      | FE80::4   |                     |
|          | e0/1      | to_R3       | 192.168.0.38  | 255.255.255.252 |             | 2022:a304:20bf::a:4:3/96      | FE80::4   |                     |
|          | e0/2.20   | to_SW2      | 192.168.20.3  | 255.255.255.0   |             | 2022:a304:20bf:20::2/64       | FE80::2:4 |                     |
|          | e0/3.21   | to_SW1      | 192.168.21.3  | 255.255.255.0   |             | 2022:a304:20bf:21::2/64       | FE80::1:4 |                     |
|          | e1/0      | to_R1       | 192.168.0.26  | 255.255.255.252 |             | 2022:a304:20bf::7:4:1/96      | FE80::4   |                     |
|          | Loopback0 |             | 192.168.1.4   | 255.255.255.255 |             | 2022:a304:20bf:8::4/128       |           |                     |
| SW1      | e0/0      | to_R3       |               |                 |             |                               |           |                     |
|          | e0/1      | to_R4       |               |                 |             |                               |           |                     |
|          | VLAN10    | Customer1   |               |                 |             |                               |           |                     |
|          | VLAN99    | MGMT        | 192.168.2.4   | 255.255.255.0   | 192.168.2.1 | 2022:a304:20bf:8::1:1/128     |           |                     |
| SW2      | e0/0      | to_R4       |               |                 |             |                               |           |                     |
|          | e0/1      | to_R3       |               |                 |             |                               |           |                     |
|          | VLAN20    | Customer2   |               |                 |             |                               |           |                     |
|          | VLAN99    | MGMT        | 192.168.2.5   | 255.255.255.0   | 192.168.2.1 | 2022:a304:20bf:8::1:2/128     |           |                     |
| VPC1     | NIC       |             | DHCP          |                 |             |                               |           |                     |
| VPC7     | NIC       |             | DHCP          |                 |             |                               |           |                     |
| R5       | e0/0      | to_R2       | 192.168.0.6   | 255.255.255.252 |             | 2022:a304:20bf::2:5:2/96      | FE80::5   |                     |
|          | e0/1      | to_R7       | 192.168.11.1  | 255.255.255.252 |             |                               |           |                     |
|          | e0/2      | to_R6       | 192.168.11.17 | 255.255.255.252 |             |                               |           |                     |
|          | e0/3      | to_R12      | 192.168.11.25 | 255.255.255.252 |             |                               |           |                     |
|          | e1/0      | to_R1       | 192.168.0.10  | 255.255.255.252 |             | 2022:a304:20bf::3:5:1/96      | FE80::5   |                     |
|          | e1/1      | to_R7       | 192.168.11.5  | 255.255.255.252 |             |                               |           |                     |
|          | e1/2      | to_R6       | 192.168.11.21 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.5  | 255.255.255.255 |             | 2022:a304:20bf:8::5/128       |           |                     |
| R6       | e0/0      | to_R1       | 192.168.0.2   | 255.255.255.252 |             | 2022:a304:20bf::1:6:1/96      | FE80::6   |                     |
|          | e0/1      | to_R8       | 192.168.11.9  | 255.255.255.252 |             |                               |           |                     |
|          | e0/2      | to_R5       | 192.168.11.18 | 255.255.255.252 |             |                               |           |                     |
|          | e1/0      | to_R2       | 192.168.0.14  | 255.255.255.252 |             | 2022:a304:20bf::4:6:2/96      | FE80::6   |                     |
|          | e1/1      | to_R8       | 192.168.11.13 | 255.255.255.252 |             |                               |           |                     |
|          | e1/2      | to_R5       | 192.168.11.22 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.6  | 255.255.255.255 |             | 2022:a304:20bf:8::6/128       |           |                     |
| R7       | e0/0      | to_R5       | 192.168.11.1  | 255.255.255.252 |             |                               |           |                     |
|          | e0/1      | to_R10      | 192.168.11.33 | 255.255.255.252 |             |                               |           |                     |
|          | e0/3      | to_R12      | 192.168.11.30 | 255.255.255.252 |             |                               |           |                     |
|          | e1/0      | to_R5       | 192.168.11.6  | 255.255.255.252 |             |                               |           |                     |
|          | e1/1      | to_R9       | 192.168.11.50 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.7  | 255.255.255.255 |             |                               |           |                     |
| R8       | e0/0      | to_R6       | 192.168.11.10 | 255.255.255.252 |             |                               |           |                     |
|          | e0/1      | to_R9       | 192.168.11.45 | 255.255.255.252 |             |                               |           |                     |
|          | e1/0      | to_R6       | 192.168.11.14 | 255.255.255.252 |             |                               |           |                     |
|          | e1/1      | to_R11      | 192.168.11.42 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.8  | 255.255.255.255 |             |                               |           |                     |
| R9       | e0/0      | to_R8       | 192.168.11.46 | 255.255.255.252 |             |                               |           |                     |
|          | e0/1      | to_R7       | 192.168.11.49 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.9  | 255.255.255.255 |             |                               |           |                     |
| R10      | e0/0      | to_R7       | 192.168.11.34 | 255.255.255.252 |             |                               |           |                     |
|          | e0/1      | to_R11      | 192.168.11.37 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.10 | 255.255.255.255 |             |                               |           |                     |
| R11      | e0/0      | to_R10      | 192.168.11.38 | 255.255.255.252 |             |                               |           |                     |
|          | e0/1      | to_R8       | 192.168.11.41 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.11 | 255.255.255.255 |             |                               |           |                     |
| R12      | e0/0      | to_R5       | 192.168.11.26 | 255.255.255.252 |             |                               |           |                     |
|          | e0/1      | to_R7       | 192.168.11.29 | 255.255.255.252 |             |                               |           |                     |
|          | Loopback0 |             | 192.168.10.12 | 255.255.255.255 |             |                               |           |                     |
| R31      | e0/0      | to_R33      | 10.10.0.1     | 255.255.255.252 |             | 2022:abcc:318:1::31:33/96     | FE80::31  | 110.1.22.0/24       |
|          | e0/1      | to_R32      | 10.10.0.5     | 255.255.255.252 |             | 2022:abcc:318:1::1:31:32/96   | FE80::31  | 2022:abcc:318::/48  |
|          | e0/2      | to_R35      | 10.10.0.25    | 255.255.255.252 |             | 2022:abcc:318:1::6:31:35/96   | FE80::31  |                     |
|          | e1/0      | to_R34      | 10.10.0.9     | 255.255.255.252 |             | 2022:abcc:318:1::2:31:34/96   | FE80::31  |                     |
|          | Loopback0 |             | 10.10.8.31    | 255.255.255.255 |             | 2022:abcc:318:8::31/128       |           |                     |
| R32      | e0/0      | to_R34      | 10.10.0.13    | 255.255.255.252 |             | 2022:abcc:318:1::3:32:34/96   | FE80::32  |                     |
|          | e0/1      | to_R31      | 10.10.0.6     | 255.255.255.252 |             | 2022:abcc:318:1::1:32:31/96   | FE80::32  |                     |
|          | e0/2      | to_R36      | 10.10.0.34    | 255.255.255.252 |             | 2022:abcc:318:1::8:32:36/96   | FE80::32  |                     |
|          | e1/0      | to_R33      | 10.10.0.17    | 255.255.255.252 |             | 2022:abcc:318:1::4:32:33/96   | FE80::32  |                     |
|          | Loopback0 |             | 10.10.8.32    | 255.255.255.255 |             | 2022:abcc:318:8::32/128       |           |                     |
| R33      | e0/0      | to_R31      | 10.10.0.2     | 255.255.255.252 |             | 2022:abcc:318:1::33:31/96     | FE80::33  |                     |
|          | e0/1      | to_R34      | 10.10.0.21    | 255.255.255.252 |             | 2022:abcc:318:1::5:33:34/96   | FE80::33  |                     |
|          | e0/2      | to_R37      | 10.10.0.37    | 255.255.255.252 |             | 2022:abcc:318:1::9:33:37/96   | FE80::33  |                     |
|          | e1/0      | to_R32      | 10.10.0.18    | 255.255.255.252 |             | 2022:abcc:318:1::4:33:32/96   | FE80::33  |                     |
|          | Loopback0 |             | 10.10.8.33    | 255.255.255.255 |             | 2022:abcc:318:8::33/128       |           |                     |
| R34      | e0/0      | to_R32      | 10.10.0.14    | 255.255.255.252 |             | 2022:abcc:318:1::3:34:32/96   | FE80::34  |                     |
|          | e0/1      | to_R33      | 10.10.0.22    | 255.255.255.252 |             | 2022:abcc:318:1::5:34:33/96   | FE80::34  |                     |
|          | e0/2      | to_R37      | 10.10.0.42    | 255.255.255.252 |             | 2022:abcc:318:1::a:34:37/96   | FE80::34  |                     |
|          | e1/0      | to_R31      | 10.10.0.10    | 255.255.255.252 |             | 2022:abcc:318:1::2:34:31/96   | FE80::34  |                     |
|          | Loopback0 |             | 10.10.8.34    | 255.255.255.255 |             | 2022:abcc:318:8::34/128       |           |                     |
| R35      | e0/1      | to_R14      | 135.200.13.50 | 255.255.255.254 |             | 2022:a304:11aa:1::1:21/112    | FE80::35  |                     |
|          | e0/2      | to_R31      | 10.10.0.26    | 255.255.255.252 |             | 2022:abcc:318:1::6:35:31/96   | FE80::35  |                     |
|          | e0/3      | to_R36      | 10.10.0.29    | 255.255.255.252 |             | 2022:abcc:318:1::7:35:36/96   | FE80::35  |                     |
|          | Loopback0 |             | 10.10.8.35    | 255.255.255.255 |             | 2022:abcc:318:8::35/128       |           |                     |
| R36      | e0/0      | to_R2       | 110.1.22.9    | 255.255.255.254 |             | 2022:abcc:318:abab:18::40/112 | FE80::36  |                     |
|          | e0/2      | to_R32      | 10.10.0.33    | 255.255.255.252 |             | 2022:abcc:318:1::8:36:32/96   | FE80::36  |                     |
|          | e0/3      | to_R35      | 10.10.0.30    | 255.255.255.252 |             | 2022:abcc:318:1::7:36:35/96   | FE80::36  |                     |
|          | Loopback0 |             | 10.10.8.36    | 255.255.255.255 |             | 2022:abcc:318:8::36/128       |           |                     |
| R37      | e0/0      | to_R33      | 10.10.0.38    | 255.255.255.252 |             | 2022:abcc:318:1::9:37:33/96   | FE80::37  |                     |
|          | e0/1      | to_R34      | 10.10.0.41    | 255.255.255.252 |             | 2022:abcc:318:1::a:37:34/96   | FE80::37  |                     |
|          | Loopback0 |             | 10.10.8.37    | 255.255.255.255 |             | 2022:abcc:318:8::37/128       |           |                     |
| R14      | e0/0      | to_R1       | 99.13.77.1    | 255.255.255.254 |             | 2022:a304:20bf::2/112         | FE80::14  | 135.200.13.0/24     |
|          | e0/1      | to_R35      | 135.200.13.51 | 255.255.255.254 |             | 2022:a304:11aa:1::1:20/112    | FE80::14  | 2022:a304:11aa::/48 |
|          | Loopback0 |             | 10.10.10.14   | 255.255.255.255 |             | 2022:a304:11aa:8::14/128      |

2. Для всех сетевых элементов выполнить первичные настройки, интерфейсам присвоить IP адреса.
Покажем на примере настройки R1.
````
hostname R1
!
boot-start-marker
boot-end-marker
!
enable secret 5 $1$Ij0c$LbyRcNuJEcl2zCZ0MiBx3/
!
no aaa new-model
clock timezone MSK 3 0
mmi polling-interval 60
no mmi auto-configure
no mmi pvc
mmi snmp-timeout 180
!
no ip domain lookup
ip domain name OperaTor.ru
ip cef
ipv6 unicast-routing
ipv6 cef
!
multilink bundle-name authenticated
!
username admin privilege 15 secret 5 $1$jkKc$ZJL1U9SJCdFkhlKZEs7j01
!
redundancy
!
interface Loopback0
 ip address 192.168.1.1 255.255.255.255
 ipv6 address 2022:A304:20BF:8::1/128
!
interface Ethernet0/0
 description to_R6
 ip address 192.168.0.1 255.255.255.252
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::1:1:6/96
 ipv6 enable
!
interface Ethernet0/1
 description to_R3
 ip address 192.168.0.21 255.255.255.252
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::6:1:3/96
 ipv6 enable
!
interface Ethernet0/2
 description to_R2
 ip address 192.168.0.17 255.255.255.252
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::5:1:2/96
 ipv6 enable
!
interface Ethernet0/3
 description to_R14
 ip address 99.13.77.0 255.255.255.254
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::1/112
 ipv6 enable
!
interface Ethernet1/0
 description to_R5
 ip address 192.168.0.9 255.255.255.252
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::3:1:5/96
 ipv6 enable
!
interface Ethernet1/1
 description to_R4
 ip address 192.168.0.25 255.255.255.252
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::7:1:4/96
 ipv6 enable
!
interface Ethernet1/2
 no ip address
 shutdown
!
interface Ethernet1/3
 no ip address
 shutdown
!
ip forward-protocol nd
!
no ip http server
no ip http secure-server
!
control-plane
!
banner motd ^C Unauthorized access is strictly prohibited ^C
!
line con 0
 exec-timeout 0 0
 password 7 094F471A1A0A
 logging synchronous
 login
line aux 0
line vty 0 4
 exec-timeout 15 0
 password 7 01100F175804
 logging synchronous
 login
 transport input none
!
end
````
3. Настроить сеть офиса оператора.

Выполним настройку коммутаторов SW1 и SW2 сети доступа. 
Здесь VLAN 21 - пользовательский, VLAN 99 - управление коммутатором. В целях повышения безопасности изменен VLAN по умолчанию с 1 на 4094.
Для всех не используемых портов назначен VLAN 4093.

Применены подходы по защите от атаки VLAN Hopping 
- все порты коммутаторов настроены вручную либо в режиме Trunk (магистральный) или Access (доступа)
- отключены неиспользуемые порты и им назначен неиспользуемый VLAN 4093
- установлен для native VLAN 4094, отличный от VLAN1

Для нейтрализация атак таблицы MAC-адресов применена защита портов.
Здесь в большей степени имеет значение защита собственной сети от не санкционированного подключения.
Все рабочие места должны быть должным образом оборудованы терминалами связанными с технологическим процессом и не допустить появление сторонних 
устройств крайне важно. Поэтому клинтские порты настроены так, что-бы определенному порту соответсвовал только один сетевой терминал.
Это безусловно накладывает дополнительную нагрузку на администраторов сети, в случае замены терминалов или в случае когда необходимо выполнить
переключение на другой порт даже в пределах одного коммутатора.
В случае если сотруднику будет необхдимо подключить например рабочий ноутбук вместо стационарного ПК, можно будет увеличить максимальное кол-во изученных адресов
и добавить нужный MAC-адрес вручную.

Применены защита от ARP атак и атак DHCP.

Покажем на примере конфигурации SW1
````
hostname SW1
!
boot-start-marker
boot-end-marker
!
!
enable secret 5 $1$inTI$Hru8qRfAb.F94KpTghgpO.
!
username admin privilege 15 secret 5 $1$UrB8$F1z7iFfdUtZ2faoE75j4v/
no aaa new-model
clock timezone MSK 3 0
!
ip arp inspection vlan 21
!
ip dhcp snooping vlan 21
ip dhcp snooping
no ip domain-lookup
ip domain-name OperaTor.ru
ip cef
no ipv6 cef
!
spanning-tree mode rapid-pvst
spanning-tree extend system-id
!
vlan internal allocation policy ascending
!
vlan 4093
 name Parking
!
vlan 4094
 name Native
!
interface Ethernet0/0
 description to_R3
 switchport trunk allowed vlan 21,99
 switchport trunk encapsulation dot1q
 switchport trunk native vlan 4094
 switchport mode trunk
 ip arp inspection trust
 ip dhcp snooping trust
!
interface Ethernet0/1
 description to_R4
 switchport trunk allowed vlan 21,99
 switchport trunk encapsulation dot1q
 switchport trunk native vlan 4094
 switchport mode trunk
 ip arp inspection trust
 ip dhcp snooping trust
!
interface Ethernet0/2
 description to_VPC21
 switchport access vlan 21
 switchport mode access
 switchport port-security mac-address sticky
 switchport port-security mac-address sticky 0050.7966.681d
 switchport port-security aging static
 switchport port-security
 spanning-tree portfast edge
 spanning-tree bpduguard enable
!
interface Ethernet0/3
 switchport access vlan 4093
 switchport mode access
 shutdown
!
interface Ethernet1/0
 switchport access vlan 4093
 switchport mode access
 shutdown
!
interface Ethernet1/1
 switchport access vlan 4093
 switchport mode access
 shutdown
!
interface Ethernet1/2
 switchport access vlan 4093
 switchport mode access
 shutdown
!
interface Ethernet1/3
 switchport access vlan 4093
 switchport mode access
 shutdown
!
interface Vlan99
 ip address 192.168.2.4 255.255.255.0
 ipv6 address 2022:A304:20BF:8::1:1/128
!
ip default-gateway 192.168.2.1
ip forward-protocol nd
!
no ip http server
no ip http secure-server
!
control-plane
!
banner motd ^C Unauthorized access is strictly prohibited ^C
!
line con 0
 exec-timeout 0 0
 password 7 13061E010803
 logging synchronous
 login
line aux 0
line vty 0 4
 exec-timeout 15 0
 password 7 01100F175804
 logging synchronous
 login
!
!
end
````
Несколько результатов выводов по настройке коммутатора для иллюстрации.
````
SW1#sh vlan

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active
21   Client21                         active    Et0/2
99   MGMT                             active
1002 fddi-default                     act/unsup
1003 token-ring-default               act/unsup
1004 fddinet-default                  act/unsup
1005 trnet-default                    act/unsup
4093 Parking                          active    Et0/3, Et1/0, Et1/1, Et1/2
                                                Et1/3
4094 Native                           active
````
````
SW1#sh int trunk

Port        Mode             Encapsulation  Status        Native vlan
Et0/0       on               802.1q         trunking      4094
Et0/1       on               802.1q         trunking      4094

Port        Vlans allowed on trunk
Et0/0       21,99
Et0/1       21,99

Port        Vlans allowed and active in management domain
Et0/0       21,99
Et0/1       21,99

Port        Vlans in spanning tree forwarding state and not pruned
Et0/0       21,99
Et0/1       21,99
````
````
SW1#sh port-security interface e0/2
Port Security              : Enabled
Port Status                : Secure-up
Violation Mode             : Shutdown
Aging Time                 : 0 mins
Aging Type                 : Absolute
SecureStatic Address Aging : Enabled
Maximum MAC Addresses      : 1
Total MAC Addresses        : 1
Configured MAC Addresses   : 0
Sticky MAC Addresses       : 1
Last Source Address:Vlan   : 0000.0000.0000:0
Security Violation Count   : 0

SW1#sh port-security address
               Secure Mac Address Table
-----------------------------------------------------------------------------
Vlan    Mac Address       Type                          Ports   Remaining Age
                                                                   (mins)
----    -----------       ----                          -----   -------------
  21    0050.7966.681d    SecureSticky                  Et0/2        -
-----------------------------------------------------------------------------
Total Addresses in System (excluding one mac per port)     : 0
Max Addresses limit in System (excluding one mac per port) : 4096
SW1#
````
В окончании данного раздела можно добавить следующие моменты:
 - сложно представить, что у оператора работают не компетентные сотрудники. Скорее всего они знают, что делают, но никто не застрахован от ошибок. 
   Например, кто-то принес домашний роутер и ему удалось за счет подмены MAC адреса подключить его в локальную сеть. И тут защита от DHCP атаки 
   выглядит уже не такой избыточной.
 - При добавлении нового VLAN в существующий транковый порт команда _**switchport trunk allowed vlan 100**_ приведет к назначению VLAN 100 на указанный порт, но при этом
   все ранее назначенные VLAN будут удаленыи IOS не выдаст даже предупреждения. Не забываем добавлять в команду **_add_** в итоге команда будет выглядеть так _**switchport trunk allowed vlan add 100**_

Пример настройка SUB-интерфейсов на роутере R3.
Для обеспечения избыточности шлюзов применим проприетарный протокол Cisco GLBP, который не настраивался в лабораторной работе.
Настройку GLBP производим на группе из двух роутеров R3 и R4. В качестве AVG выбран R3, соотвественно R4 и R3 выполняют роль AVF.
````
````

























На сети ISP2 настроить протокол EIGRP, настройку IBGP выполнить с разбиением на 2 кластера с 2-мя роутрефлекторами.
На ядре сети оператора AS1000 выполнить настройку протокола OSPF. Настроить фрагмент сети офиса. Настроить сервер DHCP.
На фрагменте транспортной IP сети оператора настроить протокол IS-IS и запустить транспортный протокол MPLS-TE.
На траспортной сети оператора постоить туннели для пользователей 1 и 2
Настроить на стыках с провайдерами EBGP.ugugugyug