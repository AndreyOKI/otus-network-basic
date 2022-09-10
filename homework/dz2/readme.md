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

##### Шаг 1. Запишите MAC-адреса сетевых устрйоств.

а. Вводим к командную строку **ipconfig /all**.

MAC-адреса показаны на скриншотах (Physical address):

![](https://sun1.userapi.com/sun1-90/s/v1/ig2/6bOix-Cz-0BxnuQOY2ZfAm7Q7DPBxOGofgdX2uKp94JAgZNeUdY6jsCkfIsjT3ouQJpZOZ2pyItH1vBa-KF7PuXC.jpg?size=691x756&quality=96&type=album)

b. Вводим команду команду **show interface f0/1** через терминал PC-A, чтобы узнать MAC-адрес S1:

![](https://sun1.userapi.com/sun1-13/s/v1/ig2/Bfb4Vyoo46qu-Y7LZcMZXIPj3SCIxdjqLXt6y56-QVjqePhgawJ0AA27YEng99InhE7ZIKpVdYaXIthfJQojnI-s.jpg?size=627x515&quality=96&type=album)

Таким же способом узнаем через терминал PC-B, чтобы узнать MAC-адрес S2:

![](https://sun9-east.userapi.com/sun9-33/s/v1/ig2/iOmKLtixj1sILSwJKqugmMD0sn-YhwNutkIOmxgKRzNgdIaNTvM3Os9tBLfur2wmgkyVk5QeBcXD8hKtW6wTFLSA.jpg?size=631x500&quality=96&type=album)
