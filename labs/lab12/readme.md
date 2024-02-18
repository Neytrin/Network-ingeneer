## Практическое задание №12

1. Настроить NAT(PAT) на R14 и R15. Трансляция должна осуществляться в адрес автономной системы AS1001.
2. Настроить NAT(PAT) на R18. Трансляция должна осуществляться в пул из 5 адресов автономной системы AS2042.
3. Настроить статический NAT для R20.
4. Настроить NAT так, чтобы R19 был доступен с любого узла для удаленного управления.
5*. Настроить статический NAT(PAT) для офиса Чокурдак.
5. Настроить IPv4 DHCP сервер в офисе Москва на маршрутизаторах R12 и R13. VPC1 и VPC7 должны получать сетевые настройки по DHCP.
6. Настроить NTP сервер на R12 и R13. Все устройства в офисе Москва должны синхронизировать время с R12 и R13.











1. Настроить NAT(PAT) на R14 и R15. Трансляция должна осуществляться в адрес автономной системы AS1001.
````
R14(config)#ip nat pool Pool_MSK_client 98.10.10.3 98.10.10.3 netmask 255.255.255.0

````
3. Настроить NAT(PAT) на R18. Трансляция должна осуществляться в пул из 5 адресов автономной системы AS2042.
3. Настроить статический NAT для R20.
4. Настроить NAT так, чтобы R19 был доступен с любого узла для удаленного управления.
   5*. Настроите статический NAT(PAT) для офиса Чокурдах.
5. Настроить IPv4 DHCP сервер в офисе Москва на маршрутизаторах R12 и R13. VPC1 и VPC7 должны получать сетевые настройки по DHCP.



````
R12(config)#ip dhcp excluded-address 172.16.8.1 172.16.8.4
R12(config)#ip dhcp excluded-address 172.16.12.1 172.16.12.4
R12(config)#ip dhcp pool NET_10
R12(dhcp-config)#network 172.16.8.0 255.255.255.0
R12(dhcp-config)# domain-name Moskow1001.com
R12(dhcp-config)# default-router 172.16.8.1
R12(dhcp-config)# lease 2
R12(dhcp-config)#exit
R12(config)#ip dhcp pool NET_20
R12(dhcp-config)# network 172.16.12.0 255.255.255.0
R12(dhcp-config)# default-router 172.16.12.1
R12(dhcp-config)# domain-name Moskow1001.com
R12(dhcp-config)#exit
R12(config)#ipv6 dhcp pool SW4-Stateless
R12(config-dhcpv6)# dns-server 203A:BB8A:D701:1001::1
R12(config-dhcpv6)# domain-name Moskow1001.com
R12(config-dhcpv6)#int ra e0/0-1
R12(config-if-range)#ipv6 nd other-config-flag
R12(config-if-range)# ipv6 dhcp server SW4-Stateless

````

````
SW4(config-if)#ip helper-address 192.168.0.12
SW4(config-if)#ip helper-address 192.168.0.13
SW4(config-if)#ipv6 dhcp relay destination 203a:bb8a:d701:8888::12
SW4(config-if)#ipv6 dhcp relay destination 203a:bb8a:d701:8888::13
````
6. Настроить NTP сервер на R12 и R13. Все устройства в офисе Москва должны синхронизировать время с R12 и R13.









