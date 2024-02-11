## Практическое задание №10

1. Настроить iBGP в офисом Москва между маршрутизаторами R14 и R15.
2. Настроить iBGP в провайдере Триада, с использованием RR.
3. Настроить сеть офиса Москва так, чтобы приоритетным провайдером стал Ламас.
4. Настроить сеть офиса С.-Петербург так, чтобы трафик до любого офиса распределялся по двум линкам одновременно.


### 1. Настроить iBGP в офисом Москва между маршрутизаторами R14 и R15.
Для настройки iBGP соседства для передачи маршрутной информации можно установить TCP сессию между физическими интерфейсами e1/0 роутеров 
R14 и R15. Но это не надежно, по причине если пропадет линк, то пропадет и iBGP соседство между R14 и R15, а вместе с ним и информация о маршрутах.
Конечно можно установить дополнительное BGP соседство через транзитные роутеры R12 и R13. В таком случае соседсво на R14
будет выглядеть так

![R14 sh_ip_bgp_sum.png](R14%20sh_ip_bgp_sum.png)

А так выглядит список маршрутов в базе BGP.

![R14 sh_ip_bgp.png](R14%20sh_ip_bgp.png)

Видно, что получены маршруты по iBGP (internal), все они valid, а лучшим выбран прямой маршрут R14-R15.

Но есть более элегантное решение.
В качестве интерфейсов для установления соседства по BGP использовать TCP сессию установленную между интерфейсами Loopback0
роутеров R14 и R15. Виртуальный сетевой интерфейс будет доступен всегда, а надежность связанности между Loopback интерфейсами 
R14 и R15 обеспечивается избыточностью связей Backbone area OSPF.

Запускаем процесс OSPF на интерфейсах Loopbak0 R14, R15. Покажем на примере R14.
````
R14(config)#int loopback 0
R14(config-if)#ip ospf 1 area 0
````
Теперь настраиваем процесс iBGP на роутерах одновременно для IPv4 и IPv6.
````
R14(config)#router bgp 1001
R14(config-router)#neighbor 192.168.0.15 remote-as 1001
R14(config-router)#neighbor 192.168.0.15 update-source loopback 0
R14(config-router)#neighbor 203a:bb8a:d701:8888::15 remote-as 1001
R14(config-router)#address-family ipv4
R14(config-router-af)#neighbor 192.168.0.15 next-hop-self
R14(config-router-af)#address-family ipv6
R14(config-router-af)#neighbor 203a:bb8a:d701:8888::15 activate
R14(config-router-af)#neighbor 203a:bb8a:d701:8888::15 next-hop-self
````
Меньше соседей и меньше записей маршрутов в базе BGP.  

![R14 sh_ip_bgp_sum_lo0.png](R14%20sh_ip_bgp_sum_lo0.png)

![R14 sh_ip_bgp_lo0.png](R14%20sh_ip_bgp_lo0.png)

Маршрутная информация получена, а в качестве Next Hop указан IPv4 адрес Loopback0 R15.

### 2. Настроить iBGP в провайдере Триада, с использованием RR.

Для начала настроим eBGP между Киторн и Триада, которую не учли в предыдущей работе.
Отобразим установевление соседских отношений по eBGP между R22 и R23.

![R23 sh_ip_bgp_sum.png](R23%20sh_ip_bgp_sum.png)

и полученные маршруты в базе BGP R23. 

![R23 sh_ip_bgp.png](R23%20sh_ip_bgp.png)

Распределим роли маршрутизаторов в процессе iBGP AS 520 Триада.
Пусть R24 и R26 будут выполнять роль Route reflector далее RR, а R23 и R25 - RR клиенты.
Сеть на кластеры не разбивалась.

По легенде Триада является крупным ISP и для упрощения приведен только фрагмент его сети.
В таком случае использование Full-Mesh топологии будет не оптимальным решением, но на приведенном фрагменте это не очевидно,
ввиду небольшого кол-ва роутеров.

Кол-во связей рассчитывается по формуле n*(n-1)/2

при Full-Mesh - потребуется установление 6 связей

при одном RR - потребуется установить 3 связи

при двух RR - потребуется установить 5 связей.

При двух RR потребуется установить больше связанностей чем при одном RR, но наличие альтернативного RR повышает надежность 
сохранения маршрутной информации в случае возникновения проблем на одном из них.

Пример настройки RR на R24
````
R24#sh run | sec bgp
router bgp 520
 bgp router-id 24.24.24.24
 bgp log-neighbor-changes
 neighbor 10.1.1.23 remote-as 520
 neighbor 10.1.1.23 update-source Loopback0
 neighbor 10.1.1.25 remote-as 520
 neighbor 10.1.1.25 update-source Loopback0
 neighbor 10.1.1.26 remote-as 520
 neighbor 10.1.1.26 update-source Loopback0
 neighbor 203A:88A1:A789:1::2:1 remote-as 301
 neighbor 203A:88A1:A789:1::3:1 remote-as 2042
 neighbor 203A:88A1:A789:8888::23 remote-as 520
 neighbor 203A:88A1:A789:8888::23 update-source Loopback0
 neighbor 203A:88A1:A789:8888::25 remote-as 520
 neighbor 203A:88A1:A789:8888::25 update-source Loopback0
 neighbor 203A:88A1:A789:8888::26 remote-as 520
 neighbor 203A:88A1:A789:8888::26 update-source Loopback0
 neighbor 90.7.17.53 remote-as 301
 neighbor 113.201.100.8 remote-as 2042
 !
 address-family ipv4
  network 90.7.16.0 mask 255.255.252.0
  neighbor 10.1.1.23 activate
  neighbor 10.1.1.23 route-reflector-client
  neighbor 10.1.1.25 activate
  neighbor 10.1.1.25 route-reflector-client
  neighbor 10.1.1.26 activate
  no neighbor 203A:88A1:A789:1::2:1 activate
  no neighbor 203A:88A1:A789:1::3:1 activate
  no neighbor 203A:88A1:A789:8888::23 activate
  no neighbor 203A:88A1:A789:8888::25 activate
  no neighbor 203A:88A1:A789:8888::26 activate
  neighbor 90.7.17.53 activate
  neighbor 113.201.100.8 activate
 exit-address-family
 !
 address-family ipv6
  network 203A:88A1:A789::/48
  neighbor 203A:88A1:A789:1::2:1 activate
  neighbor 203A:88A1:A789:1::3:1 activate
  neighbor 203A:88A1:A789:8888::23 activate
  neighbor 203A:88A1:A789:8888::23 route-reflector-client
  neighbor 203A:88A1:A789:8888::25 activate
  neighbor 203A:88A1:A789:8888::25 route-reflector-client
  neighbor 203A:88A1:A789:8888::26 activate
 exit-address-family
R24#
````
Настройки RR клиента покажем на R23
````
R23#sh run | sec bgp
router bgp 520
 bgp log-neighbor-changes
 neighbor 10.1.1.24 remote-as 520
 neighbor 10.1.1.24 update-source Loopback0
 neighbor 10.1.1.26 remote-as 520
 neighbor 10.1.1.26 update-source Loopback0
 neighbor 203A:88A1:A789:1::1:1 remote-as 101
 neighbor 203A:88A1:A789:8888::24 remote-as 520
 neighbor 203A:88A1:A789:8888::24 update-source Loopback0
 neighbor 203A:88A1:A789:8888::26 remote-as 520
 neighbor 203A:88A1:A789:8888::26 update-source Loopback0
 neighbor 90.7.17.11 remote-as 101
 !
 address-family ipv4
  neighbor 10.1.1.24 activate
  neighbor 10.1.1.26 activate
  no neighbor 203A:88A1:A789:1::1:1 activate
  no neighbor 203A:88A1:A789:8888::24 activate
  no neighbor 203A:88A1:A789:8888::26 activate
  neighbor 90.7.17.11 activate
 exit-address-family
 !
 address-family ipv6
  neighbor 203A:88A1:A789:1::1:1 activate
  neighbor 203A:88A1:A789:8888::24 activate
  neighbor 203A:88A1:A789:8888::26 activate
 exit-address-family
R23#
````
Покажем установление соседства по iBGP на примере RR R26

![R26 sh_ip_bgp_summ.png](R26%20sh_ip_bgp_summ.png)

а так-же RR клинта на R25

![R25 sh_ip_bgp_summ.png](R25%20sh_ip_bgp_summ.png)

База данных маршрутов BGP для IPv4 на R26

![R26 sh_ip_bgp.png](R26%20sh_ip_bgp.png)

Маршруты полученные по BGP d таблицe маршрутизации IPv4 R26

![R26 sh_ip_route_bgp.png](R26%20sh_ip_route_bgp.png)

Маршруты по iBGP получены и добавлены в таблицу маршрутизации роутера.

Для проверки надежности сети построенной на двух RR проведем имитацию отключения одного из RR.
Выберем RR на R24, так будет нагляднее увидим как изменится список маршрутов в базе BGP на R26, и проверим
наличие IP связанности между сетями офисов Москва и С.-Петербург.

Покажем что на R26 пропало соседство по iBGP с К24.

![R26 sh_ip_bgp_sum_no_R24.png](R26%20sh_ip_bgp_sum_no_R24.png)

Из-за нарушенного соседства пропала часть маршрутов iBGP, ожидаемо

![R26 sh_ip_bgp_noR24.png](R26%20sh_ip_bgp_noR24.png)

Теперь в AS 1001 и 301 можем попасть только через AS101 ISP Киторн.

Проверяем IP связанность между интерфесами Loopback1 роутеров R15 и R18
cо стороны R18.

![R18 ping R15 lo1.png](R18%20ping%20R15%20lo1.png)

Доказали, что сеть в топологии с двумя RR более отказоустойчива и проверили сохранение IP связанности между
сетями офисов Москва и С.-Петербург.

Стоит обратить внимание, что при настройке iBGP в сети Триада атрибут Next hop









