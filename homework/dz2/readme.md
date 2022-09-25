### Лабораторная работа. Просмотр таблицы MAC-адресов коммутатора.


#### Топология.
![](https://sun9-east.userapi.com/sun9-75/s/v1/ig2/KE5pEvQb5RYILP1eN5W8Y18OZVVA4rAZbWQwFzpIBYIyUhfaL4PcvVj2Pol6B7HjUPpO12lwza9XGfYfEEK3VPMu.jpg?size=348x224&quality=96&type=album)

#### Таблица адресации.

| Устройство | Интерфейс |   IP-адрес   | Маска подсети |
|------------|-----------|:------------:|:-------------:|
| S1         | VLAN 1    | 192.168.1.11 | 255.255.255.0 |
| S2         | VLAN 1    | 192.168.1.12 | 255.255.255.0 |
| PC-A       | NIC       | 192.168.1.1  | 255.255.255.0 |
| PC-B       | NIC       | 192.168.1.2  | 255.255.255.0 |

#### Задачи
##### Часть 1. Создание и настройка сети.

##### Часть 2. Изучение таблицы MAC-адресов коммутатора.

#### Решение.

#### Часть 1.

##### Шаг 1. Подключение сети в соответствии с топологией.

![](https://sun9-north.userapi.com/sun9-79/s/v1/ig2/t5xXF9hCtku_6XyKUlHMqcLluJY6zeJWihJpjGXLB12zr5RTxVEVh_-zZpDpbN070MKHza1MUL1znxcdR1JpVXrW.jpg?size=647x389&quality=96&type=album)

##### Шаг 2. Настройка узлов ПК.

Задаем IP-адреса PC-A и PC-B

![](https://sun1.userapi.com/sun1-18/s/v1/ig2/yzCo_2d21biBTG5T3esD22LE4j4WrBcjHwJ9tdAmyEVSLVxIEmxgqR_kNBRQguN35d_6wrlskwqlibvr2646FEpc.jpg?size=704x286&quality=96&type=album)

![](https://sun1.userapi.com/sun1-23/s/v1/ig2/BLadwB8u575FsrkAWi797awiNIJeeqoxg_vjUY6k-ByQxTiB3QLbaWg_t_kmzcHhQ5oqStfGjPMoZETBI-esZs71.jpg?size=697x295&quality=96&type=album)

##### Шаг 3. Выполнение инициализации и перезагрузки коммутаторов.

Вводим команду **erase startup-config**, чтобы удалить файл загрузочной конфигурации из NVRAM. 

Вводим команду **reload** , чтобы перезагрузить коммутаторы.

##### Шаг 4. Настройте базовые параметры каждого коммутатора.

Настраиваем коммутаторы в соответствии с заданием. Тоже самое делаем с PC-B:

![](https://sun1.userapi.com/sun1-30/s/v1/ig2/S7J02VLVJRAPVAa23AVQk928GGEvNE2fDkQmtDZUYawyXcMp6mOaa2UySIrFYoyPvwD6DjJupvuIQomiNJtZN7fS.jpg?size=626x504&quality=96&type=album)

![](https://sun1.userapi.com/sun1-47/s/v1/ig2/3PN363spiJNpSyoYrx-3ObEWJp-PG7MFDwaWO_2VKUVVaAnou8L-P8JCLE0haRIU4TRXyRHgaZ-8MM3B-xptowAE.jpg?size=632x522&quality=96&type=album)

#### Часть 2. изучение таблицы MAC-адресов коммутатора.

##### Шаг 1. Запишите MAC-адреса сетевых устройств.

а. Вводим к командную строку **ipconfig /all**.

MAC-адреса показаны на скриншотах (Physical address):

![](https://sun1.userapi.com/sun1-90/s/v1/ig2/6bOix-Cz-0BxnuQOY2ZfAm7Q7DPBxOGofgdX2uKp94JAgZNeUdY6jsCkfIsjT3ouQJpZOZ2pyItH1vBa-KF7PuXC.jpg?size=691x756&quality=96&type=album)

b. Вводим команду команду **show interface f0/1** через терминал PC-A, чтобы узнать MAC-адрес S1:

![](https://sun1.userapi.com/sun1-13/s/v1/ig2/Bfb4Vyoo46qu-Y7LZcMZXIPj3SCIxdjqLXt6y56-QVjqePhgawJ0AA27YEng99InhE7ZIKpVdYaXIthfJQojnI-s.jpg?size=627x515&quality=96&type=album)

Таким же способом узнаем через терминал PC-B, чтобы узнать MAC-адрес S2:

![](https://sun9-east.userapi.com/sun9-33/s/v1/ig2/iOmKLtixj1sILSwJKqugmMD0sn-YhwNutkIOmxgKRzNgdIaNTvM3Os9tBLfur2wmgkyVk5QeBcXD8hKtW6wTFLSA.jpg?size=631x500&quality=96&type=album)

##### Шаг 2. Просмотр таблицы MAC-адресов коммутатора.

Мы зашли в привелегированный режим на коммутаторе S2 и ввели команду **show mac address-table**:

![](https://sun1.userapi.com/sun1-28/s/v1/ig2/pI9DsG-GV_REScQ2T7LQQ-axCVCq59pQIrVHBwQAv6zvknphNYa54d5gB6Kl7WdZ9yzFzR9aWaE6hnPks-YYojZY.jpg?size=629x171&quality=96&type=album)

У нас в таблице записан MAC-адрес коммутатора S1.

_Если вы не записали МАС-адреса сетевых устройств в шаге 1, как можно определить, каким устройствам принадлежат МАС-адреса, используя только выходные данные команды **show mac address-table**? Работает ли это решение в любой ситуации?_

В большинстве случаев данная команда позволит определить какой MAC-адрес у устройства, но если два коммутатора соединены друг с другом и один пытается "записать" МАС-адрес устройства, которое присоединено к другому коммутатору.

##### Шаг 3. Очищение таблицы МАс-адресов коммутатора S2 и отображение таблицы MAC-адресов.

Команда **clear mac address-table dynamic** очищает динамические адреса из таблицы и после быстрого введения **show mac address-table** мы ничего не увидим.

После того, как мы подождали 10 секунд и ввели заново **show mac address-table** мы увидим снова динамический MAC-адрес.

##### Шаг 4.  С компьютера PC-B отправляем эхо-запросы устройствам в сети и просмотр таблицы МАС-адресов коммутатора.

а. После введения команды **arp -a** в командной строке нам выдало:

![](https://sun1.userapi.com/sun1-15/s/v1/ig2/LqX4JoAeEfpWjvVY7Pz9SvkP4nDjD4NBaUA9dKy_HCpudjrDrPpnBLL3RstFb8dXVQC0BKZISvZv0YE5NQocWLea.jpg?size=655x125&quality=96&type=album)

b. отправляем эхо-запрос на PC-A:

![](https://sun9-east.userapi.com/sun9-21/s/v1/ig2/QUpXFUcJ1Z7WGiySAcD2mQb6t7R7HRLrzlQdTE-OaI-vr09FEzQuUJ0IApAxSCwMcpYqJnTL-K_Iweazj21O-SgN.jpg?size=627x209&quality=96&type=album)

отправялем эхо-запрос на S1 и S2 соответственно: 

![](https://sun9-west.userapi.com/sun9-61/s/v1/ig2/Nl6LQTVP1dN_-GF1iD3YmYOs9PGD92LuIh99sOFAHbQut5MAhF2_w2iqL-Yr6PZ0So2VwMUxUVOY68M8ZQIMMoC7.jpg?size=629x429&quality=96&type=album)
