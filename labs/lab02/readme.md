# Практическое задание №2

[1. Создание сети и настройка основных параметров устройства](https://github.com/Neytrin/Network-ingeneer/blob/main/labs/lab02/readme.md#1-%D0%B2-%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B5-eve-ng-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B5%D0%BC-%D1%81%D0%B5%D1%82%D0%B5%D0%B2%D1%8B%D0%B5-%D1%8D%D0%BB%D0%B5%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B8-%D1%81%D0%BE%D0%B5%D0%B4%D0%B8%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%BD%D0%BE-%D1%81-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F%D0%BC%D0%B8-%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D1%8F-%D1%80%D0%B8%D1%81%D1%83%D0%BD%D0%BE%D0%BA-1)

[2. Выбор корневого моста]()

[3. Наблюдение за процессом выбора протоколом STP порта, исходя из стоимости портов]()

[4. Наблюдение за процессом выбора протоколом STP порта, исходя из приоритета портов]()

## 1. В программе EVE-NG создаем сетевые элементы и соединения согласно с условиями задания. [(рисунок 1)]
![Shem_lab02_EVE.PNG](Shem_lab02_EVE.PNG)
производим настройку коммутаторов
отключаем поиcк DNS командой _no ip domain-lookup_

присвоение имени коммутатору _hostname Sw1_

назначаем **class**  в качестве зашифрованного пароля доступа к привилигированному режиму _enable secret class_

назначаем **cisco** в качестве паролей консоли и VTY

назначаем logging synchronous для консоли

настраиваем баннерное сообщение дня MOTD, команда _banner motd C Attention!!! You bear full responsibility for interfering with the operation of the equipment. C_

задаем IP-address, указанный в таблице адресации для VLAN1 на всех коммутаторах

копируем текущую конфигурацию в файл загрузочной конфигурации, команда _copy running-config startup-config_

Результат первичной конфигурации на примере Sw1
[Initial settings](Initial%20settings)









