## Практическое задание №9

1. Настроить eBGP между офисом Москва и двумя провайдерами - Киторн и Ламас.
2. Настроить eBGP между провайдерами Киторн и Ламас.
3. Настроить eBGP между Ламас и Триада.
4. Настроить eBGP между офисом С.-Петербург и провайдером Триада.
5. Организовать IP доступность между пограничным роутерами офисов Москва и С.-Петербург.


Представленная схема лабораторного стенда притерпела изменения в результате выполнения условия 
практического задания по настройке протокола OSPF в офисе Москва.
Повышение отказоустойчивости Area0 OSPF.



### 1. Настроить eBGP между офисом Москва и двумя провайдерами - Киторн и Ламас.

Настройку протокола EBGP для IPv4 и IPv6 покажем на примере R14 в офисе Москва.
Выполним последовательность команд
````
R14(config)#router bgp 1001
R14(config-router)# bgp router-id 14.14.14.14
R14(config-router)#neighbor 33.13.8.20 remote-as 101
R14(config-router)#neighbor 203A:BB8A:D701::1 remote-as 101
R14(config-router)#address-family ipv4
R14(config-router-af)#network 98.10.10.0 mask 255.255.255.0
R14(config-router-af)exit
R14(config-router)#address-family ipv4
R14(config-router-af)network 203A:BB8A:D701::/48
R14(config-router-af)neighbor 203A:BB8A:D701::1 activate
````
На этом первичную натсройку можно считать завершенной.
Аналогичные настройки выполнены на R22 со стороны Киторн.
````
R22#sh run | sec bgp
router bgp 101
 bgp router-id 22.22.22.22
 bgp log-neighbor-changes
 neighbor 203A:BB8A:D701::2 remote-as 1001
 neighbor 33.13.8.21 remote-as 1001
 !
 address-family ipv4
  network 33.13.7.0 mask 255.255.255.0
  network 33.13.8.0 mask 255.255.255.0
  no neighbor 203A:BB8A:D701::2 activate
  neighbor 33.13.8.21 activate
 exit-address-family
 !
 address-family ipv6
  network 203A:A87A:413::/48
  neighbor 203A:BB8A:D701::2 activate
 exit-address-family
````
Проверим состояние соседства по BGP.

![R14 peer R22 neigh.png](R14%20peer%20R22%20neigh.png)

Проверим маршруты в таблице BGP R14 полученные от R22.
Но до этого создадим интерфейсы Loopback и статические маршруты к ним на обоих роутерах, в противном случае при отсутствии
маршрута к этой сети таблица BGP будет пустой. Через интерфейсы Loopback будем проверять IP связанность.
Настройка на примере R14
````
interface Loopback0
 ip address 192.168.0.14 255.255.255.255
 ipv6 address 203A:BB8A:D701:8888::14/128
 ipv6 enable
!
interface Loopback1
 ip address 98.10.10.0 255.255.255.255

ip route 98.10.10.0 255.255.255.0 Loopback1
!
ipv6 route 203A:BB8A:D701::/48 Loopback0
````
В таблице BGP появились записи о полученных маршрутах к объявленным сетям.

![R14 sh_ip_bgp.png](R14%20sh_ip_bgp.png)

В таблицу маршрутизации роутера были добавлены сети полученные по BGP.

![R14 sh_ip_route.png](R14%20sh_ip_route.png)

Проверим IP связанность между Loopback1 R14 и R22 по IPv4 и Loopback0 R14 и R22 по IPv6.

![R14 ping R22.png](R14%20ping%20R22.png)

Аналогично производим настройку соседства по BGP между R15 и R21.

Для R15
````
R15(config)#do sh run | sec bgp
router bgp 1001
 bgp router-id 15.15.15.15
 bgp log-neighbor-changes
 neighbor 203A:BB8A:D701:1::1 remote-as 301
 neighbor 77.100.10.40 remote-as 301
 !
 address-family ipv4
  network 98.10.10.0 mask 255.255.255.0
  no neighbor 203A:BB8A:D701:1::1 activate
  neighbor 77.100.10.40 activate
 exit-address-family
 !
 address-family ipv6
  network 203A:BB8A:D701::/48
  neighbor 203A:BB8A:D701:1::1 activate
 exit-address-family
````
и R21
````
R21#sh run | sec bgp
router bgp 301
 bgp router-id 21.21.21.21
 bgp log-neighbor-changes
 neighbor 203A:BB8A:D701:1::2 remote-as 1001
 neighbor 77.100.10.41 remote-as 1001
 !
 address-family ipv4
  network 77.100.10.0 mask 255.255.255.0
  no neighbor 203A:BB8A:D701:1::2 activate
  neighbor 77.100.10.41 activate
 exit-address-family
 !
 address-family ipv6
  network 203A:90AA:91::/48
  neighbor 203A:BB8A:D701:1::2 activate
 exit-address-family
````
В доказательство успешной настройки покажем содержание таблицы BGP R21.

![R21 sh_ip_bgp.png](R21%20sh_ip_bgp.png)

### 2. Настроить eBGP между провайдерами Киторн и Ламас.

Процедура настройки достаточно проста, но требует внимания.
Приводить здесь и далее непосредственно настройки конфигурации маршрутизаторов особого смысла нет.
Они и так отображены в полной кофигурации оборудования для лабораторного стенда.

Куда больший интерес представляет изменения в таблицах BGP роутеров и IP доступность между роутерами.

![R21 sh_ip_bgp2.png](R21%20sh_ip_bgp2.png)

Не трудно понять изменения. На примере IPv4 ранее доступная сеть 98.10.10.0/24 маршруту с AS1001 теперь доступна и через 
AS101, а так-же добавлены маршруты на сети 33.13.7.0/24 и 33.13.8.0/24 объяаленные внутри AS101.

Проверим 





















