### Лабораторная работа. Базовая насторойка коммутатора.


#### Топология
![](https://sun9-west.userapi.com/sun9-16/s/v1/ig2/xoNQ7JHXTmcZLcWycbkRm3Kfq1aSyMKC3Mu6BIBzVKp2SxODvbIk16ySxhzw2xhFGorxaj2WonUAD7W817gTuUZR.jpg?size=502x154&quality=96&type=album)

#### Таблица адресации
| Устройство | Интерфейс | IP-адресс / префикс |
|------------|-----------|---------------------|
| S1         | VLAN 1    | 192.168.1.2/24      |
| PC-A       | NIC       | 192.168.1.10/24     |

#### Задачи
##### Часть 1. Проверка конфигурации коммутатора по умолчанию

##### Часть 2. Создание сети и настройка основных параметров устройства 
* Настройте базовые параметры коммутатора.
* Настройте IP-адрес для ПК.

##### Часть 3. Проверка сетевых подлючений 
* Отобразите конфигурацию устройства.
* Протестируйте сквозное соединение, отправив эхо-запрос.
* Протестируйте возможности удаленного управления с помощью Telnet.

#### Решение

##### Часть 1.
##### Шаг 1. Создание сети.
a. С помощью консольного кабеля подключили компьютер и коммутатор.

![](https://sun9-west.userapi.com/sun9-45/s/v1/ig2/brp6JvdaB3SLdkUVLCJRwZqzmFOZoXrZXgqIcjJEqQhKKgPiISvaeCHmTkzYOctJs320Y4uUJqLX8zYUkjZmZrrJ.jpg?size=868x293&quality=96&type=album)

b. Подключились к терминалу.

![](https://sun9-north.userapi.com/sun9-80/s/v1/ig2/p7fFXBKeOfy4uqouPDpN8rHeAyU3_puQE-zOHLNhAbQssCYFz06-9cZ3eJMFwWpc5NbghXncizUqcdEYpuFQrkhK.jpg?size=633x530&quality=96&type=album)

**_Почему нужно использовать консольное подключение для первоначальной настройки коммутатора? Почему нельзя подключиться к коммутатору через Telnet или SSH?_**
Так как коммутатор "из коробки" не имеет никаких базовых настроек, а значит нет никаких данных, то подключиться через Telnet или SSH не получится.
##### Шаг 2. Проверка настроек коммутатора по умолчанию.
а. на данных скриншотах видно, что паролей и IP-адресов нет.

![](https://sun9-east.userapi.com/sun9-76/s/v1/ig2/JGI8bn_o4CQK0BsGljmW_V8SlBCRlFZAlWr5WMJXz3oQGfWkGpMXf_30GwNThSR-_YVvx-d5QD-fd88sLE90P1Kw.jpg?size=636x521&quality=96&type=album)
![](https://sun9-east.userapi.com/sun9-34/s/v1/ig2/mkKkVudcR0kCOf0f71N_w_hWmVTkQV74Mjso-r4a7VLIdGZV-PIxkWVTkBT8tLyjHhp5HevdoVbv58s9mTgpSmos.jpg?size=633x497&quality=96&type=album)

b. На коммутаторе имеется 24 интерфейсов FastEthernet, 2 интерфейса GigabitEthernet. 0-4 и 5-15: диапазоны значений, отображаемых в vty-линиях.

с. После ввода команды **show startup-configuration** появляется сообщение **startup-config is not present**, потому что мы не сохраняли никаких конфигураций.

d. На скриншоте видно, что интерфейс выключен, MAC-адресс виден на второй строчке выполненной команды

![](https://sun9-east.userapi.com/sun9-43/s/v1/ig2/GuM4JL18OTo7snuuYJw4S5owNNQu3rSCZu_dt8a_ZiAGtiRKI5WkSsG6OzVMEg-wvQRateyBtStEc-xZllSGbObX.jpg?size=627x353&quality=96&type=album)

e. После введения команды было получено:

![](https://sun9-north.userapi.com/sun9-86/s/v1/ig2/Z_gGkegJLTzCPoHGiym4zU-LVkVWHxpzrgFD3KkV0D2q1Lma-9CiaDH37aQmF1rs884sE8B6Vt3BrNGG7bMjm1rc.jpg?size=629x126&quality=96&type=album)

f.  После подсоединения кабеля были получены выходные данные:

![](https://sun9-north.userapi.com/sun9-78/s/v1/ig2/pAfPkCdMlq9jttDJ_kzJeWH19m7NOFoYwPi8oL_k6iyKd0XGoZelXtxka9SA3eScO3Pyb9pbCZrDGdX4r3MLIi1m.jpg?size=619x127&quality=96&type=album)

g. После введение команды **show version**, мы можем увидеть версию Cisco IOS: 15.0(2)SE4
Название файла образа системы показано на скрине в самой нижней строчке:

![](https://sun9-east.userapi.com/sun9-43/s/v1/ig2/vrpFdsJPDTaVMGqRqYHVhE8deG_h6yQxLx61FYWw3ZPO5_kezAUkp0NoyPkkv-1uhwH9RM2PHhApvUPu2IbpWRBk.jpg?size=700x126&quality=96&type=album)

Базовый MAC-адресс на второй строчке сверху:

![](https://sun1.userapi.com/sun1-95/s/v1/ig2/x25d9w3K_zvs6E7JZCXvdghnhEKLZNi9RK34ueOKKDeNENQhqsaV6m0O19kR4SM2wdffJJEzEgWwEIOW4VUoSz6q.jpg?size=546x318&quality=96&type=album)

h. из скриншота видно, что интерфейс включен (первая строчка выполненной команды).
чтобы включить интерфейс, нужно использовать команду **no shutdown**.
MAC-адресс представлен на второй строчке выполненной команды.
Настройки дуплекса и скорости: **full-duplex, 100Mb/s**.

![](https://sun1.userapi.com/sun1-22/s/v1/ig2/oAaGPznoiwTuOIbDWxYQAFGx1QCdrOvHbqg8QDcD59EPdFdkc9KXTAlqBhAEaPiy0llyGg0U6Pg9CwHCMssxY9Ko.jpg?size=586x387&quality=96&type=album)

i.  Имя по умолчанию: **default**.
Расположены 24 порта FastEthernet и 2 порта GigabitEthernet.
Статус: **active**.
Тип: **enet**

![](https://sun1.userapi.com/sun1-99/s/v1/ig2/Uf_cqiMX0Ziet6qWGhn6cBC7tXCnZHBaCwPdyExMdYO3SCQf-DlbAeDhyEZWR96ufhLwf-k3QmqFOeauTW8KSBvN.jpg?size=628x491&quality=96&type=album)

j. Присвоенное имя показано на скриншоте:

![](https://sun9-east.userapi.com/sun9-23/s/v1/ig2/4xsvYcBHaiAjfZfieJ8JmYbezh2RFUa5oJRBdPz7YOdQvBqORii2-_JBrJcJTxjTWN5AV6Fgl_3gjNyeBQwBIJ8f.jpg?size=574x130&quality=96&type=album)

##### Часть 2.
##### Шаг 1. Настройка базовых параметров коммутатора.
a. Вводим команды, представленные в методических указаниях.

![](https://sun1.userapi.com/sun1-13/s/v1/ig2/5Oxf6hblaSJ-jT6mJor3g1YNrltg5VyzuT6i-MAKk0CWmdz5HBv--C4EJ0nDeubhWuF3peBDmPy0xcu0GsxKx9oD.jpg?size=628x309&quality=96&type=album)
![](https://sun1.userapi.com/sun1-15/s/v1/ig2/SqeLwIasB-K6WlWip5jxvhUkZJVuQgfWlYBW5z_r6JJ5Na1QfoCrmFZ9W8XgA_2No88G_f8PAhHYujbmMdoeqxJL.jpg?size=636x216&quality=96&type=album)

b. Назначаем IP-адрес интерфейсу SVI на коммутаторе.

![](https://sun9-north.userapi.com/sun9-83/s/v1/ig2/LJ3jhYNzBOoQ-oK4F7cgLW96iXb9EEQCzr1Zr0V2UOFXptdm1-cZiFylN4sgGpb1O5UxFE3G3YKzCTtnh8LiZhNW.jpg?size=627x168&quality=96&type=album)

Затем создаем vlan 99 и подключаем к нему f0/24, g0/1-2:

	S1# configure terminal
	S1(config)# vlan 99
	S1(config-vlan)# exit
	S1(config)# interface range f0/24, g0/1 - 2
	S1(config-if-range)# switchport access vlan 99
	S1(config-if-range)# exit

c. Ограничиваем доступ через порт с помощью пароля и настраиваем vty:

![](https://sun9-west.userapi.com/sun9-48/s/v1/ig2/2OHdcJwwDzHUYvSGTRETcoYZQPNXOhdVov7VMmbdsBMe_lphlO4GvwCMqtPi4ZUOJe1SQrd7Jihqxftc3D2-zeEC.jpg?size=588x325&quality=96&type=album)

**_Для чего нужна команда login?_**

Чтобы удаленно подключить доступ Telnet.

##### Шаг 2. Настройка IP-адреса на компьютере.
![](https://sun1.userapi.com/sun1-18/s/v1/ig2/MZ9x53QrOaZn5zhfaANsqM6uVyyYkWOIZzzN4pTU9QDM7AhuLKZ_dE1idf8bS8BP-a7tiUsBgqVXEMA-l08o9S1P.jpg?size=686x682&quality=96&type=album)

##### Часть 3. Проверка сетевых подключений.
##### Шаг 1. Отображение настроек коммутатора.
![](https://sun9-west.userapi.com/sun9-16/s/v1/ig2/gj5a2ir7XBMaNgN8z7oiSfqbs6zVv0ZdjhY6MBQD4Lwmdj1R4n99fiKBAifGgT5OdergYwMKQgwpOstfI9JsQsCo.jpg?size=628x330&quality=96&type=album)

![](https://sun1.userapi.com/sun1-47/s/v1/ig2/3LQw0_y05NOqdCDLkXAf90X2l6zmoHpNKGBbm-KDHsV9OSEB1oC2gTefkG-hVdqsRcbtCyiXAIsrQ5MmcPLI4quu.jpg?size=631x509&quality=96&type=album)

b. Проверка параметров vlan 1:
Состояние vlan 1 и канального протокола находится на строчке 1 после выполнения команды, а полоса пропускания на 4.

![](https://sun9-east.userapi.com/sun9-34/s/v1/ig2/4I9ZIM2wD0Xql_WY0G0cIkUfFRc8IGhqEThJp3IsnnOkH7GwfFegHokyCCAsPSA6C26FB9Wyzg83f7SK7CO-XFQc.jpg?size=627x369&quality=96&type=album)

##### Шаг 2. Тест сквозного соедниения.

![](https://sun9-east.userapi.com/sun9-22/s/v1/ig2/Cj75ENegYdHl71CvzGqbcV1-8CdR0onpWygxNFrs1Bb22woiBU0Z4oEl4RBPnAmm8rRMZ7wfq-A1Fddpc13azXK7.jpg?size=645x485&quality=96&type=album)

##### Шаг 3. Удаленное управление коммутатором.

![](https://sun1.userapi.com/sun1-92/s/v1/ig2/DdB67896jxt9dxvB7Y48LCiI0ziOI86_kSZkrWLwLs9B8AfQqlW4NzyRtd8otrzYEg1m2kxKM3Y-UUx46Wga8PzU.jpg?size=629x166&quality=96&type=album)

##### Вопросы для самопроверки.
 _Зачем необходимо настраивать пароль VTY для коммутатора?_
 
 Чтобы проключаться к протоколу Telnet.
 
 _Что нужно сделать, чтобы пароли не отправлялись в незашифрованном виде?_
 
 Нужно использовать команду **service password encryption.**
