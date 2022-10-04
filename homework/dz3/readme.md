### Лабораторная работа. Настройка IPv6-адресов на сетевых устройствах.

#### Топология.

![](https://sun9-west.userapi.com/sun9-2/s/v1/ig2/-p5TpNTRQcQKubHbOglfqsGdqELAjdZq60bTgNfs8W1he9obP99WyA-4bJqWM_88zP5LZFNEyn6uz-afmvu-L5aV.jpg?size=823x129&quality=96&type=album)

#### Таблица адресации.

| Устройство | Интерфейс |     IPv6-адрес     | Длина префикса | Шлюз по умолчанию |
|------------|-----------|:------------------:|:--------------:|-------------------|
| R1         | G0/0/0    | 2001:db8:acad:a::1 | 64             | -                 |
|            | G0/0/1    | 2001:db8:acad:1::1 | 64             | -                 |
| S1         | VLAN 1    | 2001:db8:acad:1::b | 64             | -                 |
| PC-A       | NIC       | 2001:db8:acad:1::3 | 64             | fe80::1           |
| PC-B       | NIC       | 2001:db8:acad:a::3 | 64             | fe80::1           |
