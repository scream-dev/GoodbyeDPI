# Better GoodbyeDPI
At the moment, the original GoodbyeDPI is not updated, and I, the original program, am doing this: https://github.com/ValdikSS/GoodbyeDPI

На данный момент оригинальный GoodbyeDPI не обновляется, и этим занимаюсь я, оригинал программы: https://github.com/ValdikSS/GoodbyeDPI

# Works with
## - YouTube
## - Discord
## - More sites are written in russia-blacklist.txt 

# Job guarantee
The program is guaranteed to work on Windows 7, 8, 8.1, 10, 11. If your system is not in the list, put one of the specified. 
_____________________________________________________
Работа программы гарантируется на Windows 7, 8, 8.1, 10, 11. Если вашей системы нет в списке, поставьте одну из указанных. 

# How it works
### Passive DPI
Most passive DPI servers send a 302 HTTP redirect request if you are trying to access a blocked website over HTTP, and a TCP reset request in the case of HTTPS, faster than the target website. Packets sent by DPI \ servers usually contain an IP identification field equal to 0x0000 or 0x0001, as in the case of Russian providers. These packages, if they redirect you to another website(the censorship page), are blocked by GoodbyeDPI.

### Active DPI
Cheating Active DPI is harder. Currently, the software uses 7 ways to bypass Active DPI:

### Fragmentation of the first data packet at the TCP level
TCP-level fragmentation for persistent HTTP \ sessions (keep-alive)

### Replacing the Host header with hoSt
Removing a space between the header name and the value in the Host header
Adding extra space between the HTTP \ method (GET, POST, etc.).\ ) AND URI
Case of mixing host header values
Sending fake HTTP / HTTPS\packets with a low lifetime, invalid checksum, or invalid TCP sequence / acknowledgment numbers to trick DPI and prevent them from being delivered to the recipient
These methods should not disrupt the operation of websites, since they are fully compatible with the TCP and HTTP standards, but they are sufficient to prevent DPI data classification and circumvent censorship. The extra space may interfere with the operation of some websites, although this is allowed according to the HTTP/1.1 \ specification(see. 19.3 "Tolerant apps").

This software is designed to bypass deep packet inspection systems that are used by many Internet service providers to block access to certain websites.

It handles DPIs connected via optical splitter or port mirroring (passive DPI), which do not block any data, but simply respond faster than the requested destination, and active DPI connected in series.

The program loads the WinDivert driver, which uses the Windows filtering platform to install filters and redirect packets to \ user space. It runs as long as the console window is open, and ends when the\window is closed.
____________________________________________________________________________________
### Пассивный DPI
Большинство пассивных DPI-серверов отправляют HTTP-запрос 302 на переадресацию, если вы пытаетесь получить доступ к заблокированному веб-сайту по протоколу HTTP, и TCP-запрос на сброс в случае HTTPS, быстрее, чем целевой веб-сайт. Пакеты, отправляемые DPI-серверами, обычно содержат поле идентификации IP, равное 0x0000 или 0x0001, как в случае с российскими провайдерами. Эти пакеты, если они перенаправляют вас на другой веб-сайт (страницу цензуры), блокируются GoodbyeDPI.

### Активный DPI
Обмануть Active DPI сложнее. В настоящее время программное обеспечение использует 7 способов обхода Active DPI:

### Фрагментация первого пакета данных на уровне TCP
Фрагментация на уровне TCP для постоянных HTTP-сессий (keep-alive)

### Замена Host заголовка на hoSt
Удаление пробела между именем заголовка и значением в Host заголовке
Добавление дополнительного пространства между HTTP-методом (GET, POST и т.д.) И URI
Случай смешивания значений заголовка хоста
Отправка поддельных HTTP/HTTPS-пакетов с низким значением времени жизни, неверной контрольной суммой или неверными порядковыми номерами/номерами подтверждения TCP, чтобы обмануть DPI и предотвратить их доставку получателю
Эти методы не должны нарушать работу веб-сайтов, поскольку они полностью совместимы со стандартами TCP и HTTP, но их достаточно для предотвращения классификации данных DPI и обхода цензуры. Дополнительное пространство может нарушить работу некоторых веб-сайтов, хотя это допустимо согласно спецификации HTTP/1.1 (см. 19.3 «Толерантные приложения»).

Это программное обеспечение предназначено для обхода систем глубокой проверки пакетов, которые используются многими интернет-провайдерами для блокировки доступа к определённым веб-сайтам.

Она обрабатывает DPI, подключенные с помощью оптического разветвителя или зеркального отображения портов (пассивный DPI), которые не блокируют какие-либо данные, а просто отвечают быстрее, чем запрошенный адресат, и активный DPI, подключенный последовательно.

Программа загружает драйвер WinDivert, который использует платформу фильтрации Windows для установки фильтров и перенаправления пакетов в пользовательское пространство. Она работает до тех пор, пока открыто окно консоли, и завершается при закрытии окна.
