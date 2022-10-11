### Лабораторная работа. Настройка IPv6-адресов на сетевых устройствах.

#### Топология.

![](https://sun9-west.userapi.com/sun9-2/s/v1/ig2/-p5TpNTRQcQKubHbOglfqsGdqELAjdZq60bTgNfs8W1he9obP99WyA-4bJqWM_88zP5LZFNEyn6uz-afmvu-L5aV.jpg?size=823x129&quality=96&type=album)

#### Таблица адресации.

| Устройство | Интерфейс |     IPv6-адрес     | Длина префикса | Шлюз по умолчанию |
|------------|-----------|:------------------:|:--------------:|-------------------|
| R1         | G0/0/0    | 2001:db8:acad:а::1 | 64             | -                 |
|            | G0/0/1    | 2001:db8:acad:1::1 | 64             | -                 |
| S1         | VLAN 1    | 2001:db8:acad:1::b | 64             | -                 |
| PC-A       | NIC       | 2001:db8:acad:1::3 | 64             | fe80::1           |
| PC-B       | NIC       | 2001:db8:acad:а::3 | 64             | fe80::1           |

#### Задачи

##### Часть 1. Настройка топологии и конфигурация основных параметров маршрутизатора и коммутатора.

##### Часть 2. Ручная настройка IPv6-адресов.

##### Часть 3. Проверка сквозного соединения.

#### Решение.

##### Часть 1. Настройка топологии и конфигурация основных параметров маршрутизатора и коммутатора.

##### Шаг 1. Настройка коммутатора.

а. Задаем имя коммутатору S1 с помощью команды **hostname**.

##### Шаг 2. Настройка маршрутизатора.

a. Задаем имя маршрутизатору R1 с помощью команды **hostname**.

##### Часть 2. Ручная настройка IPv6-адресов.

##### Шаг 1. Назначаем IPv6-адреса интерфейсам Ethernet на R1.

a. Назначаем адрес.

![](https://sun9-north.userapi.com/sun9-80/s/v1/ig2/tBTm2aHmnF_fgaQ2HfLD3cP8Zoc5LhU0p2jPVrzL_ORl373l2CLUAgzYYx-KhL7yZs5sAxUVc_bBoO7yWIHvydOE.jpg?size=636x100&quality=96&type=album)

Назначаем шлюз.

![](https://sun1.userapi.com/sun1-30/s/v1/ig2/S1YupYacyv-6rbCU-hWLHuPEdEv_aRow1N-PFjrY-kwpiWyAiVrVxuLhnsipDOvqy5XkxvN5L9CEo6HyU5wmTL7A.jpg?size=636x100&quality=96&type=album)

Все тоже самое делаем для g0/0/1.

b. С помощью команды **show ipv6 interface brief** проверяем назначение адреса интерфейсу.

![](https://sun9-west.userapi.com/sun9-70/s/v1/ig2/-iLFeuctoqZzpNsKs0C4zKmpdqu_X2nVA6rMHsXUSFaGw8Ybr9eOrqw4v2jDOPf5QDuTkFi9NARD-Hbz8ktI1pdo.jpg?size=622x149&quality=96&type=album)

_Какие группы многоадресной рассылки назначены интерфейсу G0/0/0?_

Это можно узнать с помощью команды **show ipv6 interface g0/0/0**:

![](https://sun1.userapi.com/sun1-16/s/v1/ig2/gF6g_v9TQUpl9C1FSb-ffXXugzW16j0cf7myKsGGT-T_Hhz3D-l1F0r0-HUK5NsyHnIYEPL90zxzWRAyO0h5mDMk.jpg?size=632x217&quality=96&type=album)
