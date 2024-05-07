# "Домашнее задание к занятию «Уязвимости и атаки на информационные системы»" - Файзиев Давлат.

### Задание 1

Скачайте и установите виртуальную машину Metasploitable: https://sourceforge.net/projects/metasploitable/.

Это типовая ОС для экспериментов в области информационной безопасности, с которой следует начать при анализе уязвимостей.

Просканируйте эту виртуальную машину, используя **nmap**.

Попробуйте найти уязвимости, которым подвержена эта виртуальная машина.

Сами уязвимости можно поискать на сайте https://www.exploit-db.com/.

Для этого нужно в поиске ввести название сетевой службы, обнаруженной на атакуемой машине, и выбрать подходящие по версии уязвимости.

Ответьте на следующие вопросы:

- Какие сетевые службы в ней разрешены?
- Какие уязвимости были вами обнаружены? (список со ссылками: достаточно трёх уязвимостей)
 
*Приведите ответ в свободной форме.*

### Решение 1

Разрешены следующие сетевые службы:

  PORT     STATE SERVICE
* 21/tcp   open  ftp
* 22/tcp   open  ssh
* 23/tcp   open  telnet
* 25/tcp   open  smtp
* 53/tcp   open  domain
* 80/tcp   open  http
* 111/tcp  open  rpcbind
* 139/tcp  open  netbios-ssn
* 445/tcp  open  microsoft-ds
* 512/tcp  open  exec
* 513/tcp  open  login
* 514/tcp  open  shell
* 1099/tcp open  rmiregistry
* 1524/tcp open  ingreslock
* 2049/tcp open  nfs
* 2121/tcp open  ccproxy-ftp
* 3306/tcp open  mysql
* 5432/tcp open  postgresql
* 5900/tcp open  vnc
* 6000/tcp open  X11
* 6667/tcp open  irc
* 8009/tcp open  ajp13
* 8180/tcp open  unknown

Были обнаружены следующие уязвимости:
1. [vsftpd 2.3.4 - Backdoor Command Execution](https://www.exploit-db.com/exploits/49757). 
2. [OpenSSH < 7.7 - User Enumeration (2)](https://www.exploit-db.com/exploits/45939). 
3. [MySQL 5.0.x - IF Query Handling Remote Denial of Service](https://www.exploit-db.com/exploits/30020).

---
### Задание 2

Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.

Запишите сеансы сканирования в Wireshark.

Ответьте на следующие вопросы:

- Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?
- Как отвечает сервер?

*Приведите ответ в свободной форме.*

### Решение 2

- С точки зрения сетевого трафика эти режимы отличаются типами используемых протоколов передачи и применяемыми флагами в заголовках. 
- Сервер отвечает подтверждением (при доступности порта) или отказом (при недоступности порта).
---
