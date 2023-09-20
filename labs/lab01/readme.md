 # Практическая работа №1

## Задание
1. Создание сети и настройка основных параметров устройства
2. Создание сетей VLAN и назначение портов коммутатора
3. Настройка транка 802.1Q между коммутаторами
4. Настройка маршрутизации между VLAN на маршрутизаторе
5. Проверка работы маршрутизации между VLAN.

## Решение
1. [Создание сети и первичная настройка оборудования](https://github.com/Neytrin/Network-ingeneer/edit/main/labs/lab01/readme.md#1-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D0%B5%D1%82%D0%B8-%D0%B8-%D0%BF%D0%B5%D1%80%D0%B2%D0%B8%D1%87%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B1%D0%BE%D1%80%D1%83%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)
2. [Создание сетей VLAN и настройка портов коммутатора на примере Sw1](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/readme.md#2-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D0%B5%D1%82%D0%B5%D0%B9-vlan-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%80%D1%82%D0%BE%D0%B2-%D0%BA%D0%BE%D0%BC%D0%BC%D1%83%D1%82%D0%B0%D1%82%D0%BE%D1%80%D0%B0-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D0%B5-sw1)
3. [Создание маршрутизации между VLAN на роутере R1](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/readme.md#3-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B0%D1%80%D1%88%D1%80%D1%83%D1%82%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-vlan-%D0%BD%D0%B0-%D1%80%D0%BE%D1%83%D1%82%D0%B5%D1%80%D0%B5-r1) 
4. [Проверка работы маршрутизации между VLAN.](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/readme.md#4-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D0%BC%D0%B0%D1%80%D1%88%D1%80%D1%83%D1%82%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-vlan)

## 1. Создание сети и первичная настройка оборудования
Созданная схема приведена на рисунке ![рисунке](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/Graf_shem.PNG)

Таблица адресов
| Device  | Interface | IP address    | Subnet mask   | Default Gateway |
|---------|-----------|---------------|---------------|-----------------|
| R1      | e0/0.3    | 192.168.3.1   | 255.255.255.0 | NA              |
|         | e0/0.4    | 192.168.4.1   | 255.255.255.0 | NA              |
|         | e0/0.1007 | 192.168.107.1 | 255.255.255.0 | NA              |
|         | e0/0.8    | NA            | NA            | NA              |
| Sw1     | VLAN3     | 192.168.3.11  | 255.255.255.0 | 192.168.3.1     |
| Sw2     | VLAN3     | 192.168.3.12  | 255.255.255.0 | 192.168.3.1     |
| VPC_A1  | VPCS1     | 192.168.4.2   | 255.255.255.0 | 192.168.4.1     |
| VPC_A2  | VPCS1     | 192.168.4.3   | 255.255.255.0 | 192.168.4.1     |
| VPC_B1  | VPCS1     | 192.168.107.2 | 255.255.255.0 | 192.168.107.1   |
| VPC_B2  | VPCS1     | 192.168.107.3 | 255.255.255.0 | 192.168.107.1   |
| VPC_B3  | VPCS1     | 192.168.107.4 | 255.255.255.0 | 192.168.107.1   |

Таблица VLAN
| VLAN | Name       | Network          |
|------|------------|------------------|
| 3    | Management | 192.168.3.0/24   |
| 4    | A_Net      | 192.168.4.0/24   |
| 1007 | B_Net      | 192.168.107.0/24 |
| 8    | Native     |                  |




## 2. Создание сетей VLAN и настройка портов коммутатора на примере Sw1

Список созданных VLAN на Sw1 ![](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/%D0%A1%D0%BF%D0%B8%D1%81%D0%BE%D0%BA%20VLAN%20Sw1.PNG) 

Настройка интерфейсов коммутатора Sw1            ![](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/Conf_int_Sw1.PNG)


## 3. Создание маршрутизации между VLAN на роутере R1

Производим настройку Subinterfaces на порту e0/0 маршрутизатора R1  
![](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/conf_R1.PNG)

## 4. Проверка работы маршрутизации между VLAN.

C терминала VPC_B2 принадлежащего сети B_Net производим проверку доступности:
 1. терминала VPC_B1 по адресу 192.168.107.2 в сети B_Net
 2. шлюза по адресу 192.168.107.1
 3. терминала VPC_B1 по адресу 192.168.4.2 в сети B_Net
    
    ![](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab01/ping%20VPC_B2.PNG)
    
Полная настройка оборудования в [каталоге config](https://github.com/Neytrin/Network-ingeneer/tree/main/labs/lab01/config)
