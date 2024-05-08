## Проектная работа
## Построение сети оператора по предоставлению IP транзитных услуг

Постановка целей:

1. Повторение пройденных материалов и закрепление навыков.
2. Самостоятельно изучить принципы работы сетей с использованием технологии MPLS-TE.

Задачи:

#### Часть 1.

1. [Разработать схему лабораторного стенда, задокументировать адресное пространство.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#1-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-%D1%81%D1%85%D0%B5%D0%BC%D1%83-%D0%BB%D0%B0%D0%B1%D0%BE%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D1%81%D1%82%D0%B5%D0%BD%D0%B4%D0%B0-%D0%B7%D0%B0%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%BD%D0%BE%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D1%81%D1%82%D0%B2%D0%BE)
2. [Для всех сетевых элементов выполнить первичные настройки, интерфейсам присвоить IP адреса.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#2-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%81%D0%B5%D1%85-%D1%81%D0%B5%D1%82%D0%B5%D0%B2%D1%8B%D1%85-%D1%8D%D0%BB%D0%B5%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D1%8C-%D0%BF%D0%B5%D1%80%D0%B2%D0%B8%D1%87%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D0%B0%D0%BC-%D0%BF%D1%80%D0%B8%D1%81%D0%B2%D0%BE%D0%B8%D1%82%D1%8C-ip-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0)
3. [Настроить сеть офиса оператора](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#3-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D1%81%D0%B5%D1%82%D1%8C-%D0%BE%D1%84%D0%B8%D1%81%D0%B0-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
- Настроить коммутаторы SW1 и SW2
- Настроить протокол GLBP на R3 и R4
- Настройка DHCP сервера на R3 и R4
- Настроить протокол OSPF
- На R1 и R2 настроить маршруты по-умолчанию.
4. [Настроить EIGRP на сети провайдера ISP2.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#4-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-eigrp-%D0%BD%D0%B0-%D1%81%D0%B5%D1%82%D0%B8-isp2-%D0%B2-%D0%B8%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%BC-%D1%80%D0%B5%D0%B6%D0%B8%D0%BC%D0%B5)
5. [Настроить eBGP между оператором и ISP, а так-же между ISP1 и ISP2.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-ebgp-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%BC-%D0%B8-isp-%D0%B0-%D1%82%D0%B0%D0%BA-%D0%B6%D0%B5-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-isp1-%D0%B8-isp2)
6. [Настроить iBGP между R1 и R2 в сети офиса оператора](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#6-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-ibgp-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-r1-%D0%B8-r2-%D0%B2-%D1%81%D0%B5%D1%82%D0%B8-%D0%BE%D1%84%D0%B8%D1%81%D0%B0-%D0%BE%D1%80%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
7. [Настроить iBGP в сети ISP2 с разбиением на 2-а кластера с двумя RR в каждой.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#7-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-ibgp-%D0%B2-%D1%81%D0%B5%D1%82%D0%B8-isp2-%D1%81-%D1%80%D0%B0%D0%B7%D0%B1%D0%B8%D0%B5%D0%BD%D0%B8%D0%B5%D0%BC-%D0%BD%D0%B0-2-%D0%B0-%D0%BA%D0%BB%D0%B0%D1%81%D1%82%D0%B5%D1%80%D0%B0-%D1%81-%D0%B4%D0%B2%D1%83%D0%BC%D1%8F-rr-%D0%B2-%D0%BA%D0%B0%D0%B6%D0%B4%D0%BE%D0%B9)
8. [Манипуляция с атрибутами BGP в сети офиса оператора.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#8-%D0%BC%D0%B0%D0%BD%D0%B8%D0%BF%D1%83%D0%BB%D1%8F%D1%86%D0%B8%D1%8F-%D1%81-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B0%D0%BC%D0%B8-bgp-%D0%B2-%D1%81%D0%B5%D1%82%D0%B8-%D0%BE%D1%84%D0%B8%D1%81%D0%B0-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
9. [Настроить NAT на R1 и R2 в сети оператора](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#9-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-nat-%D0%BD%D0%B0-r1-%D0%B8-r2-%D0%B2-%D1%81%D0%B5%D1%82%D0%B8-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%B0)

#### Часть 2.

10. [Настроить протокол динамической маршрутизации IS-IS в MPLS сегменте сети провайдера.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#10-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB-%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B9-%D0%BC%D0%B0%D1%80%D1%88%D1%80%D1%83%D1%82%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-is-is-%D0%B2-mpls-%D1%81%D0%B5%D0%B3%D0%BC%D0%B5%D0%BD%D1%82%D0%B5-%D1%81%D0%B5%D1%82%D0%B8-%D0%BF%D1%80%D0%BE%D0%B2%D0%B0%D0%B9%D0%B4%D0%B5%D1%80%D0%B0)
11. [Настроить MPLS-TE на всех маршрутизаторах сегмента MPLS оператора.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#11-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-mpls-te-%D0%BD%D0%B0-%D0%B2%D1%81%D0%B5%D1%85-%D0%BC%D0%B0%D1%80%D1%88%D1%80%D1%83%D1%82%D0%B8%D0%B7%D0%B0%D1%82%D0%BE%D1%80%D0%B0%D1%85-%D1%81%D0%B5%D0%B3%D0%BC%D0%B5%D0%BD%D1%82%D0%B0-mpls-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
12. [Построение динамического туннеля.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/Project/Readme.md#11-%D0%BF%D0%BE%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B3%D0%BE-%D1%82%D1%83%D0%BD%D0%BD%D0%B5%D0%BB%D1%8F)
13. [Приоритизация туннелей]()
14. [Управление туннелями]()
15. [Построение защитных туннелей.]()
16. [Построить L3VPN в туннеле MPLS-TE.]()

#### 1. Разработать схему лабораторного стенда, задокументировать адресное пространство.

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
|          | R7       | e0/0      | to_R5       | 192.168.11.2  | 255.255.255.252 |             |                               |           |                     |
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




#### 2. Для всех сетевых элементов выполнить первичные настройки, интерфейсам присвоить IP адреса.
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
#### 3. Настроить сеть офиса оператора.

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


#### 4. Настройка EIGRP на сети ISP2 в именованном режиме.
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
#### 5. Настроить eBGP между оператором и ISP, а так-же между ISP1 и ISP2.
Конфигурацию покажем на примере R1 и R2 оператора.

R1 в сторону ISP 
```
R1#sh run | sec bgp
router bgp 1000
 bgp router-id 192.168.1.1
 bgp log-neighbor-changes
 neighbor 2022:A304:20BF::2 remote-as 120
 neighbor 99.13.77.1 remote-as 120
 !
 address-family ipv4
  network 99.13.77.0 mask 255.255.255.0
  no neighbor 2022:A304:20BF::2 activate
  neighbor 99.13.77.1 activate
 exit-address-family
 !
 address-family ipv6
  network 22:A304:20BF::/48
  neighbor 2022:A304:20BF::2 activate
 exit-address-family
R1#
````
R2 в сторону ISP2
````
R2#sh run | sec bgp
router bgp 1000
 bgp router-id 192.168.1.2
 bgp log-neighbor-changes
 neighbor 2022:ABCC:318:ABAB:18::40 remote-as 100
 neighbor 110.1.22.9 remote-as 100
 !
 address-family ipv4
  network 99.13.77.0 mask 255.255.255.0
  no neighbor 2022:ABCC:318:ABAB:18::40 activate
  neighbor 110.1.22.9 activate
 exit-address-family
 !
 address-family ipv6
  network 22:A304:20BF::/48
  neighbor 2022:ABCC:318:ABAB:18::40 activate
 exit-address-family
R2#
````
Покажем установление соседства на настроенном R1 по протоколу BGP.
````
R1#sh ip bgp nei
BGP neighbor is 99.13.77.1,  remote AS 120, external link
  BGP version 4, remote router ID 10.10.10.14
  BGP state = Established, up for 03:45:12
  Last read 00:00:40, last write 00:00:17, hold time is 180, keepalive interval is 60 seconds
  Neighbor sessions:
    1 active, is not multisession capable (disabled)
  Neighbor capabilities:
    Route refresh: advertised and received(new)
    Four-octets ASN Capability: advertised and received
    Address family IPv4 Unicast: advertised and received
    Enhanced Refresh Capability: advertised and received
    Multisession Capability:
    Stateful switchover support enabled: NO for session 1
  Message statistics:
    InQ depth is 0
    OutQ depth is 0

                         Sent       Rcvd
    Opens:                  1          1
    Notifications:          0          0
    Updates:                1          1
    Keepalives:           250        250
    Route Refresh:          0          0
    Total:                252        252
  Default minimum time between advertisement runs is 30 seconds

 For address family: IPv4 Unicast
  Session: 99.13.77.1
  BGP table version 1, neighbor version 1/0
  Output queue size : 0
  Index 1, Advertise bit 0
  1 update-group member
  Slow-peer detection is disabled
  Slow-peer split-update-group dynamic is disabled
  Interface associated: Ethernet0/3
                                 Sent       Rcvd
  Prefix activity:               ----       ----
    Prefixes Current:               0          0
    Prefixes Total:                 0          0
    Implicit Withdraw:              0          0
    Explicit Withdraw:              0          0
    Used as bestpath:             n/a          0
    Used as multipath:            n/a          0

                                   Outbound    Inbound
  Local Policy Denied Prefixes:    --------    -------
    Total:                                0          0
  Number of NLRIs in the update sent: max 0, min 0
  Last detected as dynamic slow peer: never
  Dynamic slow peer recovered: never
  Refresh Epoch: 1
  Last Sent Refresh Start-of-rib: never
  Last Sent Refresh End-of-rib: never
  Last Received Refresh Start-of-rib: never
  Last Received Refresh End-of-rib: never
                                       Sent       Rcvd
        Refresh activity:              ----       ----
          Refresh Start-of-RIB          0          0
          Refresh End-of-RIB            0          0

  Address tracking is enabled, the RIB does have a route to 99.13.77.1
  Connections established 1; dropped 0
  Last reset never
  Transport(tcp) path-mtu-discovery is enabled
  Graceful-Restart is disabled
Connection state is ESTAB, I/O status: 1, unread input bytes: 0
Connection is ECN Disabled, Mininum incoming TTL 0, Outgoing TTL 1
Local host: 99.13.77.0, Local port: 16570
Foreign host: 99.13.77.1, Foreign port: 179
Connection tableid (VRF): 0
Maximum output segment queue size: 50

Enqueued packets for retransmit: 0, input: 0  mis-ordered: 0 (0 bytes)

Event Timers (current time is 0xDDCCB78):
Timer          Starts    Wakeups            Next
Retrans           252          0             0x0
TimeWait            0          0             0x0
AckHold           251        245             0x0
SendWnd             0          0             0x0
KeepAlive           0          0             0x0
GiveUp              0          0             0x0
PmtuAger        12541      12540       0xDDCCD01
DeadWait            0          0             0x0
Linger              0          0             0x0
ProcessQ            0          0             0x0

iss: 3268355561  snduna: 3268360392  sndnxt: 3268360392
irs: 1575082409  rcvnxt: 1575087240

sndwnd:  15947  scale:      0  maxrcvwnd:  16384
rcvwnd:  15947  scale:      0  delrcvwnd:    437

SRTT: 1000 ms, RTTO: 1003 ms, RTV: 3 ms, KRTT: 0 ms
minRTT: 1 ms, maxRTT: 1000 ms, ACK hold: 200 ms
uptime: 13512467 ms, Sent idletime: 17447 ms, Receive idletime: 17242 ms
Status Flags: active open
Option Flags: nagle, path mtu capable
IP Precedence value : 6

Datagrams (max data segment is 1460 bytes):
Rcvd: 503 (out of order: 0), with data: 252, total data bytes: 4830
Sent: 504 (retransmit: 0, fastretransmit: 0, partialack: 0, Second Congestion: 0), with data: 252, total data bytes: 4830

 Packets received in fast path: 0, fast processed: 0, slow path: 0
 fast lock acquisition failures: 0, slow path: 0
TCP Semaphore      0xE380DAB4  FREE

R1#
````
Проверим маршруты в таблице BGP R1 полученные от R14. Но до этого создадим интерфейсы Loopback 1 и статические машруты
на обоих роутерах, в противном случае при отсутствии маршрута к этой сети таблица BGP будут пустыми.
Через интерфейсы Loopback1 будем проверять IP связанность. Настройка на примере R1.

Так на R14 ISP1 настроим интерфейс Loopback1 и создадим статический маршрут в сеть провайдера ISP1.
````
!
interface Loopback1
 ip address 135.200.13.8 255.255.255.255
 ipv6 address 2022:A304:11AA::8888/128
!
ip route 135.200.13.0 255.255.255.0 Null0
!
ipv6 route 2022:A304:11AA::/48 Null0
````
На R37 в сети ISP2
````
interface Loopback1
 ip address 110.1.22.8 255.255.255.0
 ipv6 address 2022:ABCC:318::8888/128
!
ip route 110.1.22.0 255.255.255.0 Null0
!
ipv6 route 2022:ABCC:318::/48 Null0
````
а так-же распространим информацию об интерфейсе Loopback1 по EIGRP
````
R37(config)#router eigrp ISP2
R37(config-router)#address-family ipv4 unicast autonomous-system 1
R37(config-router-af)#
R37(config-router-af)#network 110.1.22.8 0.0.0.0
````
Покажем маршруты IPv4 BGP добавленные в таблицу маршрутизации BGP

для R1
````
R1#sh ip route bgp
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route, H - NHRP, l - LISP
       a - application route
       + - replicated route, % - next hop override

Gateway of last resort is 99.13.77.1 to network 0.0.0.0

      110.0.0.0/24 is subnetted, 1 subnets
B        110.1.22.0 [20/0] via 99.13.77.1, 01:30:28
      135.200.0.0/24 is subnetted, 1 subnets
B        135.200.13.0 [20/0] via 99.13.77.1, 02:34:54
R1#
````
и для R2
````
R2#sh ip bgp
BGP table version is 2, local router ID is 192.168.1.2
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 *>  110.1.22.0/24    110.1.22.9         2048640             0 100 i
R2#
````
Видим, что на R1 получены маршруты в сети ISP1 и ISP2 в то время как на R2 только в сеть ISP2. 
Маршрут в сеть ISP2 появится если настроим протокол iBGP на сети ISP2 ну или на сети оператора.

#### 6. Настроить iBGP между R1 и R2 в сети офиса орератора.

В качестве интерфейсов для установления соседства по BGP использовать TCP сессию установленную между интерфейсами Loopback0
роутеров R1 и R2. Виртуальный сетевой интерфейс будет доступен всегда, а надежность связанности между Loopback интерфейсами R1 и R2
обеспечивается избыточностью связей Backbone Area0 OSPF.

Настройка на примере R1
````
R1(config)#router bgp 1000
R1(config-router)#neighbor 192.168.1.2 remote-as 1000
R1(config-router)#neighbor 192.168.1.2 update-source loopback 0
R1(config-router)#neighbor 2022:A304:20BF:8::2 remote-as 1000
R1(config-router)# neighbor 2022:A304:20BF:8::2 update-source loopback 0
R1(config-router)#address-family ipv4
R1(config-router-af)#neighbor 192.168.1.2 next-hop-self
R1(config-router-af)#address-family ipv6
R1(config-router-af)#neighbor 2022:A304:20BF:8::2 activate
R1(config-router-af)#neighbor 2022:A304:20BF:8::2 next-hop-self
````
Отобразим на R2 установленное соседство по iBGP с R1
````
R2#sh ip bgp nei 192.168.1.1
BGP neighbor is 192.168.1.1,  remote AS 1000, internal link
  BGP version 4, remote router ID 192.168.1.1
  BGP state = Established, up for 00:07:54
  Last read 00:00:45, last write 00:00:16, hold time is 180, keepalive interval is 60 seconds
  Neighbor sessions:
    1 active, is not multisession capable (disabled)
  Neighbor capabilities:
    Route refresh: advertised and received(new)
    Four-octets ASN Capability: advertised and received
    Address family IPv4 Unicast: advertised and received
    Enhanced Refresh Capability: advertised and received
    Multisession Capability:
    Stateful switchover support enabled: NO for session 1
  Message statistics:
    InQ depth is 0
    OutQ depth is 0

                         Sent       Rcvd
    Opens:                  1          1
    Notifications:          0          0
    Updates:                4          4
    Keepalives:            10         10
    Route Refresh:          0          0
    Total:                 15         15
  Default minimum time between advertisement runs is 0 seconds

 For address family: IPv4 Unicast
  Session: 192.168.1.1
  BGP table version 3, neighbor version 3/0
  Output queue size : 0
  Index 3, Advertise bit 1
  3 update-group member
  NEXT_HOP is always this router for eBGP paths
  Slow-peer detection is disabled
  Slow-peer split-update-group dynamic is disabled
  Interface associated: (none)
                                 Sent       Rcvd
  Prefix activity:               ----       ----
    Prefixes Current:               1          1 (Consumes 80 bytes)
    Prefixes Total:                 1          2
    Implicit Withdraw:              0          0
    Explicit Withdraw:              1          1
    Used as bestpath:             n/a          1
    Used as multipath:            n/a          0

                                   Outbound    Inbound
  Local Policy Denied Prefixes:    --------    -------
    Bestpath from this peer:              1        n/a
    Total:                                1          0
  Number of NLRIs in the update sent: max 1, min 0
  Last detected as dynamic slow peer: never
  Dynamic slow peer recovered: never
  Refresh Epoch: 1
  Last Sent Refresh Start-of-rib: never
  Last Sent Refresh End-of-rib: never
  Last Received Refresh Start-of-rib: never
  Last Received Refresh End-of-rib: never
                                       Sent       Rcvd
        Refresh activity:              ----       ----
          Refresh Start-of-RIB          0          0
          Refresh End-of-RIB            0          0

  Address tracking is enabled, the RIB does have a route to 192.168.1.1
  Connections established 1; dropped 0
  Last reset never
  Transport(tcp) path-mtu-discovery is enabled
  Graceful-Restart is disabled
Connection state is ESTAB, I/O status: 1, unread input bytes: 0
Connection is ECN Disabled, Mininum incoming TTL 0, Outgoing TTL 255
Local host: 192.168.1.2, Local port: 179
Foreign host: 192.168.1.1, Foreign port: 25314
Connection tableid (VRF): 0
Maximum output segment queue size: 50

Enqueued packets for retransmit: 0, input: 0  mis-ordered: 0 (0 bytes)

Event Timers (current time is 0xEAE2D09):
Timer          Starts    Wakeups            Next
Retrans            12          0             0x0
TimeWait            0          0             0x0
AckHold            12          9             0x0
SendWnd             0          0             0x0
KeepAlive           0          0             0x0
GiveUp              0          0             0x0
PmtuAger            0          0             0x0
DeadWait            0          0             0x0
Linger              0          0             0x0
ProcessQ            0          0             0x0

iss: 3747984438  snduna: 3747984858  sndnxt: 3747984858
irs: 3581405056  rcvnxt: 3581405480

sndwnd:  15965  scale:      0  maxrcvwnd:  16384
rcvwnd:  15961  scale:      0  delrcvwnd:    423

SRTT: 798 ms, RTTO: 2221 ms, RTV: 1423 ms, KRTT: 0 ms
minRTT: 0 ms, maxRTT: 1000 ms, ACK hold: 200 ms
uptime: 474177 ms, Sent idletime: 16130 ms, Receive idletime: 15922 ms
Status Flags: passive open, gen tcbs
Option Flags: nagle, path mtu capable
IP Precedence value : 6

Datagrams (max data segment is 1460 bytes):
Rcvd: 26 (out of order: 0), with data: 13, total data bytes: 423
Sent: 25 (retransmit: 0, fastretransmit: 0, partialack: 0, Second Congestion: 0), with data: 13, total data bytes: 419

 Packets received in fast path: 0, fast processed: 0, slow path: 0
 fast lock acquisition failures: 0, slow path: 0
TCP Semaphore      0xE3E512DC  FREE
````
Ограничимся демонстрацией таблицы BGP на R2
````
R2# sh ip bgp
BGP table version is 3, local router ID is 192.168.1.2
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 *>  110.1.22.0/24    110.1.22.9         2048640             0 100 i
 *>i 135.200.13.0/24  192.168.1.1              0    100      0 120 i
R2#
````
А вот и обещанный маршрут в сторону ISP1, только полученный со стороны R1 по iBGP.

#### 7. Настроить iBGP в сети ISP2 с разбиением на 2-а кластера с двумя RR в каждой.

Чтобы обеспечить полносвязную топологию BGP c меньшим колличеством связей. Разобьем сеть на кластер 1 (R31, R32, R35, R36)
и кластер 2 (R33, R34, R37). Настроим R31, R32, R33, R34 как Route reflector для своих кластеров.

![IBGP ISP2.png](Stend%2FIBGP%20ISP2.png)

Настройку Route reflector покажем на примере R31.
````
R31#sh run | sec bgp
router bgp 100
 bgp router-id 10.10.8.31
 bgp cluster-id 1
 bgp log-neighbor-changes
 neighbor iBGP_Cli peer-group
 neighbor iBGP_Cli remote-as 100
 neighbor iBGP_Cli update-source Loopback0
 neighbor iBGP_RR peer-group
 neighbor iBGP_RR remote-as 100
 neighbor iBGP_RR update-source Loopback0
 neighbor iBGP_RR_IPv6 peer-group
 neighbor iBGP_RR_IPv6 remote-as 100
 neighbor iBGP_RR_IPv6 update-source Loopback0
 neighbor iBGP_Cli_IPv6 peer-group
 neighbor iBGP_Cli_IPv6 remote-as 100
 neighbor iBGP_Cli_IPv6 update-source Loopback0
 neighbor 10.10.8.32 peer-group iBGP_RR
 neighbor 10.10.8.33 peer-group iBGP_RR
 neighbor 10.10.8.34 peer-group iBGP_RR
 neighbor 10.10.8.35 peer-group iBGP_Cli
 neighbor 10.10.8.36 peer-group iBGP_Cli
 neighbor 2022:ABCC:318:8::32 peer-group iBGP_RR_IPv6
 neighbor 2022:ABCC:318:8::33 peer-group iBGP_RR_IPv6
 neighbor 2022:ABCC:318:8::34 peer-group iBGP_RR_IPv6
 neighbor 2022:ABCC:318:8::35 peer-group iBGP_Cli_IPv6
 neighbor 2022:ABCC:318:8::36 peer-group iBGP_Cli_IPv6
 !
 address-family ipv4
  neighbor iBGP_Cli route-reflector-client
  neighbor iBGP_Cli next-hop-self
  neighbor iBGP_RR next-hop-self
  neighbor 10.10.8.32 activate
  neighbor 10.10.8.33 activate
  neighbor 10.10.8.34 activate
  neighbor 10.10.8.35 activate
  neighbor 10.10.8.36 activate
  no neighbor 2022:ABCC:318:8::32 activate
  no neighbor 2022:ABCC:318:8::33 activate
  no neighbor 2022:ABCC:318:8::34 activate
  no neighbor 2022:ABCC:318:8::35 activate
  no neighbor 2022:ABCC:318:8::36 activate
 exit-address-family
 !
 address-family ipv6
  neighbor iBGP_RR_IPv6 next-hop-self
  neighbor iBGP_Cli_IPv6 route-reflector-client
  neighbor iBGP_Cli_IPv6 next-hop-self
  neighbor 2022:ABCC:318:8::32 activate
  neighbor 2022:ABCC:318:8::33 activate
  neighbor 2022:ABCC:318:8::34 activate
  neighbor 2022:ABCC:318:8::35 activate
  neighbor 2022:ABCC:318:8::36 activate
 exit-address-family
R31#
````
Использование Peer-group позволяет уменьшить кол-во настроек, будет заметней с увеличением кол-ва клиентов.

Настройки RR клиента ничем не отличаются от обычной настройки iBGP, покажем на примере R35.
````
R35#sh run | sec bgp
router bgp 100
 bgp router-id 10.10.8.35
 bgp log-neighbor-changes
 neighbor 10.10.8.31 remote-as 100
 neighbor 10.10.8.31 update-source Loopback0
 neighbor 10.10.8.32 remote-as 100
 neighbor 10.10.8.32 update-source Loopback0
 neighbor 2022:A304:11AA:1::1:20 remote-as 120
 neighbor 2022:ABCC:318:8::31 remote-as 100
 neighbor 2022:ABCC:318:8::31 update-source Loopback0
 neighbor 2022:ABCC:318:8::32 remote-as 100
 neighbor 2022:ABCC:318:8::32 update-source Loopback0
 neighbor 135.200.13.51 remote-as 120
 !
 address-family ipv4
  network 110.1.22.0 mask 255.255.255.0
  neighbor 10.10.8.31 activate
  neighbor 10.10.8.31 next-hop-self
  neighbor 10.10.8.32 activate
  neighbor 10.10.8.32 next-hop-self
  no neighbor 2022:A304:11AA:1::1:20 activate
  no neighbor 2022:ABCC:318:8::31 activate
  no neighbor 2022:ABCC:318:8::32 activate
  neighbor 135.200.13.51 activate
 exit-address-family
 !
 address-family ipv6
  network 2022:ABCC:318::/48
  neighbor 2022:A304:11AA:1::1:20 activate
  neighbor 2022:ABCC:318:8::31 activate
  neighbor 2022:ABCC:318:8::31 next-hop-self
  neighbor 2022:ABCC:318:8::32 activate
  neighbor 2022:ABCC:318:8::32 next-hop-self
 exit-address-family
R35#
````
Посмотрим, что заданные условия выполнены, покажем команды вывода _**sh ip protocols**_ для RR R31 и клиента R35.

````
Routing Protocol is "bgp 100"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Route Reflector for address family IPv4 Unicast with the cluster-id 0.0.0.1, 2                                                                         clients
  Route Reflector for address family IPv6 Unicast with the cluster-id 0.0.0.1, 2                                                                         clients
  IGP synchronization is disabled
  Automatic route summarization is disabled
  Neighbor(s):
    Address          FiltIn FiltOut DistIn DistOut Weight RouteMap
    10.10.8.32
    10.10.8.33
    10.10.8.34
    10.10.8.35
    10.10.8.36
  Maximum path: 1
  Routing Information Sources:
    Gateway         Distance      Last Update
    10.10.8.35           200      6d19h
    10.10.8.36           200      6d19h
  Distance: external 20 internal 200 local 200

R31#
````
````
Routing Protocol is "bgp 100"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  IGP synchronization is disabled
  Automatic route summarization is disabled
  Neighbor(s):
    Address          FiltIn FiltOut DistIn DistOut Weight RouteMap
    10.10.8.31
    10.10.8.32
    135.200.13.51
  Maximum path: 1
  Routing Information Sources:
    Gateway         Distance      Last Update
    10.10.8.31           200      6d19h
    135.200.13.51         20      6d19h
  Distance: external 20 internal 200 local 200

R35#
````
Ну и содержание таблицы базы данных маршрутов BGP для R35
````
R35#sh ip bgp
BGP table version is 7, local router ID is 10.10.8.35
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 * i 99.13.77.0/24    10.10.8.36               0    100      0 1000 i
 *>i                  10.10.8.36               0    100      0 1000 i
 *                    135.200.13.51                          0 120 1000 i
 * i 110.1.22.0/24    10.10.8.36         2048640    100      0 i
 *>                   10.10.0.25         2048640         32768 i
 *>  135.200.13.0/24  135.200.13.51            0             0 120 i
R35#
````
Настройка не особо отличается от обычной настройки BGP с RR.

Вернемся к настройке сети офиса оператора.

#### 8. Манипуляция с атрибутами BGP в сети офиса оператора.

По какой-то причине, допустим по стоимости трафика, нам необходимо направить весь трафик в сторону ISP1. Тогда ISP2 станет для нас резервным провайдером.
Отобразим на примере R36 текущие маршруты в базе BGP
````
R36#sh ip bgp
BGP table version is 7, local router ID is 10.10.8.36
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 *>  99.13.77.0/24    110.1.22.8               0             0 1000 i
 * i 110.1.22.0/24    10.10.8.35         2048640    100      0 i
 *>                   10.10.0.34         2048640         32768 i
 *   135.200.13.0/24  110.1.22.8                             0 1000 120 i
 * i                  10.10.8.35               0    100      0 120 i
 *>i                  10.10.8.35               0    100      0 120 i
R36#
```` 
Наилучшим маршрутом для доставки трафика в сеть 99.13.77.0/24 AS1000 является прямое соединение между R2 и R36.
Наша задача, сделать так, чтобы провайдер ISP1 стал приоритетным. Для этого попробуем повлиять на атрибут AS-Path.
Настройку производим на R2.
````
R2(config)#route-map AS_PATH_PREP permit 10
R2(config-route-map)#set as-path prepend 1000 1000 1000
R2(config)#router bgp 1000
R2(config-router)#address-family ipv4
R2(config-router-af)#neighbor 110.1.22.9 route-map AS_PATH_PREP out
````
После внесенных изменений талица маршрутов BGP R36 выглядит так
````
R36#sh ip bgp
BGP table version is 10, local router ID is 10.10.8.36
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 *>i 99.13.77.0/24    10.10.8.35               0    100      0 120 1000 i
 * i                  10.10.8.35               0    100      0 120 1000 i
 *                    110.1.22.8               0             0 1000 1000 1000 1000 i
 * i 110.1.22.0/24    10.10.8.35         2048640    100      0 i
 *>                   10.10.0.34         2048640         32768 i
 *   135.200.13.0/24  110.1.22.8                             0 1000 1000 1000 1000 120 i
 * i                  10.10.8.35               0    100      0 120 i
 *>i                  10.10.8.35               0    100      0 120 i
R36#
````
Очевидно, что входящий трафик в сеть провайдера из/через AS100 попадет в сторону оператора на сеть  99.13.77.0/24 уже только через AS120.
Да мы нарочно пустили так трафик и скорее всего задержки увеличатся, но мы не сервис проовайдер интернет.

Что касается исходящего трафика, то его так-же направим в сторону ISP1.
Настройку производим на R1 а результат посмотрим на R2.

До настройки таблица маршрутов BGP на R2
````
R2#sh ip bgp
BGP table version is 5, local router ID is 192.168.1.2
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 *>  99.13.77.0/24    0.0.0.0                  0         32768 i
 *>  110.1.22.0/24    110.1.22.9         2048640             0 100 i
 *>i 135.200.13.0/24  192.168.1.1              0    100      0 120 i
 *                    110.1.22.9                             0 100 120 i
R2#
````
Выполняем настройки на R1
````
R1(config)#route-map Local-Pref permit 10
R1(config-route-map)#set local-preference 500

R1(config)#router bgp 1000
R1(config-router)#address-family ipv4
R1(config-router-af)#neighbor 99.13.77.1 route-map Local-Pref in
````
Теперь 
````
R2#sh ip bgp
BGP table version is 8, local router ID is 192.168.1.2
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal,
              r RIB-failure, S Stale, m multipath, b backup-path, f RT-Filter,
              x best-external, a additional-path, c RIB-compressed,
Origin codes: i - IGP, e - EGP, ? - incomplete
RPKI validation codes: V valid, I invalid, N Not found

     Network          Next Hop            Metric LocPrf Weight Path
 *>  99.13.77.0/24    0.0.0.0                  0         32768 i
 *>i 110.1.22.0/24    192.168.1.1              0    500      0 120 100 i
 *                    110.1.22.9         2048640             0 100 i
 *>i 135.200.13.0/24  192.168.1.1              0    500      0 120 i
 *                    110.1.22.9                             0 100 120 i
````
Очевидно, что теперь и весь исходящий трафик оператора пойдет в сторону AS120 ISP1.

Обезопасим себя от транзитного трафика сети интернет.
Настройки выполним для R1 и R2, а покажем на примере R1
````
R1(config)# ip prefix-list BGP_no_trasit seq 5 permit 99.13.77.0/24
R1(config)# ipv6 prefix-list BGP_no_trasit_v6 seq 5 permit 2022:a304:20bf::/48
R1(config)#router bgp 1000
R1(config-router)#address-family ipv4
R1(config-router-af)#neighbor 99.13.77.1 prefix-list BGP_no_trasit out

R1(config-router)#address-family ipv6
R1(config-router-af)#neighbor 2022:A304:20BF::2 prefix-list BGP_no_trasit_v6 out
````

#### 9. Настроить NAT на R1 и R2 в сети оператора

Настроим NAT c перегрузкой на R1 и R2 в пул из двух IP адресов собственной AS оператора.
Разрешим пользователям в сети 192.168.20.0/24 выход в глобальную сеть через NAT.

Настройки на примере R1.

Cоздаем стандартный нумерованный ACL
````
R1(config)#access-list 20 deny 192.168.20.0 0.0.0.3
R1(config)#access-list 20 permit 192.168.20.0 0.0.0.255
````
Cоздаем пул ip адресов с именем Pool_inet и включаем PAT для IP адресов разрешенного диапазона access-list 20 в созданный пул Pool_inet.
````
R1(config)#ip nat pool Pool_inet 98.13.77.2 98.13.77.3 netmask 255.255.255.0
R1(config)#ip nat inside source list 9 pool Pool_inet overload
````
Устанавливаем интерфейсы e0/1-2 и e1/1 R1 как внутренние для NAT, а e0/3 - внешний с помощбю команд
````
R1(config-if)#ip nat inside
R1(config-if)#ip nat outside
````


Часть 2.

Что-бы раскрыть все преймущества технологии передачи пакетов с помощью меток (далее MPLS-TE) необходимо построить разветвленную сеть с кольцевыми топологиями.
Фрагмент сети MPLS-TE оператора представлен на отдельной картинке

Сегмент сети MPLS провайдера.

![MPLS-Shem.png](Stend%2FMPLS-Shem.png)

Немного о схеме. R5 и R6 находятся на центральном узле связи. Все остальные роутеры находятся на удаленных площадках.
Соединения между R5 и R7, R6 и R8 разненсены по разным направлениям и соеденены между собой оборудование спектрального уплотнения DWDM.
Все остальные соединения выполнены по серому волокну. Красным цветом выделены магистральные линки с большой пропускной способностью.
Собственно в них и будет помещена большая часть трафика. 


В MPLS-TE используются LSP построенные с помощью протокола RSVP-TE, который в срою очередь может работать поверх IGP OSPF или IS-IS.
Настройку начнем с динамического протокола маршрутизации IS-IS.

#### 10. Настроить протокол динамической маршрутизации IS-IS в MPLS сегменте сети провайдера.

Допустим все роутеры представленного сегмента находятся в одной зоне Area1.
При запуске процесса IS-IS присваиваем имя Area1, подразумевая, что будет еще расширение сети и на R5 и R6 будут запущены отдельные процессы IS-IS.
Для MPLS важно, что-бы все маршрутизаторы использовали один тип соседства, выбираем тип 2. При настройке IS-IS значение System identifier совпадает с IPv4 адресами интерфейсов Loopback 0.
Так-же предусмотрим защитный механизм аутентификации.

Настройки IS-IS на всех роутерах практически однотипны, покажем на примере R5. Настройку начинаем с создания цепочки ключей аутентификации
````
R5(config)#key chain key_isis
R5(config-keychain)# key 1
R5(config-keychain-key)#  key-string 7 03075218050061
R5(config-keychain-key)#  cryptographic-algorithm md5
````
Создаем роутер IS-IS
````
R5(config)#router isis Area1
R5(config-router)#net 49.0001.1921.6801.0005.00
R5(config-router)#is-type level-2-only
R5(config-router)#passive-interface Ethernet0/0
R5(config-router)#passive-interface Ethernet1/0
R5(config-router)#passive-interface Loopback0
````
Настройки на интерфейсах участвующих в процессе IS-IS
````
R5(config-if)#ip router isis Area1
R5(config-if)#isis network point-to-point
R5(config-if)#isis authentication mode md5
R5(config-if)#isis authentication key-chain key_isis
````
Несколько результатов команд выводов

Соседство
````
R5#sh isis nei

Tag Area1:
System Id      Type Interface   IP Address      State Holdtime Circuit Id
R6             L2   Et0/2       192.168.11.18   UP    29       01
R6             L2   Et1/2       192.168.11.22   UP    24       03
R7             L2   Et0/1       192.168.11.2    UP    29       00
R7             L2   Et1/1       192.168.11.6    UP    27       03
R12            L2   Et0/3       192.168.11.26   UP    23       00
R5#
````
Топология сети.
````
R5# sh isis topology

Tag Area1:

IS-IS TID 0 paths to level-2 routers
System Id            Metric     Next-Hop             Interface   SNPA
R5                   --
R6                   10         R6                   Et0/2       aabb.cc00.1120
                                R6                   Et1/2       aabb.cc00.1121
R7                   10         R7                   Et0/1       aabb.cc00.7100
                                R7                   Et1/1       aabb.cc00.7101
R8                   20         R6                   Et0/2       aabb.cc00.1120
                                R6                   Et1/2       aabb.cc00.1121
R9                   20         R7                   Et0/1       aabb.cc00.7100
                                R7                   Et1/1       aabb.cc00.7101
R10                  20         R7                   Et0/1       aabb.cc00.7100
                                R7                   Et1/1       aabb.cc00.7101
R11                  30         R6                   Et0/2       aabb.cc00.1120
                                R6                   Et1/2       aabb.cc00.1121
                                R7                   Et0/1       aabb.cc00.7100
                                R7                   Et1/1       aabb.cc00.7101
R12                  10         R12                  Et0/3       aabb.cc00.f100
R5#
````
Список маршрутов полученных по протоколу IS-IS
````
R5#sh ip route isis
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

      192.168.0.0/24 is variably subnetted, 6 subnets, 2 masks
i L2     192.168.0.0/30 [115/10] via 192.168.11.22, 01:27:50, Ethernet1/2
                        [115/10] via 192.168.11.18, 01:27:50, Ethernet0/2
i L2     192.168.0.12/30 [115/10] via 192.168.11.22, 01:27:50, Ethernet1/2
                         [115/10] via 192.168.11.18, 01:27:50, Ethernet0/2
      192.168.10.0/32 is subnetted, 8 subnets
i L2     192.168.10.6 [115/10] via 192.168.11.22, 01:27:50, Ethernet1/2
                      [115/10] via 192.168.11.18, 01:27:50, Ethernet0/2
i L2     192.168.10.7 [115/10] via 192.168.11.6, 01:01:29, Ethernet1/1
                      [115/10] via 192.168.11.2, 01:01:29, Ethernet0/1
i L2     192.168.10.8 [115/20] via 192.168.11.22, 00:57:19, Ethernet1/2
                      [115/20] via 192.168.11.18, 00:57:19, Ethernet0/2
i L2     192.168.10.9 [115/20] via 192.168.11.6, 00:55:09, Ethernet1/1
                      [115/20] via 192.168.11.2, 00:55:09, Ethernet0/1
i L2     192.168.10.10 [115/20] via 192.168.11.6, 00:52:19, Ethernet1/1
                       [115/20] via 192.168.11.2, 00:52:19, Ethernet0/1
i L2     192.168.10.11 [115/30] via 192.168.11.22, 00:51:27, Ethernet1/2
                       [115/30] via 192.168.11.18, 00:51:27, Ethernet0/2
                       [115/30] via 192.168.11.6, 00:51:27, Ethernet1/1
                       [115/30] via 192.168.11.2, 00:51:27, Ethernet0/1
i L2     192.168.10.12 [115/10] via 192.168.11.26, 00:58:56, Ethernet0/3
      192.168.11.0/24 is variably subnetted, 18 subnets, 2 masks
i L2     192.168.11.8/30 [115/20] via 192.168.11.22, 01:27:50, Ethernet1/2
                         [115/20] via 192.168.11.18, 01:27:50, Ethernet0/2
i L2     192.168.11.12/30 [115/20] via 192.168.11.22, 01:27:50, Ethernet1/2
                          [115/20] via 192.168.11.18, 01:27:50, Ethernet0/2
i L2     192.168.11.28/30 [115/20] via 192.168.11.26, 00:58:56, Ethernet0/3
                          [115/20] via 192.168.11.6, 00:58:56, Ethernet1/1
                          [115/20] via 192.168.11.2, 00:58:56, Ethernet0/1
i L2     192.168.11.32/30 [115/20] via 192.168.11.6, 01:01:29, Ethernet1/1
                          [115/20] via 192.168.11.2, 01:01:29, Ethernet0/1
i L2     192.168.11.36/30 [115/30] via 192.168.11.6, 00:52:19, Ethernet1/1
                          [115/30] via 192.168.11.2, 00:52:19, Ethernet0/1
i L2     192.168.11.40/30 [115/30] via 192.168.11.22, 00:57:19, Ethernet1/2
                          [115/30] via 192.168.11.18, 00:57:19, Ethernet0/2
i L2     192.168.11.44/30 [115/30] via 192.168.11.22, 00:55:09, Ethernet1/2
                          [115/30] via 192.168.11.18, 00:55:09, Ethernet0/2
                          [115/30] via 192.168.11.6, 00:55:09, Ethernet1/1
                          [115/30] via 192.168.11.2, 00:55:09, Ethernet0/1
i L2     192.168.11.48/30 [115/20] via 192.168.11.6, 01:01:29, Ethernet1/1
                          [115/20] via 192.168.11.2, 01:01:29, Ethernet0/1
R5#
````

#### 11. Настройка MPLS-TE на всех маршрутизаторах сегмента MPLS оператора.

Настройка приведена на примере R5. На роутере включаем поддержку MPLS-TE
````
R5(config)#mpls traffic-eng tunnels
````
По умолчанию метрики IGP, в нашем случае IS-IS, равны метрикам TE и при построении туннеля CSPF (Constrained Shortest Path First) 
построит LSP (Label Switched Path) ориентируясь на метрику TE.
````
R5# sh mpls traffic-eng top
My_System_id: 1921.6801.0005.00 (isis  level-2)

Signalling error holddown: 10 sec Global Link Generation 14

IGP Id: 1921.6801.0005.00, MPLS TE Id:192.168.10.5 Router Node  (isis  level-2)
      link[0]: Point-to-Point, Nbr IGP Id: 1921.6801.0006.00, nbr_node_id:2, gen                                                                                                             :2
          frag_id 0, Intf Address:192.168.11.17, Nbr Intf Address:192.168.11.18
          TE metric:10, IGP metric:10, attribute flags:0x0
          SRLGs: None
          physical_bw: 10000 (kbps), max_reservable_bw_global: 0 (kbps)
          max_reservable_bw_sub: 0 (kbps)

                                 Global Pool       Sub Pool
               Total Allocated   Reservable        Reservable
               BW (kbps)         BW (kbps)         BW (kbps)
               ---------------   -----------       ----------
        bw[0]:            0                0                0
        bw[1]:            0                0                0
        bw[2]:            0                0                0
        bw[3]:            0                0                0
        bw[4]:            0                0                0
        bw[5]:            0                0                0
        bw[6]:            0                0                0
        bw[7]:            0                0                0

      link[1]: Point-to-Point, Nbr IGP Id: 1921.6801.0006.00, nbr_node_id:2, gen                                                                                                             :2
````

Немного о метриках. Алгоритм CSPF рассчитывает кратчайший LSP на основании метрик и с учетом дополнительных ограничений
RSVP-TE (Resource ReSerVation Protocol), заданных при настройке туннеля. Можем указать использовать 
метрику IGP (в настройках тунельного интерфеса исп. команда **_R5(config-if)#tunnel mpls traffic-eng path-selection metric igp_**
) вместо TE и в случае необходимости менять ее на каждом физическом интерфейсе. Так-же, в случае необходимости,
можем изменять метрику TE для каждого интерфейса, что мне кажется более удобным. Так и поступим.
Для основных магистральных линий (на схеме выделены красным и по легенде имеют большую пропускную способность) оставим
метрики TE=10 неизменными тогда как для остальных увеличим до 20.

Настройки для интерфейсов маршрутизатора R5.
Для e0/3
````
R5(config)#int e0/3
R5(config-if)#mpls traffic-eng tunnels
R5(config-if)#mpls traffic-eng administrative-weight 20
R5(config-if)#ip rsvp bandwidth 4000
````
Включены возможности TE, изменена метрика TE на 20, указано ограничения по полосе пропускания 4 МБит/с.
 Команда **_ip rsvp bandwidth 4000_** является обязательной если хотим указывать требования по полосе туннеля.
Это только референсное значение для расчёта пути TE, и фактически команда никак не ограничивает реальную скорость 
TE-трафика, через интерфейс. Одно из возможных применений (резервирование ресурса) в условиях ограниченности ресурсов
пропускной способности линков, исключить просчет алгоритмом CSFP маршрута LSP для тунелей емкостью свыше 6 МБит/c.

Изменения после настройки
````
R5#sh mpls traffic-eng link-management interfaces e0/3
System Information::
    Links Count:          5
Link ID::  Et0/3 (192.168.11.25)
    Local Intfc ID:         4
    Link Status:
      SRLGs:                None
      Intfc Switching Capability Descriptors:
         Default:           Intfc Switching Cap psc1, Encoding ethernet
      Link Label Type:      Packet
      Physical Bandwidth:   10000 kbits/sec
      Max Res Global BW:    4000 kbits/sec (reserved: 0% in, 0% out)
      Max Res Sub BW:       0 kbits/sec (reserved: 100% in, 100% out)
      MPLS TE Link State:   MPLS TE on, RSVP on, admin-up, flooded
      Inbound Admission:    reject-huge
      Outbound Admission:   allow-if-room
      Link MTU:             IP 1500, MPLS 1500
      Admin. Weight:        20 (configured)
      IGP Neighbor Count:   1
      Neighbor:             ID 1921.6801.0012.00, IP 192.168.11.26 (Up)
    Flooding Status for each configured area [1]:
      IGP Area[1]:  isis  level-2:  flooded
````
Для остальных интерфейсов учавствующих в процесс TE
````
R5(config-if)#mpls traffic-eng tunnels
R5(config-if)#ip rsvp bandwidth 10000
````
Выполним аналогичные настройки для всех оставшихся роутеров.

Выполняем настройки для протокола IS-IS.
````
R5(config)#router isis Area1
R5(config-router)#metric-style wide
R5(config-router)#mpls traffic-eng router-id Loopback0
R5(config-router)#mpls traffic-eng level-2
````
Настройки на всех роутерах одинаковые

#### 11. Построение динамического туннеля.

Произведем настройку динамического туннеля между R5-R10
````
R5(config)#interface tunnel 10
R5(config-if)#description to Customer1_R10
R5(config-if)#ip unnumbered Loopback0
R5(config-if)#tunnel mode mpls traffic-eng
R5(config-if)#tunnel destination 192.168.10.10
R5(config-if)#tunnel mpls traffic-eng bandwidth 500
R5(config-if)#tunnel mpls traffic-eng path-option 1 dynamic
````
И сразу динамический туннель поднялся.
````
R5#sh mpls traffic-eng tunnels tunnel10

Name: to Customer1_R10                    (Tunnel10) Destination: 192.168.10.10
  Status:
    Admin: up         Oper: up     Path: valid       Signalling: connected
    path option 1, type dynamic (Basis for Setup, path weight 60)

  Config Parameters:
    Bandwidth: 500      kbps (Global)  Priority: 7  7   Affinity: 0x0/0xFFFF
    Metric Type: TE (default)
    AutoRoute:  disabled  LockDown: disabled  Loadshare: 500      bw-based
    auto-bw: disabled
  Active Path Option Parameters:
    State: dynamic path option 1 is active
    BandwidthOverride: disabled  LockDown: disabled  Verbatim: disabled


  InLabel  :  -
  OutLabel : Ethernet0/2, 16
  RSVP Signalling Info:
       Src 192.168.10.5, Dst 192.168.10.10, Tun_Id 10, Tun_Instance 1
    RSVP Path Info:
      My Address: 192.168.11.17
      Explicit Route: 192.168.11.18 192.168.11.10 192.168.11.41 192.168.11.37
                      192.168.10.10
      Record   Route:   NONE
      Tspec: ave rate=500 kbits, burst=1000 bytes, peak rate=500 kbits
    RSVP Resv Info:
      Record   Route:   NONE
      Fspec: ave rate=500 kbits, burst=1000 bytes, peak rate=500 kbits
  Shortest Unconstrained Path Info:
    Path Weight: 20 (TE)
    Explicit Route: 192.168.11.2 192.168.11.34 192.168.10.10
  History:
    Tunnel:
      Time since created: 13 minutes, 36 seconds
      Time since path change: 12 minutes, 23 seconds
      Number of LSP IDs (Tun_Instances) used: 1
    Current LSP:
      Uptime: 12 minutes, 23 seconds
R5#
````
Но заработал по маршруту через R5-R6-R8-R11-R10, вопрос почему не по кратчайшему пути.
А проблема в том, что недонастроил интерфейсы на R7, а именно не хватало команды **_ip rsvp bandwidth_**.
Дело в том, что при указании требования по полосе для туннеля данная команда является обязательной, иначе IGP
эту информацию не анонсирует, а CSPF не будет учитывать эту линию и не вычислит путь под требования туннеля.
Исправим досадную ошибку
````
R5#sh mpls traffic-eng tunnels tunnel10

Name: to Customer1_R10                    (Tunnel10) Destination: 192.168.10.10
  Status:
    Admin: up         Oper: up     Path: valid       Signalling: connected
    path option 1, type dynamic (Basis for Setup, path weight 30)

  Config Parameters:
    Bandwidth: 500      kbps (Global)  Priority: 7  7   Affinity: 0x0/0xFFFF
    Metric Type: TE (default)
    AutoRoute:  disabled  LockDown: disabled  Loadshare: 500      bw-based
    auto-bw: disabled
  Active Path Option Parameters:
    State: dynamic path option 1 is active
    BandwidthOverride: disabled  LockDown: disabled  Verbatim: disabled


  InLabel  :  -
  OutLabel : Ethernet0/1, 16
  RSVP Signalling Info:
       Src 192.168.10.5, Dst 192.168.10.10, Tun_Id 10, Tun_Instance 3
    RSVP Path Info:
      My Address: 192.168.11.1
      Explicit Route: 192.168.11.2 192.168.11.34 192.168.10.10
      Record   Route:   NONE
      Tspec: ave rate=500 kbits, burst=1000 bytes, peak rate=500 kbits
    RSVP Resv Info:
      Record   Route:   NONE
      Fspec: ave rate=500 kbits, burst=1000 bytes, peak rate=500 kbits
  Shortest Unconstrained Path Info:
    Path Weight: 30 (TE)
    Explicit Route: 192.168.11.2 192.168.11.34 192.168.10.10
  History:
    Tunnel:
      Time since created: 37 minutes, 22 seconds
      Time since path change: 7 seconds
      Number of LSP IDs (Tun_Instances) used: 3
    Current LSP:
      Uptime: 7 seconds
      Selection: reoptimization
    Prior LSP:
      ID: path option 1 [1]
      Removal Trigger: path error
R5#
````
Теперь все в порядке, единственно что туннель не перестроился до того момента пока не спровоцировал повреждение 
по маршруту ранее построенного LSP. Хотя надо было в настройках тунеля указать команду _**routing dynamic**_ и тогда 
в случае доступности кратчайшего маршрута перестроение туннеля будет выполнено автоматически.
````
R5#traceroute mpls traffic-eng tunnel 10
Tracing MPLS TE Label Switched Path on Tunnel10, timeout is 2 seconds

Codes: '!' - success, 'Q' - request not sent, '.' - timeout,
  'L' - labeled output interface, 'B' - unlabeled output interface,
  'D' - DS Map mismatch, 'F' - no FEC mapping, 'f' - FEC mismatch,
  'M' - malformed request, 'm' - unsupported tlvs, 'N' - no label entry,
  'P' - no rx intf label prot, 'p' - premature termination of LSP,
  'R' - transit router, 'I' - unknown upstream index,
  'X' - unknown return code, 'x' - return code 0

Type escape sequence to abort.
  0 192.168.11.1 MRU 1500 [Labels: 16 Exp: 0]
L 1 192.168.11.2 MRU 1504 [Labels: implicit-null Exp: 0] 82 ms
! 2 192.168.11.34 9 ms
R5#
````
Был построен только один однонаправленный туннель в сторону R10, необходимо организовать такой-же туннель, но только уже от R10 в сторону R5.
````
R10(config)#interface Tunnel10
R10(config-if)# description to Customer1_R5
R10(config-if)# ip unnumbered Loopback0
R10(config-if)# tunnel mode mpls traffic-eng
R10(config-if)# tunnel destination 192.168.10.5
R10(config-if)# tunnel mpls traffic-eng bandwidth 500
R10(config-if)# tunnel mpls traffic-eng path-option 1 dynamic
R10(config-if)# routing dynamic
````
Успешно настроили туннели в оба направления
````
R10#sh mpls traffic-eng tunnels brief
Signalling Summary:
LSP Tunnels Process:            running
Passive LSP Listener:           running
RSVP Process:                   running
Forwarding:                     enabled
Periodic reoptimization:        every 3600 seconds, next in 2258 seconds
Periodic FRR Promotion:         Not Running
Periodic auto-bw collection:    every 300 seconds, next in 158 seconds
TUNNEL NAME                      DESTINATION      UP IF      DOWN IF    STATE/PROT
to Customer1_R5                  192.168.10.5     -         Et0/0     up/up
to Customer1_R10                 192.168.10.10    Et0/0      -          up/up   
Displayed 1 (of 1) heads, 0 (of 0) midpoints, 1 (of 1) tails
````
#### 12. Приоритизация туннелей

Покажем конфигурацию Tunnel10 на R5
````
interface Tunnel10
 description to Customer1_R10
 ip unnumbered Loopback0
 tunnel mode mpls traffic-eng
 tunnel destination 192.168.10.10
 tunnel mpls traffic-eng priority 7 7
 tunnel mpls traffic-eng bandwidth 500
 tunnel mpls traffic-eng path-option 1 dynamic
````
**_tunnel mpls traffic-eng priority 7 7_** такую команду не задавали, команда создана автоматически как только было создано требование 
к полосе туннеля.
Команда имеет два параметра по поряку: Setup Priority и Hold Priority.
Значение каждого могут варьировать от 0-наивысшего до 7-низшего приоритета.
Логика в том, что в условиях не ограниченной полосы тракта его ресурса на все туннели может не хватить и туннели с навысшим приоритетом
будут вытеснять туннели с низшим. Обычно выбираются одинаковые для Setup и Hold

#### 13. Управление туннелями
Можно выделить такие способы повлиять на построение туннелей как
1 Метрика пути MPLS TE
2 Ограничение по полосе пропускания
3 Explicit-Path
4 SRLG
5 Administrative Groups/Affinity

Первые два уже затронули и посмотрели в т.ч приоретизацию.
Не упоминалась упоминалась функция AutoBandwidth. Суть которой
отслеживать загрузку туннеля в течение определённого периода и адаптировать резервирование.

Но мы хотим определять загрузку линков самостоятельно и в этом случае больший интерес представляет Explicit-Path.
Вручную зададим, через какие узлы должен пройти LSP, а через какие не должен.
CSPF рассчитает маршрут с учётом Explicit-Path.

Настроим еще один туннель от R6 до R9.

На стороне R6
````
R6(config)#interface Tunnel9
R6(config-if)# description to Customer2_R9
R6(config-if)# ip unnumbered Loopback0
R6(config-if)# tunnel mode mpls traffic-eng
R6(config-if)# tunnel destination 192.168.10.9
R6(config-if)# tunnel mpls traffic-eng bandwidth 1000
R6(config-if)# tunnel mpls traffic-eng path-option 1 dynamic
*May  6 16:32:47.638: %LINEPROTO-5-UPDOWN: Line protocol on Interface Tunnel9, changed state to up
R6(config-if)#
````
На стороне R9
````
R9(config-if-range)#exit
R9(config)#interface Tunnel9
R9(config-if)# description to Customer1_R6
R9(config-if)# ip unnumbered Loopback0
R9(config-if)# tunnel mode mpls traffic-eng
R9(config-if)# tunnel destination 192.168.10.6
R9(config-if)# tunnel mpls traffic-eng bandwidth 1000
R9(config-if)# tunnel mpls traffic-eng path-option 1 dynamic
````
Туннель должны быть построен по короткому маршруту LSP R6-R8-R9 и наоборот.

Удостоверимся.
````
R6#sh mpls traffic-eng tunnels tunnel 9

Name: to Customer2_R9                     (Tunnel9) Destination: 192.168.10.9
  Status:
    Admin: up         Oper: up     Path: valid       Signalling: connected
    path option 1, type dynamic (Basis for Setup, path weight 30)

  Config Parameters:
    Bandwidth: 1000     kbps (Global)  Priority: 7  7   Affinity: 0x0/0xFFFF
    Metric Type: TE (default)
    AutoRoute:  disabled  LockDown: disabled  Loadshare: 1000     bw-based
    auto-bw: disabled
  Active Path Option Parameters:
    State: dynamic path option 1 is active
    BandwidthOverride: disabled  LockDown: disabled  Verbatim: disabled


  InLabel  :  -
  OutLabel : Ethernet0/1, 16
  RSVP Signalling Info:
       Src 192.168.10.6, Dst 192.168.10.9, Tun_Id 9, Tun_Instance 1
    RSVP Path Info:
      My Address: 192.168.11.9
      Explicit Route: 192.168.11.10 192.168.11.46 192.168.10.9
      Record   Route:   NONE
      Tspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
    RSVP Resv Info:
      Record   Route:   NONE
      Fspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
  Shortest Unconstrained Path Info:
    Path Weight: 30 (TE)
    Explicit Route: 192.168.11.10 192.168.11.46 192.168.10.9
  History:
    Tunnel:
      Time since created: 42 minutes, 55 seconds
      Time since path change: 42 minutes, 17 seconds
      Number of LSP IDs (Tun_Instances) used: 1
    Current LSP:
      Uptime: 42 minutes, 17 seconds
R6#
````
Да проходит, причем через интерфейс e0/0 R8 (192.168.11.10).
теперь попробуем указать маршрут для LSP через роутеры R5 и R7.

Cначала попробуем настроить на R6 так
````
R6(config)#ip explicit-path name Customer2
R6(cfg-ip-expl-path)#exclude-address 192.168.11.10
R6(cfg-ip-expl-path)#exclude-address 192.168.11.14
Explicit Path name Customer2:
    1: exclude-address 192.168.11.10
    2: exclude-address 192.168.11.14
R6(config)#int tunnel 9
R6(config-if)#tunnel mpls traffic-eng path-option 1 explicit name Customer2
````
Здесь мы запрещаем строить LSP через интерфейсы e0/0-1 R8. Проверяем как построен туннель.
````
R6#sh mpls traffic-eng tunnels tunnel 9

Name: to Customer2_R9                     (Tunnel9) Destination: 192.168.10.9
  Status:
    Admin: up         Oper: up     Path: valid       Signalling: connected
    path option 1, type explicit Customer2 (Basis for Setup, path weight 40)

  Config Parameters:
    Bandwidth: 1000     kbps (Global)  Priority: 7  7   Affinity: 0x0/0xFFFF
    Metric Type: TE (default)
    AutoRoute:  disabled  LockDown: disabled  Loadshare: 1000     bw-based
    auto-bw: disabled
  Active Path Option Parameters:
    State: explicit path option 1 is active
    BandwidthOverride: disabled  LockDown: disabled  Verbatim: disabled


  InLabel  :  -
  OutLabel : Ethernet0/2, 16
  RSVP Signalling Info:
       Src 192.168.10.6, Dst 192.168.10.9, Tun_Id 9, Tun_Instance 3
    RSVP Path Info:
      My Address: 192.168.11.18
      Explicit Route: 192.168.11.17 192.168.11.2 192.168.11.49 192.168.10.9
      Record   Route:   NONE
      Tspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
    RSVP Resv Info:
      Record   Route:   NONE
      Fspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
  Shortest Unconstrained Path Info:
    Path Weight: 30 (TE)
    Explicit Route: 192.168.11.10 192.168.11.46 192.168.10.9
  History:
    Tunnel:
      Time since created: 1 hours, 29 minutes
      Time since path change: 9 minutes, 5 seconds
      Number of LSP IDs (Tun_Instances) used: 3
    Current LSP:
      Uptime: 9 minutes, 5 seconds
    Prior LSP:
      ID: path option 1 [1]
      Removal Trigger: configuration changed
````
Полцчили маршрут R5(e0/2)-R7(e0/0)-R9(e0/1). Добились чего желали, но есть нюанс, что для данной топологии и конкретно 
нашего случая такая настройка приведет к фатальному исходу.
Отключим роутер R7. 
Получили закономерный результат
````
*May  6 18:14:31.822: %LINEPROTO-5-UPDOWN: Line protocol on Interface Tunnel9, changed state to down``
````
При этом есть рабочий доступный выход через R8, но мы сами обрубили концы.
Делаем вывод, что-бы эффективно использовать Explicit-Path нужно хорошо знать топологию сети и иметь прямые руки.

Добавим команду в настройке интерфейса Tunnel9
````
R6(config-if)#tunnel mpls traffic-eng path-option 10 dynamic
````
Команда имеет более низкий приоритет, но поскольку туннель не может быть построен по указанному нами условию,
то он будет построен динамически.

Имеем в итоге рабочий туннель через R8.
````
R6#sh mpls traffic-eng tunnels tunnel 9

Name: to Customer2_R9                     (Tunnel9) Destination: 192.168.10.9
  Status:
    Admin: up         Oper: up     Path: valid       Signalling: connected
    path option 10, type dynamic (Basis for Setup, path weight 30)
    path option 1, type explicit Customer2

  Config Parameters:
    Bandwidth: 1000     kbps (Global)  Priority: 7  7   Affinity: 0x0/0xFFFF
    Metric Type: TE (default)
    AutoRoute:  disabled  LockDown: disabled  Loadshare: 1000     bw-based
    auto-bw: disabled
  Active Path Option Parameters:
    State: dynamic path option 10 is active
    BandwidthOverride: disabled  LockDown: disabled  Verbatim: disabled


  InLabel  :  -
  OutLabel : Ethernet1/1, 16
  RSVP Signalling Info:
       Src 192.168.10.6, Dst 192.168.10.9, Tun_Id 9, Tun_Instance 82
    RSVP Path Info:
      My Address: 192.168.11.13

R6#sh mpls traffic-eng tunnels tunnel 9

Name: to Customer2_R9                     (Tunnel9) Destination: 192.168.10.9
  Status:
    Admin: up         Oper: up     Path: valid       Signalling: connected
    path option 10, type dynamic (Basis for Setup, path weight 30)
    path option 1, type explicit Customer2

  Config Parameters:
    Bandwidth: 1000     kbps (Global)  Priority: 7  7   Affinity: 0x0/0xFFFF
    Metric Type: TE (default)
    AutoRoute:  disabled  LockDown: disabled  Loadshare: 1000     bw-based
    auto-bw: disabled
  Active Path Option Parameters:
    State: dynamic path option 10 is active
    BandwidthOverride: disabled  LockDown: disabled  Verbatim: disabled


  InLabel  :  -
  OutLabel : Ethernet1/1, 16
  RSVP Signalling Info:
       Src 192.168.10.6, Dst 192.168.10.9, Tun_Id 9, Tun_Instance 82
    RSVP Path Info:
      My Address: 192.168.11.13
      Explicit Route: 192.168.11.14 192.168.11.46 192.168.10.9
      Record   Route:   NONE
      Tspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
    RSVP Resv Info:
      Record   Route:   NONE
      Fspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
  Shortest Unconstrained Path Info:
    Path Weight: 30 (TE)
    Explicit Route: 192.168.11.10 192.168.11.46 192.168.10.9
  History:
    Tunnel:
      Time since created: 2 hours, 54 minutes
      Time since path change: 7 minutes, 46 seconds
      Number of LSP IDs (Tun_Instances) used: 82
    Current LSP:
      Uptime: 7 minutes, 46 seconds
    Prior LSP:
      ID: path option 1 [72]
      Removal Trigger: configuration changed
      Last Error: PCALC:: No path to destination, 1921.6801.0009.00
````
Теперь выполним наcтройки на стороне R9, но применим другой подход. Явно укажем маршрут для построения тунеля R7(e1/1)-R5(e0/1)-R6(e0/2).
````
R9(config)#ip explicit-path name Customer2
R9(cfg-ip-expl-path)#next-address 192.168.11.17
R9(cfg-ip-expl-path)#next-address 192.168.11.1
R9(cfg-ip-expl-path)#next-address 192.168.11.18

R9(config)#int tun 9
tunnel mpls traffic-eng path-option 1 explicit name Customer2
tunnel mpls traffic-eng path-option 10 dynamic

````
В результате имеем маршрут туннеля
````
Explicit Route: 192.168.11.50 192.168.11.1 192.168.11.18 192.168.10.6
````

Удобная функция по защите от плоских колец SRLG — Shared Risk Link Group. Объединяет интерфейсы в группы, не позволяя строить основной и резервный туннели
через интерфейсы принадлежащие одной группе.

И посдедняя функция это Affinity. Имеет смысл настраивать и использовать на разветвленной сети. Позволяет автоматически строить туннели по ранее заданным критериям. Оперирует 
32-х битным параметром интерфейса Attribute-Flag. Сложный процесс настройки, но если правильно настроена позволяет строить туннели удовлетворяющие определенным критериям автоматически.

#### 14. Построение защитных туннелей.

MPLS-TE два решения для обеспечения стабильности трафика и уменьшение времени простоя. Для этого используются механизмы Path Protection и Local Protection.
Для нашей схемы используем Path Protection. Суть ее заключается в том, что при настройке тунеля указывается, необходимость в построении двух LSP Primary и Secondary.

Настроим туннель между R7 и R11. Маршруты построения LSP для основного и защитного туннеля зададим вручную. При создании ip explicit-path используем IP address интерфейсов Loopback маршрутизаторов.

Покажем настройку на примере R7
````
R7(config)#ip explicit-path name Customer3
R7(cfg-ip-expl-path)#next-address 192.168.10.10

R7(config)#ip explicit-path name Customer3_protect
R7(cfg-ip-expl-path)#next-address 192.168.10.9
R7(cfg-ip-expl-path)#next-address 192.168.10.8

R7(config)#interface Tunnel11
R7(config-if)#description to Customer3_R11
R7(config-if)#ip unnumbered Loopback0
R7(config-if)#tunnel mode mpls traffic-eng
R7(config-if)#tunnel destination 192.168.10.11
R7(config-if)#tunnel mpls traffic-eng bandwidth 1000
R7(config-if)#tunnel mpls traffic-eng path-option 5 explicit name Customer3
R7(config-if)#tunnel mpls traffic-eng path-option protect 5 explicit name Customer3_protect
````
Путь рабочего тунеля проходит R7-R10-R11, а защитного R7-R9-R8-R11.
````
R7#sh mpls traffic-eng tunnels tunnel 11 protection
to Customer3_R11
  LSP Head, Tunnel11, Admin: up, Oper: up
  Src 192.168.10.7, Dest 192.168.10.11, Instance 1
  Fast Reroute Protection: None
  Path Protection: 0 Common Link(s), 0 Common Node(s)
    Primary lsp path:192.168.11.34 192.168.11.38
                     192.168.10.11
    Protect lsp path:192.168.11.49 192.168.11.45
                     192.168.11.41 192.168.10.11

    Path Protect Parameters:
      Bandwidth: 1000     kbps (Global)  Priority: 4  4   Affinity: 0x0/0xFFFF
      Metric Type: TE (default)
    InLabel  :  -
    OutLabel : Ethernet1/1, 16
    RSVP Signalling Info:
         Src 192.168.10.7, Dst 192.168.10.11, Tun_Id 11, Tun_Instance 33
      RSVP Path Info:
        My Address: 192.168.11.50
        Explicit Route: 192.168.11.49 192.168.11.45 192.168.11.41 192.168.10.11
        Record   Route:   NONE
        Tspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
      RSVP Resv Info:
        Record   Route:   NONE
        Fspec: ave rate=1000 kbits, burst=1000 bytes, peak rate=1000 kbits
R7#
````
Произведем аналогичные настройки для R11.
Итак, построено 2-а туннеля, один из которых защитный, что горантирует за счет уже просчитанного LSP сократить время на переключение. 
Минусом является то, что защитный туннель при исправном рабочем будет простаивать, но при этом отнимать часть пропускной способности линков.

#### 15. Построить L3VPN в тунеле MPLS-TE.

Уже есть построенный туннель с защитой между R7 и R11. Настроим L3VPN для Customer3.

![L3VPN_Customer3.png](Stend%2FL3VPN_Customer3.png)

Покажем настройку на примере R7, аналогично настриваем и на R11.
````
R7(config)#ip vrf Customer3
R7(config-vrf)#rd 65001:20
R7(config-vrf)#route-target export 65001:20
R7(config-vrf)#route-target import 65001:20
R7(config-vrf)#exit
R7(config)int e0/2
R7(config-if)#description to_Customer3
R7(config-if)#ip vrf forwarding Customer3
R7(config-if)#ip address 10.10.1.1 255.255.255.0
R7(config-if)#router bgp 65001
R7(config-router)#neighbor 192.168.10.11 remote-as 65001
R7(config-router)#neighbor 192.168.10.11 update-source Loopback0
R7(config-router)#address-family vpnv4
R7(config-router-af)#neighbor 192.168.10.11 activate
R7(config-router-af)#neighbor 192.168.10.11 send-community both
R7(config-router-af)#exit
R7(config-router)#address-family ipv4 vrf Customer3
R7(config-router-af)#redistribute connected
R7(config)#interface tunnel 11
R7(config-if)#tunnel mpls traffic-eng autoroute announce
````
Маршруты в vrf Customer3

````
R7#sh ip route vrf Customer3

Routing Table: Customer3
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

      10.0.0.0/8 is variably subnetted, 3 subnets, 2 masks
C        10.10.1.0/24 is directly connected, Ethernet0/2
L        10.10.1.1/32 is directly connected, Ethernet0/2
B        10.10.2.0/24 [200/0] via 192.168.10.11, 02:33:27
R7#
````
````
R7# sh mpls traffic-eng autoroute
MPLS TE autorouting enabled
  destination 1921.6801.0011.00, area isis  level-2, has 1 tunnels
    Tunnel11    (load balancing metric 2000000, nexthop 192.168.10.11)
                (flags: Announce)
R7#
````
Проверим доступность интерфейса e0/0 R26 со стороны R25
````
R25#ping 10.10.2.2
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.2.2, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R25#
````

