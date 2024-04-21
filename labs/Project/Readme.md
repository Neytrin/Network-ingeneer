## Проектная работа
## Построение сети оператора по предоставлению IP транзитных услуг

Постановка целей:

1. Повторение пройденных материалов и закрепление навыков.
2. Самостоятельно изучить принципы работы сетей с использованием технологии MPLS-TE.

Задачи:

1. Разработать схему лабораторного стенда, задокументировать адресное пространство.
2. Для всех сетевых элементов выполнить первичные настройки, интерфейсам присвоить IP адреса.
3. Настроить сеть офиса оператора
- Настроить крммутаторы SW1 и SW2
- Настроить протокол GLBP на R3 и R4
- Настройка DHCP сервера на R3 и R4
- Настроить протокол OSPF
- На R1 и R2 настроить маршруты по-умолчанию.
4. Настроить EIGRP на сети провайдера ISP2.
5. Настроить eBGP между оператором и ISP, а так-же между ISP1 и ISP2.
6. 







1. Разработать схему лабораторного стенда, задокументировать адресное пространство.

Схема лабораторного стенда

![Shem_Project.png](Stend%2FShem_Project.png)

Таблица адресов

| Office   | Hostname | Interface | Description | IPv4 address  | Subnet mask     | Gateway     | IPv6 address                  | IPV6 LLA  | Network             |
|----------|----------|-----------|-------------|---------------|-----------------|-------------|-------------------------------|-----------|---------------------|
| Оператор | R1       | e0/0      | to_R6       | 192.168.0.1   | 255.255.255.252 |             | 2022:a304:20bf::1:1:6/96      | FE80::1   | 99.13.77.0/24       |
|          |          | e0/1      | to_R3       | 192.168.0.21  | 255.255.255.252 |             | 2022:a304:20bf::6:1:3/96      | FE80::1   | 2022:a304:20bf::/48 |
|          |          | e0/2      | to_R2       | 192.168.0.17  | 255.255.255.252 |             | 2022:a304:20bf::5:1:2/96      | FE80::1   |                     |
|          |          | e0/3      | to_R14      | 99.13.77.0    | 255.255.255.254 |             | 2022:a304:20bf::1/112         | FE80::1   |                     |
|          |          | e1/0      | to_R5       | 192.168.0.9   | 255.255.255.252 |             | 2022:a304:20bf::3:1:5/96      | FE80::1   |                     |
|          |          | e1/1      | to_R4       | 192.168.0.25  | 255.255.255.252 |             | 2022:a304:20bf::7:1:4/96      | FE80::1   |                     |
|          |          | Loopback0 |             | 192.168.1.1   | 255.255.255.255 |             | 2022:a304:20bf:8::1/128       |           |                     |
|          | R2       | e0/0      | to_R5       | 192.168.0.5   | 255.255.255.252 |             | 2022:a304:20bf::2:2:5/96      | FE80::2   |                     |
|          |          | e0/1      | to_R4       | 192.168.0.29  | 255.255.255.252 |             | 2022:a304:20bf::8:2:4/96      | FE80::2   |                     |
|          |          | e0/2      | to_R1       | 192.168.0.18  | 255.255.255.252 |             | 2022:a304:20bf::5:2:1/96      | FE80::2   |                     |
|          |          | e0/3      | to_R36      | 110.1.22.8    | 255.255.255.254 |             | 2022:abcc:318:abab:18::41/112 | FE80::2   |                     |
|          |          | e1/0      | to_R6       | 192.168.0.13  | 255.255.255.252 |             | 2022:a304:20bf::4:2:6/96      | FE80::2   |                     |
|          |          | e1/1      | to_R3       | 192.168.0.33  | 255.255.255.252 |             | 2022:a304:20bf::9:2:3/96      | FE80::2   |                     |
|          |          | Loopback0 |             | 192.168.1.2   | 255.255.255.255 |             | 2022:a304:20bf:8::2/128       |           |                     |
|          | R3       | e0/0      | to_R1       | 192.168.0.22  | 255.255.255.252 |             | 2022:a304:20bf::6:3:1/96      | FE80::3   |                     |
|          |          | e0/1      | to_R4       | 192.168.0.37  | 255.255.255.252 |             | 2022:a304:20bf::a:3:4/96      | FE80::3   |                     |
|          |          | e0/2.21   | to_SW1      | 192.168.21.2  | 255.255.255.0   |             | 2022:a304:20bf:21::1/64       | FE80::1:3 |                     |
|          |          | e0/2.99   | MGMT_SW1    | 192.168.2.2   | 255.255.255.0   |             |                               |           |                     |
|          |          | e0/3.20   | to_SW2      | 192.168.20.2  | 255.255.255.0   |             | 2022:a304:20bf:20::1/64       | FE80::2:3 |                     |
|          |          | e0/3.100  | MGMT_SW2    | 192.168.3.2   | 255.255.255.0   |             |                               |           |                     |
|          |          | e1/0      | to_R2       | 192.168.0.34  | 255.255.255.252 |             | 2022:a304:20bf::9:3:2/96      | FE80::3   |                     |
|          |          | Loopback0 |             | 192.168.1.3   | 255.255.255.255 |             | 2022:a304:20bf:8::3/128       |           |                     |
|          | R4       | e0/0      | to_R2       | 192.168.0.30  | 255.255.255.252 |             | 2022:a304:20bf::8:4:2/96      | FE80::4   |                     |
|          |          | e0/1      | to_R3       | 192.168.0.38  | 255.255.255.252 |             | 2022:a304:20bf::a:4:3/96      | FE80::4   |                     |
|          |          | e0/2.20   | to_SW2      | 192.168.20.3  | 255.255.255.0   |             | 2022:a304:20bf:20::2/64       | FE80::2:4 |                     |
|          |          | e0/2.100  | MGMT_SW2    | 192.168.3.3   | 255.255.255.0   |             |                               |           |                     |
|          |          | e0/3.21   | to_SW1      | 192.168.21.3  | 255.255.255.0   |             | 2022:a304:20bf:21::2/64       | FE80::1:4 |                     |
|          |          | e0/3.99   | MGMT_SW1    | 192.168.2.3   | 255.255.255.0   |             |                               |           |                     |
|          |          | e1/0      | to_R1       | 192.168.0.26  | 255.255.255.252 |             | 2022:a304:20bf::7:4:1/96      | FE80::4   |                     |
|          |          | Loopback0 |             | 192.168.1.4   | 255.255.255.255 |             | 2022:a304:20bf:8::4/128       |           |                     |
|          | SW1      | e0/0      | to_R3       |               |                 |             |                               |           |                     |
|          |          | e0/1      | to_R4       |               |                 |             |                               |           |                     |
|          |          | VLAN10    | Customer1   |               |                 |             |                               |           |                     |
|          |          | VLAN99    | MGMT        | 192.168.2.4   | 255.255.255.0   | 192.168.2.1 | 2022:a304:20bf:8::1:1/128     |           |                     |
|          | SW2      | e0/0      | to_R4       |               |                 |             |                               |           |                     |
|          |          | e0/1      | to_R3       |               |                 |             |                               |           |                     |
|          |          | VLAN20    | Customer2   |               |                 |             |                               |           |                     |
|          |          | VLAN100   | MGMT        | 192.168.3.4   | 255.255.255.0   | 192.168.3.1 | 2022:a304:20bf:8::1:2/128     |           |                     |
|          | VPC1     | NIC       |             | DHCP          |                 |             |                               |           |                     |
|          | VPC7     | NIC       |             | DHCP          |                 |             |                               |           |                     |
|          | R5       | e0/0      | to_R2       | 192.168.0.6   | 255.255.255.252 |             | 2022:a304:20bf::2:5:2/96      | FE80::5   |                     |
|          |          | e0/1      | to_R7       | 192.168.11.1  | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/2      | to_R6       | 192.168.11.17 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/3      | to_R12      | 192.168.11.25 | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/0      | to_R1       | 192.168.0.10  | 255.255.255.252 |             | 2022:a304:20bf::3:5:1/96      | FE80::5   |                     |
|          |          | e1/1      | to_R7       | 192.168.11.5  | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/2      | to_R6       | 192.168.11.21 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.5  | 255.255.255.255 |             | 2022:a304:20bf:8::5/128       |           |                     |
|          | R6       | e0/0      | to_R1       | 192.168.0.2   | 255.255.255.252 |             | 2022:a304:20bf::1:6:1/96      | FE80::6   |                     |
|          |          | e0/1      | to_R8       | 192.168.11.9  | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/2      | to_R5       | 192.168.11.18 | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/0      | to_R2       | 192.168.0.14  | 255.255.255.252 |             | 2022:a304:20bf::4:6:2/96      | FE80::6   |                     |
|          |          | e1/1      | to_R8       | 192.168.11.13 | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/2      | to_R5       | 192.168.11.22 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.6  | 255.255.255.255 |             | 2022:a304:20bf:8::6/128       |           |                     |
|          | R7       | e0/0      | to_R5       | 192.168.11.1  | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/1      | to_R10      | 192.168.11.33 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/3      | to_R12      | 192.168.11.30 | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/0      | to_R5       | 192.168.11.6  | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/1      | to_R9       | 192.168.11.50 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.7  | 255.255.255.255 |             |                               |           |                     |
|          | R8       | e0/0      | to_R6       | 192.168.11.10 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/1      | to_R9       | 192.168.11.45 | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/0      | to_R6       | 192.168.11.14 | 255.255.255.252 |             |                               |           |                     |
|          |          | e1/1      | to_R11      | 192.168.11.42 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.8  | 255.255.255.255 |             |                               |           |                     |
|          | R9       | e0/0      | to_R8       | 192.168.11.46 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/1      | to_R7       | 192.168.11.49 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.9  | 255.255.255.255 |             |                               |           |                     |
|          | R10      | e0/0      | to_R7       | 192.168.11.34 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/1      | to_R11      | 192.168.11.37 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.10 | 255.255.255.255 |             |                               |           |                     |
|          | R11      | e0/0      | to_R10      | 192.168.11.38 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/1      | to_R8       | 192.168.11.41 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.11 | 255.255.255.255 |             |                               |           |                     |
|          | R12      | e0/0      | to_R5       | 192.168.11.26 | 255.255.255.252 |             |                               |           |                     |
|          |          | e0/1      | to_R7       | 192.168.11.29 | 255.255.255.252 |             |                               |           |                     |
|          |          | Loopback0 |             | 192.168.10.12 | 255.255.255.255 |             |                               |           |                     |
| ISP1     | R31      | e0/0      | to_R33      | 10.10.0.1     | 255.255.255.252 |             | 2022:abcc:318:1::31:33/96     | FE80::31  | 110.1.22.0/24       |
|          |          | e0/1      | to_R32      | 10.10.0.5     | 255.255.255.252 |             | 2022:abcc:318:1::1:31:32/96   | FE80::31  | 2022:abcc:318::/48  |
|          |          | e0/2      | to_R35      | 10.10.0.25    | 255.255.255.252 |             | 2022:abcc:318:1::6:31:35/96   | FE80::31  |                     |
|          |          | e1/0      | to_R34      | 10.10.0.9     | 255.255.255.252 |             | 2022:abcc:318:1::2:31:34/96   | FE80::31  |                     |
|          |          | Loopback0 |             | 10.10.8.31    | 255.255.255.255 |             | 2022:abcc:318:8::31/128       |           |                     |
|          | R32      | e0/0      | to_R34      | 10.10.0.13    | 255.255.255.252 |             | 2022:abcc:318:1::3:32:34/96   | FE80::32  |                     |
|          |          | e0/1      | to_R31      | 10.10.0.6     | 255.255.255.252 |             | 2022:abcc:318:1::1:32:31/96   | FE80::32  |                     |
|          |          | e0/2      | to_R36      | 10.10.0.34    | 255.255.255.252 |             | 2022:abcc:318:1::8:32:36/96   | FE80::32  |                     |
|          |          | e1/0      | to_R33      | 10.10.0.17    | 255.255.255.252 |             | 2022:abcc:318:1::4:32:33/96   | FE80::32  |                     |
|          |          | Loopback0 |             | 10.10.8.32    | 255.255.255.255 |             | 2022:abcc:318:8::32/128       |           |                     |
|          | R33      | e0/0      | to_R31      | 10.10.0.2     | 255.255.255.252 |             | 2022:abcc:318:1::33:31/96     | FE80::33  |                     |
|          |          | e0/1      | to_R34      | 10.10.0.21    | 255.255.255.252 |             | 2022:abcc:318:1::5:33:34/96   | FE80::33  |                     |
|          |          | e0/2      | to_R37      | 10.10.0.37    | 255.255.255.252 |             | 2022:abcc:318:1::9:33:37/96   | FE80::33  |                     |
|          |          | e1/0      | to_R32      | 10.10.0.18    | 255.255.255.252 |             | 2022:abcc:318:1::4:33:32/96   | FE80::33  |                     |
|          |          | Loopback0 |             | 10.10.8.33    | 255.255.255.255 |             | 2022:abcc:318:8::33/128       |           |                     |
|          | R34      | e0/0      | to_R32      | 10.10.0.14    | 255.255.255.252 |             | 2022:abcc:318:1::3:34:32/96   | FE80::34  |                     |
|          |          | e0/1      | to_R33      | 10.10.0.22    | 255.255.255.252 |             | 2022:abcc:318:1::5:34:33/96   | FE80::34  |                     |
|          |          | e0/2      | to_R37      | 10.10.0.42    | 255.255.255.252 |             | 2022:abcc:318:1::a:34:37/96   | FE80::34  |                     |
|          |          | e1/0      | to_R31      | 10.10.0.10    | 255.255.255.252 |             | 2022:abcc:318:1::2:34:31/96   | FE80::34  |                     |
|          |          | Loopback0 |             | 10.10.8.34    | 255.255.255.255 |             | 2022:abcc:318:8::34/128       |           |                     |
|          | R35      | e0/1      | to_R14      | 135.200.13.50 | 255.255.255.254 |             | 2022:a304:11aa:1::1:21/112    | FE80::35  |                     |
|          |          | e0/2      | to_R31      | 10.10.0.26    | 255.255.255.252 |             | 2022:abcc:318:1::6:35:31/96   | FE80::35  |                     |
|          |          | e0/3      | to_R36      | 10.10.0.29    | 255.255.255.252 |             | 2022:abcc:318:1::7:35:36/96   | FE80::35  |                     |
|          |          | Loopback0 |             | 10.10.8.35    | 255.255.255.255 |             | 2022:abcc:318:8::35/128       |           |                     |
|          | R36      | e0/0      | to_R2       | 110.1.22.9    | 255.255.255.254 |             | 2022:abcc:318:abab:18::40/112 | FE80::36  |                     |
|          |          | e0/2      | to_R32      | 10.10.0.33    | 255.255.255.252 |             | 2022:abcc:318:1::8:36:32/96   | FE80::36  |                     |
|          |          | e0/3      | to_R35      | 10.10.0.30    | 255.255.255.252 |             | 2022:abcc:318:1::7:36:35/96   | FE80::36  |                     |
|          |          | Loopback0 |             | 10.10.8.36    | 255.255.255.255 |             | 2022:abcc:318:8::36/128       |           |                     |
|          | R37      | e0/0      | to_R33      | 10.10.0.38    | 255.255.255.252 |             | 2022:abcc:318:1::9:37:33/96   | FE80::37  |                     |
|          |          | e0/1      | to_R34      | 10.10.0.41    | 255.255.255.252 |             | 2022:abcc:318:1::a:37:34/96   | FE80::37  |                     |
|          |          | Loopback0 |             | 10.10.8.37    | 255.255.255.255 |             | 2022:abcc:318:8::37/128       |           |                     |
| ISP2     | R14      | e0/0      | to_R1       | 99.13.77.1    | 255.255.255.254 |             | 2022:a304:20bf::2/112         | FE80::14  | 135.200.13.0/24     |
|          |          | e0/1      | to_R35      | 135.200.13.51 | 255.255.255.254 |             | 2022:a304:11aa:1::1:20/112    | FE80::14  | 2022:a304:11aa::/48 |
|          |          | Loopback0 |             | 10.10.10.14   | 255.255.255.255 |             | 2022:a304:11aa:8::14/128      |




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

#### Настройка коммутаторов сети доступа.

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

#### Настройка SUB интерфейсов на R3 и R4.

Пример настройки SUB-интерфейсов на роутере R3.
Для обеспечения избыточности шлюзов применим проприетарный протокол Cisco GLBP, который не настраивался в лабораторной работе.
Настройку GLBP производим на группе из двух роутеров R3 и R4. В качестве AVG выбран R3, соотвественно R4 и R3 выполняют роль AVF.
````
track 1 interface Ethernet0/0 line-protocol
track 2 interface Ethernet0/1 line-protocol
!
interface Ethernet0/2
 description to_SW1
 no ip address
!
interface Ethernet0/2.21
 description to_Client21
 encapsulation dot1Q 21
 ip address 192.168.21.2 255.255.255.0
 glbp 1 ip 192.168.21.1
 glbp 1 priority 120
 glbp 1 preempt
 glbp 1 weighting 140 lower 100 upper 115
 glbp 1 load-balancing host-dependent
 glbp 1 authentication md5 key-string 7 1531021F0725
 glbp 1 name ipv4_Client21
 glbp 1 weighting track 1 decrement 30
 glbp 1 weighting track 2 decrement 20
 glbp 2 ipv6 FE80::1:1
 glbp 2 priority 120
 glbp 2 preempt
 glbp 2 weighting 140 lower 100 upper 115
 glbp 2 load-balancing host-dependent
 glbp 2 authentication md5 key-string 7 1531021F0725
 glbp 2 name IPv6_Client21
 glbp 2 weighting track 1 decrement 30
 glbp 2 weighting track 2 decrement 20
 ipv6 address FE80::1:3 link-local
 ipv6 address 2022:A304:20BF:21::1/64
 ipv6 enable
!
interface Ethernet0/2.99
 description MGMT_SW1
 encapsulation dot1Q 99
 ip address 192.168.2.2 255.255.255.0
 glbp 99 ip 192.168.2.1
 glbp 99 priority 120
 glbp 99 preempt
 no glbp 99 load-balancing
 glbp 99 authentication md5 key-string 7 1531021F0725
 glbp 99 name IPv4_MGMT
!
interface Ethernet0/3
 description to_SW2
 no ip address
!
interface Ethernet0/3.20
 description to_Client20
 encapsulation dot1Q 20
 ip address 192.168.20.2 255.255.255.0
 glbp 1 ip 192.168.20.1
 glbp 1 priority 120
 glbp 1 preempt
 glbp 1 weighting 140 lower 100 upper 115
 glbp 1 load-balancing host-dependent
 glbp 1 authentication md5 key-string 7 1531021F0725
 glbp 1 name ipv4_Client20
 glbp 1 weighting track 1 decrement 30
 glbp 1 weighting track 2 decrement 20
 glbp 2 ipv6 FE80::2:1
 glbp 2 priority 120
 glbp 2 preempt
 glbp 2 weighting 140 lower 100 upper 115
 glbp 2 load-balancing host-dependent
 glbp 2 authentication md5 key-string 7 1531021F0725
 glbp 2 name IPv6_Client20
 glbp 2 weighting track 1 decrement 30
 glbp 2 weighting track 2 decrement 20
 ipv6 address FE80::2:3 link-local
 ipv6 address 2022:A304:20BF:20::1/64
 ipv6 enable
!
interface Ethernet0/3.100
 description MGMT_SW2
 encapsulation dot1Q 100
 ip address 192.168.3.2 255.255.255.0
 glbp 100 ip 192.168.3.1
 glbp 100 priority 120
 glbp 100 preempt
 no glbp 100 load-balancing
 glbp 100 authentication md5 key-string 7 1531021F0725
!
````
Для отслеживания состояния портов e0/0 и e0/1 созданы track. Настройка произведена так, что изменение состояний порта e0/0 будет приводить к понижению веса на 30, а для 
e0/1 - на 20. Пороги весов настроены так, что отключение одного из этих портров не изменит роли R3 как active forwarder. В случае когда оба порта перейдут в состояние down 
весь трафик будет перенаправлен через R4. Порог веса upper подобран таки образом, что R3 cнова будет участвовать в процессе распределения трафика только при включении порта e0/0, либо при 
включениии обоих портов e0/0 и e0/1. Поэтому восстановить линк по интерфейсу e0/0 будет приоритетом. 

Таймеры оставлены по умолчанию.
Планируем настроить NAT, поэтому для клиентских сетей выбрана балансировка host-dependent. Для сетей доступа к коммуторам балансировка отключена.
````
R3#sh glbp brief
Interface   Grp  Fwd Pri State    Address         Active router   Standby router
Et0/2.21    1    -   120 Active   192.168.21.1    local           unknown
Et0/2.21    1    1   -   Active   0007.b400.0101  local           -
Et0/2.21    2    -   120 Active   FE80::1:1       local           unknown
Et0/2.21    2    1   -   Active   0007.b400.0201  local           -
Et0/2.99    99   -   120 Active   192.168.2.1     local           unknown
Et0/2.99    99   1   -   Active   0007.b400.6301  local           -
Et0/3.20    1    -   120 Active   192.168.20.1    local           192.168.20.3
Et0/3.20    1    1   -   Listen   0007.b400.0101  192.168.20.3    -
Et0/3.20    1    2   -   Active   0007.b400.0102  local           -
Et0/3.20    2    -   120 Active   FE80::2:1       local           FE80::2:4
Et0/3.20    2    1   -   Listen   0007.b400.0201  FE80::2:4       -
Et0/3.20    2    2   -   Active   0007.b400.0202  local           -
Et0/3.100   100  -   120 Active   192.168.3.1     local           192.168.3.3
Et0/3.100   100  1   -   Listen   0007.b400.6401  192.168.3.3     -
Et0/3.100   100  2   -   Active   0007.b400.6402  local           -
R3#
````
#### Настройка DHCP серверов.

Конечно лучше если-бы функцию назначения IP адресов из заданного пула выполнял отдельный сервер. Но в нашем случае 
выполним настройку DHCPv4 и DHCPv6 серверов на роутерах R3 и R4.

Настройки покажем на примере R3. Настройки для R4 абсолютно идентичны.
````
ip dhcp excluded-address 192.168.20.1 192.168.20.3
ip dhcp excluded-address 192.168.21.1 192.168.21.3
!
ip dhcp pool Network_20
 network 192.168.20.0 255.255.255.0
 default-router 192.168.20.1
 domain-name OperaTor.com
 lease infinite
!
ip dhcp pool Network_21
 network 192.168.21.0 255.255.255.0
 default-router 192.168.21.1
 domain-name OperaTor.com
 lease infinite
!
ipv6 dhcp pool Stateless
 dns-server 2022:A304:20BF:1::1
 domain-name OperaTor.com
````
Применен DHCPv6 без отслеживания состояния IPv6 адреса хосты получат с использованием метода SLAAC.
На интерфейсах e0/2.21 и e0/3.20 в сторону принимающих хостов включаем в сообщение Router Advertisement флаг О равным 1, и выполняем привязку к пулу.
````
ipv6 nd other-config-flag
ipv6 dhcp server Stateless
````
Без демонстраций работы, по причине ошибки эмуляции VPC EVE-NG.

#### Настройка протокола OSPF.
Допустим маршрутизаторы R1,R2,R4,R5 находяться в Area 0 (backbone), а R3 и R4 находятся в тупиковой Area 1.
Запуск процесса OSPF производим на портах роутеров, идентификаторы роутеров назначены вручную и совпадают с IP адресами
интерфейсов Loopback0. Используем аутентификацию на основе хеша.

Настройки покажем на примере R1 и посмотрим состояние установленных соседств по OSPF, базу LSDB и таблицу маршрутов полученных по OSPF.

Настройки OSPF для порта e0/0 и e0/1 R1
````
interface Ethernet0/0
 description to_R6
 ip address 192.168.0.1 255.255.255.252
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 7 070C285F4D06
 ip ospf network point-to-point
 ip ospf 1 area 0
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::1:1:6/96
 ipv6 enable
 ipv6 ospf 1 area 0
!
interface Ethernet0/1
 description to_R3
 ip address 192.168.0.21 255.255.255.252
 ip ospf authentication message-digest
 ip ospf message-digest-key 1 md5 7 070C285F4D06
 ip ospf network point-to-point
 ip ospf 1 area 1
 ipv6 address FE80::1 link-local
 ipv6 address 2022:A304:20BF::6:1:3/96
 ipv6 enable
 ipv6 ospf 1 area 1
````
Настройки роутеров OSPF
````
router ospf 1
 router-id 192.168.1.1
 area 1 stub
!
ipv6 router ospf 1
 router-id 192.168.1.1
 area 1 stub
````
На интерфейсах R3 и R4 в сторону коммутаторов SW1 и SW2 так-же включим процесс OSPF, но настроены как passive (запрещаем отправку Hello пакетов OSPF).

Соседи R1 по OSPF.
````
R1#sh ip ospf nei

Neighbor ID     Pri   State           Dead Time   Address         Interface
192.168.10.5      0   FULL/  -        00:00:34    192.168.0.10    Ethernet1/0
192.168.1.2       0   FULL/  -        00:00:39    192.168.0.18    Ethernet0/2
192.168.10.6      0   FULL/  -        00:00:36    192.168.0.2     Ethernet0/0
192.168.1.4       0   FULL/  -        00:00:39    192.168.0.26    Ethernet1/1
192.168.1.3       0   FULL/  -        00:00:37    192.168.0.22    Ethernet0/1
R1#sh ipv6 ospf nei

            OSPFv3 Router with ID (192.168.1.1) (Process ID 1)

Neighbor ID     Pri   State           Dead Time   Interface ID    Interface
192.168.10.5      1   FULL/DR         00:00:34    7               Ethernet1/0
192.168.1.2       1   FULL/DR         00:00:33    5               Ethernet0/2
192.168.10.6      1   FULL/DR         00:00:39    3               Ethernet0/0
192.168.1.4       1   FULL/DR         00:00:39    7               Ethernet1/1
192.168.1.3       1   FULL/DR         00:00:33    3               Ethernet0/1
````
Состояние базы LSDB R1.
````
R1#sh ip ospf database

            OSPF Router with ID (192.168.1.1) (Process ID 1)

                Router Link States (Area 0)

Link ID         ADV Router      Age         Seq#       Checksum Link count
192.168.1.1     192.168.1.1     457         0x800000A4 0x005A59 7
192.168.1.2     192.168.1.2     444         0x800000A6 0x008717 7
192.168.10.5    192.168.10.5    482         0x8000004D 0x00020C 4
192.168.10.6    192.168.10.6    457         0x8000004D 0x0019F2 4

                Summary Net Link States (Area 0)

Link ID         ADV Router      Age         Seq#       Checksum
192.168.0.20    192.168.1.1     457         0x80000045 0x00BF49
192.168.0.20    192.168.1.2     443         0x80000005 0x009E9F
192.168.0.24    192.168.1.1     457         0x80000045 0x00976D
192.168.0.24    192.168.1.2     443         0x80000006 0x0074C4
192.168.0.28    192.168.1.1     457         0x80000006 0x0052E3
192.168.0.28    192.168.1.2     443         0x80000045 0x006996
192.168.0.32    192.168.1.1     457         0x80000005 0x002C07
192.168.0.32    192.168.1.2     443         0x80000045 0x0041BA
192.168.0.36    192.168.1.1     457         0x80000005 0x00042B
192.168.0.36    192.168.1.2     443         0x80000005 0x00FD30
192.168.1.3     192.168.1.1     959         0x80000004 0x00FD58
192.168.1.3     192.168.1.2     944         0x80000004 0x00F75D
192.168.1.4     192.168.1.1     959         0x80000004 0x00F361
192.168.1.4     192.168.1.2     944         0x80000004 0x00ED66
192.168.2.0     192.168.1.1     457         0x80000005 0x0069E4
192.168.2.0     192.168.1.2     443         0x80000005 0x0063E9
192.168.3.0     192.168.1.1     457         0x80000005 0x005EEE
192.168.3.0     192.168.1.2     443         0x80000005 0x0058F3
192.168.20.0    192.168.1.1     457         0x80000005 0x00A299
192.168.20.0    192.168.1.2     443         0x80000005 0x009C9E
192.168.21.0    192.168.1.1     457         0x80000005 0x0097A3
192.168.21.0    192.168.1.2     443         0x80000005 0x0091A8

                Router Link States (Area 1)

Link ID         ADV Router      Age         Seq#       Checksum Link count
192.168.1.1     192.168.1.1     457         0x80000047 0x00A547 4
192.168.1.2     192.168.1.2     444         0x80000048 0x006F5A 4
192.168.1.3     192.168.1.3     994         0x80000045 0x001455 11
192.168.1.4     192.168.1.4     975         0x8000003C 0x00B1DB 9

                Summary Net Link States (Area 1)

Link ID         ADV Router      Age         Seq#       Checksum
0.0.0.0         192.168.1.1     704         0x80000005 0x00903E
0.0.0.0         192.168.1.2     445         0x80000005 0x008A43
192.168.0.0     192.168.1.1     457         0x80000044 0x00A877
192.168.0.0     192.168.1.2     444         0x80000044 0x00070E
192.168.0.4     192.168.1.1     457         0x80000044 0x00E42D
192.168.0.4     192.168.1.2     444         0x80000044 0x007AA0
192.168.0.8     192.168.1.1     457         0x80000044 0x0058BF
192.168.0.8     192.168.1.2     444         0x80000044 0x00B656
192.168.0.12    192.168.1.1     457         0x80000044 0x009475
192.168.0.12    192.168.1.2     444         0x80000044 0x002AE8
192.168.0.16    192.168.1.1     457         0x80000044 0x000808
192.168.0.16    192.168.1.2     444         0x80000044 0x00020D
192.168.1.1     192.168.1.1     959         0x80000004 0x00CB98
192.168.1.1     192.168.1.2     945         0x80000004 0x002A2F
192.168.1.2     192.168.1.1     959         0x80000004 0x002633
192.168.1.2     192.168.1.2     945         0x80000004 0x00BBA6
````
````
R1#sh ipv6 ospf database

            OSPFv3 Router with ID (192.168.1.1) (Process ID 1)

                Router Link States (Area 0)

ADV Router       Age         Seq#        Fragment ID  Link count  Bits
 192.168.1.1     950         0x8000009F  0            3           B
 192.168.1.2     579         0x800000A0  0            3           B
 192.168.10.5    1497        0x8000004A  0            2           None
 192.168.10.6    1494        0x80000048  0            2           None

                Net Link States (Area 0)

ADV Router       Age         Seq#        Link ID    Rtr count
 192.168.1.2     579         0x80000043  5          2
 192.168.10.5    1761        0x80000044  3          2
 192.168.10.5    1497        0x80000043  7          2
 192.168.10.6    1494        0x80000043  3          2
 192.168.10.6    1995        0x80000044  7          2

                Inter Area Prefix Link States (Area 0)

ADV Router       Age         Seq#        Prefix
 192.168.1.1     950         0x80000043  2022:A304:20BF::7:0:0/96
 192.168.1.1     950         0x80000043  2022:A304:20BF::6:0:0/96
 192.168.1.1     1696        0x80000004  2022:A304:20BF:20::/64
 192.168.1.1     1696        0x80000004  2022:A304:20BF::A:0:0/96
 192.168.1.1     1696        0x80000004  2022:A304:20BF::8:0:0/96
 192.168.1.1     1454        0x80000005  2022:A304:20BF::9:0:0/96
 192.168.1.1     1454        0x80000004  2022:A304:20BF:21::/64
 192.168.1.2     579         0x80000046  2022:A304:20BF::9:0:0/96
 192.168.1.2     579         0x80000046  2022:A304:20BF::8:0:0/96
 192.168.1.2     339         0x80000032  2022:A304:20BF::7:0:0/96
 192.168.1.2     1336        0x80000033  2022:A304:20BF::6:0:0/96
 192.168.1.2     1846        0x80000031  2022:A304:20BF::A:0:0/96
 192.168.1.2     1336        0x80000005  2022:A304:20BF:21::/64
 192.168.1.2     1336        0x80000004  2022:A304:20BF:20::/64

                Link (Type-8) Link States (Area 0)

ADV Router       Age         Seq#        Link ID    Interface
 192.168.1.1     950         0x80000046  7          Et1/0
 192.168.10.5    1761        0x80000045  7          Et1/0
 192.168.1.1     950         0x80000044  5          Et0/2
 192.168.1.2     579         0x80000044  5          Et0/2
 192.168.1.1     950         0x80000046  3          Et0/0
 192.168.10.6    1751        0x80000045  3          Et0/0

                Intra Area Prefix Link States (Area 0)

ADV Router       Age         Seq#        Link ID    Ref-lstype  Ref-LSID
 192.168.1.2     579         0x80000043  5120       0x2002      5
 192.168.10.5    1761        0x80000044  3072       0x2002      3
 192.168.10.5    1497        0x80000043  7168       0x2002      7
 192.168.10.6    1494        0x80000043  3072       0x2002      3
 192.168.10.6    1995        0x80000044  7168       0x2002      7

                Router Link States (Area 1)

ADV Router       Age         Seq#        Fragment ID  Link count  Bits
 192.168.1.1     1454        0x80000048  0            2           B
 192.168.1.2     1337        0x80000048  0            2           B
 192.168.1.3     1152        0x8000003B  0            4           None
 192.168.1.4     1315        0x80000034  0            4           None

                Net Link States (Area 1)

ADV Router       Age         Seq#        Link ID    Rtr count
 192.168.1.3     1397        0x80000004  3          2
 192.168.1.3     1397        0x80000004  7          2
 192.168.1.4     1566        0x80000004  3          2
 192.168.1.4     1566        0x80000004  4          2
 192.168.1.4     1566        0x80000004  7          2
 192.168.1.4     1566        0x80000009  15         2

                Inter Area Prefix Link States (Area 1)

ADV Router       Age         Seq#        Prefix
 192.168.1.1     950         0x80000043  2022:A304:20BF::5:0:0/96
 192.168.1.1     950         0x80000043  2022:A304:20BF::4:0:0/96
 192.168.1.1     950         0x80000043  2022:A304:20BF::1:0:0/96
 192.168.1.1     950         0x80000043  2022:A304:20BF::3:0:0/96
 192.168.1.1     950         0x80000043  2022:A304:20BF::2:0:0/96
 192.168.1.1     1696        0x80000004  ::/0
 192.168.1.2     580         0x80000043  2022:A304:20BF::5:0:0/96
 192.168.1.2     580         0x80000043  2022:A304:20BF::4:0:0/96
 192.168.1.2     580         0x80000043  2022:A304:20BF::1:0:0/96
 192.168.1.2     580         0x80000043  2022:A304:20BF::3:0:0/96
 192.168.1.2     580         0x80000043  2022:A304:20BF::2:0:0/96
 192.168.1.2     1599        0x80000004  ::/0

                Link (Type-8) Link States (Area 1)

ADV Router       Age         Seq#        Link ID    Interface
 192.168.1.1     1696        0x80000044  8          Et1/1
 192.168.1.4     1566        0x8000002D  7          Et1/1
 192.168.1.1     1696        0x80000044  4          Et0/1
 192.168.1.3     1397        0x80000032  3          Et0/1

                Intra Area Prefix Link States (Area 1)

ADV Router       Age         Seq#        Link ID    Ref-lstype  Ref-LSID
 192.168.1.3     1152        0x80000042  0          0x2001      0
 192.168.1.3     1397        0x80000004  3072       0x2002      3
 192.168.1.3     1397        0x80000004  7168       0x2002      7
 192.168.1.4     1566        0x80000004  3072       0x2002      3
 192.168.1.4     1566        0x80000004  4096       0x2002      4
 192.168.1.4     1566        0x80000004  7168       0x2002      7
 192.168.1.4     1566        0x80000009  15360      0x2002      15
R1#
````
Ну и на последок, все ради чего настраивали протокол OSPF, состояние таблицы маршрутизации с выводом только маррутов полученных по OSPF для R1.
````
R1# sh ip route ospf
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route, H - NHRP, l - LISP
       a - application route
       + - replicated route, % - next hop override

Gateway of last resort is not set

      192.168.0.0/24 is variably subnetted, 15 subnets, 2 masks
O        192.168.0.4/30 [110/20] via 192.168.0.18, 02:51:56, Ethernet0/2
                        [110/20] via 192.168.0.10, 02:51:56, Ethernet1/0
O        192.168.0.12/30 [110/20] via 192.168.0.18, 02:51:56, Ethernet0/2
                         [110/20] via 192.168.0.2, 02:51:56, Ethernet0/0
O        192.168.0.28/30 [110/20] via 192.168.0.26, 02:48:13, Ethernet1/1
O        192.168.0.32/30 [110/20] via 192.168.0.22, 02:48:56, Ethernet0/1
O        192.168.0.36/30 [110/20] via 192.168.0.26, 02:48:13, Ethernet1/1
                         [110/20] via 192.168.0.22, 02:48:56, Ethernet0/1
      192.168.1.0/32 is subnetted, 4 subnets
O        192.168.1.2 [110/11] via 192.168.0.18, 02:24:11, Ethernet0/2
O        192.168.1.3 [110/11] via 192.168.0.22, 02:22:38, Ethernet0/1
O        192.168.1.4 [110/11] via 192.168.0.26, 02:22:55, Ethernet1/1
O     192.168.2.0/24 [110/20] via 192.168.0.22, 02:48:56, Ethernet0/1
O     192.168.3.0/24 [110/20] via 192.168.0.26, 02:48:13, Ethernet1/1
                     [110/20] via 192.168.0.22, 02:48:56, Ethernet0/1
O     192.168.20.0/24 [110/20] via 192.168.0.26, 02:48:13, Ethernet1/1
                      [110/20] via 192.168.0.22, 02:48:56, Ethernet0/1
O     192.168.21.0/24 [110/20] via 192.168.0.22, 02:48:56, Ethernet0/1
R1# sh ipv6 route ospf
IPv6 Routing Table - default - 21 entries
Codes: C - Connected, L - Local, S - Static, U - Per-user Static route
       B - BGP, HA - Home Agent, MR - Mobile Router, R - RIP
       H - NHRP, I1 - ISIS L1, I2 - ISIS L2, IA - ISIS interarea
       IS - ISIS summary, D - EIGRP, EX - EIGRP external, NM - NEMO
       ND - ND Default, NDp - ND Prefix, DCE - Destination, NDr - Redirect
       O - OSPF Intra, OI - OSPF Inter, OE1 - OSPF ext 1, OE2 - OSPF ext 2
       ON1 - OSPF NSSA ext 1, ON2 - OSPF NSSA ext 2, la - LISP alt
       lr - LISP site-registrations, ld - LISP dyn-eid, a - Application
O   2022:A304:20BF::2:0:0/96 [110/20]
     via FE80::5, Ethernet1/0
     via FE80::2, Ethernet0/2
O   2022:A304:20BF::4:0:0/96 [110/20]
     via FE80::6, Ethernet0/0
     via FE80::2, Ethernet0/2
O   2022:A304:20BF::8:0:0/96 [110/20]
     via FE80::4, Ethernet1/1
O   2022:A304:20BF::9:0:0/96 [110/20]
     via FE80::3, Ethernet0/1
O   2022:A304:20BF::A:0:0/96 [110/20]
     via FE80::4, Ethernet1/1
     via FE80::3, Ethernet0/1
O   2022:A304:20BF:20::/64 [110/20]
     via FE80::4, Ethernet1/1
     via FE80::3, Ethernet0/1
O   2022:A304:20BF:21::/64 [110/20]
     via FE80::3, Ethernet0/1
R1#
````
#### На роутерах R1 и R2 настроим маршруты по-умолчанию в сторону ISP.

Создаем статические маршруты для R1
````
ip route 0.0.0.0 0.0.0.0 99.13.77.1
!
ipv6 route ::/0 2022:A304:20BF::2
````
Для R2 аналогично
````
ip route 0.0.0.0 0.0.0.0 110.1.22.9
!
ipv6 route ::/0 2022:ABCC:318:8::36
````


#### Настройка EIGRP на сети ISP2 в именованном режиме.
Все маршрутизаторы находятся в одной автономной системе EIGRP, router-id назначены вручную и соотвествуют IP адресу 
интерфейсов Loopback0.

Покажем настройку на примере R31.
Сначала создаем цепочку ключей, настроил так, что имеется один ключ без ограничения по времени.
````
key chain EIGRP
 key 1
  key-string 7 01100F175804
  cryptographic-algorithm hmac-sha-256
````
Настройка EIGRP
````
router eigrp ISP2
 !
 address-family ipv4 unicast autonomous-system 1
  !
  af-interface Ethernet0/0
   authentication mode hmac-sha-256 7 1511021F0725
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  af-interface Ethernet0/1
   authentication mode hmac-sha-256 7 05080F1C2243
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  af-interface Ethernet0/2
   authentication mode hmac-sha-256 7 00071A150754
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  af-interface Ethernet1/0
   authentication mode hmac-sha-256 7 13061E010803
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  topology base
  exit-af-topology
  network 10.10.0.0 0.0.0.255
  network 10.10.8.31 0.0.0.0
  eigrp router-id 10.10.8.31
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 1
  !
  af-interface Ethernet0/0
   authentication mode hmac-sha-256 7 1511021F0725
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  af-interface Ethernet0/1
   authentication mode hmac-sha-256 7 0822455D0A16
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  af-interface Ethernet0/2
   authentication mode hmac-sha-256 7 121A0C041104
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  af-interface Ethernet1/0
   authentication mode hmac-sha-256 7 094F471A1A0A
   authentication key-chain EIGRP
   bandwidth-percent 40
  exit-af-interface
  !
  topology base
  exit-af-topology
  eigrp router-id 10.10.8.31
 exit-address-family
!
````
Суммаризацию маршрутов не использовалась.

Результаты настройки покажем на примере установленных соседств EIGRP на R31.
````
R31#sh ip eigrp neighbors
EIGRP-IPv4 VR(ISP2) Address-Family Neighbors for AS(1)
H   Address                 Interface              Hold Uptime   SRTT   RTO  Q  Seq
                                                   (sec)         (ms)       Cnt Num
2   10.10.0.10              Et1/0                    14 14:12:26    5   100  0  35
3   10.10.0.26              Et0/2                    12 14:14:49    6   100  0  13
1   10.10.0.2               Et0/0                    13 14:51:54    3   100  0  33
0   10.10.0.6               Et0/1                    13 15:04:29    1   100  0  46
R31#sh ipv6 eigrp neighbors
EIGRP-IPv6 VR(ISP2) Address-Family Neighbors for AS(1)
H   Address                 Interface              Hold Uptime   SRTT   RTO  Q  Seq
                                                   (sec)         (ms)       Cnt Num
3   Link-local address:     Et0/2                    11 14:14:57    7   100  0  10
    FE80::35
2   Link-local address:     Et1/0                    13 14:29:04    4   100  0  21
    FE80::34
1   Link-local address:     Et0/0                    10 14:52:01    2   100  0  24
    FE80::33
0   Link-local address:     Et0/1                    14 15:04:37    5   100  0  30
    FE80::32
R31#
````
Полученные на R31 маршруты по по EIGRP.
````
R31#sh ip route eigrp
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route, H - NHRP, l - LISP
       a - application route
       + - replicated route, % - next hop override

Gateway of last resort is not set

      10.0.0.0/8 is variably subnetted, 22 subnets, 2 masks
D        10.10.0.12/30 [90/1536000] via 10.10.0.10, 14:14:13, Ethernet1/0
                       [90/1536000] via 10.10.0.6, 14:14:13, Ethernet0/1
D        10.10.0.16/30 [90/1536000] via 10.10.0.6, 14:14:11, Ethernet0/1
                       [90/1536000] via 10.10.0.2, 14:14:11, Ethernet0/0
D        10.10.0.20/30 [90/1536000] via 10.10.0.10, 14:14:11, Ethernet1/0
                       [90/1536000] via 10.10.0.2, 14:14:11, Ethernet0/0
D        10.10.0.28/30 [90/1536000] via 10.10.0.26, 13:44:56, Ethernet0/2
D        10.10.0.32/30 [90/1536000] via 10.10.0.6, 13:44:56, Ethernet0/1
D        10.10.0.36/30 [90/1536000] via 10.10.0.2, 14:14:12, Ethernet0/0
D        10.10.0.40/30 [90/1536000] via 10.10.0.10, 14:14:11, Ethernet1/0
D        10.10.8.32/32 [90/1024640] via 10.10.0.6, 14:14:11, Ethernet0/1
D        10.10.8.33/32 [90/1024640] via 10.10.0.2, 14:08:54, Ethernet0/0
D        10.10.8.34/32 [90/1024640] via 10.10.0.10, 14:14:11, Ethernet1/0
D        10.10.8.35/32 [90/1024640] via 10.10.0.26, 14:16:34, Ethernet0/2
D        10.10.8.36/32 [90/1536640] via 10.10.0.26, 13:44:56, Ethernet0/2
                       [90/1536640] via 10.10.0.6, 13:44:56, Ethernet0/1
D        10.10.8.37/32 [90/1536640] via 10.10.0.10, 13:41:59, Ethernet1/0
                       [90/1536640] via 10.10.0.2, 13:41:59, Ethernet0/0
R31# sh ipv6 route eigrp
IPv6 Routing Table - default - 25 entries
Codes: C - Connected, L - Local, S - Static, U - Per-user Static route
       B - BGP, HA - Home Agent, MR - Mobile Router, R - RIP
       H - NHRP, I1 - ISIS L1, I2 - ISIS L2, IA - ISIS interarea
       IS - ISIS summary, D - EIGRP, EX - EIGRP external, NM - NEMO
       ND - ND Default, NDp - ND Prefix, DCE - Destination, NDr - Redirect
       O - OSPF Intra, OI - OSPF Inter, OE1 - OSPF ext 1, OE2 - OSPF ext 2
       ON1 - OSPF NSSA ext 1, ON2 - OSPF NSSA ext 2, la - LISP alt
       lr - LISP site-registrations, ld - LISP dyn-eid, a - Application
D   2022:A304:11AA:1::1:0/112 [90/1536000]
     via FE80::35, Ethernet0/2
D   2022:ABCC:318:1:0:3::/96 [90/1536000]
     via FE80::32, Ethernet0/1
     via FE80::34, Ethernet1/0
D   2022:ABCC:318:1:0:4::/96 [90/1536000]
     via FE80::32, Ethernet0/1
     via FE80::33, Ethernet0/0
D   2022:ABCC:318:1:0:5::/96 [90/1536000]
     via FE80::33, Ethernet0/0
     via FE80::34, Ethernet1/0
D   2022:ABCC:318:1:0:7::/96 [90/1536000]
     via FE80::35, Ethernet0/2
D   2022:ABCC:318:1:0:8::/96 [90/1536000]
     via FE80::32, Ethernet0/1
D   2022:ABCC:318:1:0:9::/96 [90/1536000]
     via FE80::33, Ethernet0/0
D   2022:ABCC:318:1:0:A::/96 [90/1536000]
     via FE80::34, Ethernet1/0
D   2022:ABCC:318:8::32/128 [90/1024640]
     via FE80::32, Ethernet0/1
D   2022:ABCC:318:8::33/128 [90/1024640]
     via FE80::32, Ethernet0/1
     via FE80::33, Ethernet0/0
D   2022:ABCC:318:8::34/128 [90/1024640]
     via FE80::34, Ethernet1/0
D   2022:ABCC:318:8::35/128 [90/1024640]
     via FE80::35, Ethernet0/2
D   2022:ABCC:318:8::36/128 [90/1536640]
     via FE80::35, Ethernet0/2
     via FE80::32, Ethernet0/1
D   2022:ABCC:318:8::37/128 [90/1536640]
     via FE80::33, Ethernet0/0
     via FE80::34, Ethernet1/0
D   2022:ABCC:318:ABAB:18::/112 [90/2048000]
     via FE80::35, Ethernet0/2
     via FE80::32, Ethernet0/1
R31#
````
#### Настроить eBGP между оператором и ISP, а так-же между ISP1 и ISP2.
Конфигурацию покажем на примере R1 и R2 оператора.
````
````