# Домашнее задание к занятию "Уязвимости и атаки на информационные системы" - `Скакун Михаил`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`Приведите ответ в свободной форме........`

1. 21/tcp open ftp vsftpd 2.3.4
22/tcp open ssh OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
23/tcp open telnet Linux telnetd
25/tcp open smtp Postfix smtpd
53/tcp open domain ISC BIND 9.4.2
80/tcp open http Apache httpd 2.2.8 ((Ubuntu) DAV/2)
111/tcp open rpcbind 2 (rpcbind V2 protocol)
139/tcp open netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp open microsoft-ds Samba smbd 3.0.20-Debian
512/tcp open exec netkit-rsh rexecd
513/tcp open login netkit-rsh rlogind
514/tcp open shell netkit-rsh rshd
1099/tcp open rmiregistry GNU RMI registry
1524/tcp open ingreslock ingres
2049/tcp open nfs 2-4 nfsd
3306/tcp open mysql MySQL 5.0.51a-3ubuntu5
3632/tcp open distccd distccd v1 ((GNU) 4.2.4 (Ubuntu 4.2.4-1ubuntu4))
5432/tcp open postgresql PostgreSQL 8.3.0
5900/tcp open vnc VNC 4.1.2 (protocol 3.8)
6667/tcp open irc ngircd
8009/tcp open ajp13 Apache Tomcat/6.0.16
8180/tcp open unknown Jetty 6.1.12
8787/tcp open drda IBM DB2
39292/tcp open status 1 (rpcbind V2 protocol)
2. vsftpd 2.3.4 Backdoor Command Execution:

Сетевая служба: vsftpd (FTP server)
Версия: 2.3.4
Уязвимость: vsftpd 2.3.4 содержит бэкдор, который позволяет злоумышленнику выполнить произвольные команды на сервере. Этот бэкдор был внедрен в скомпрометированную версию vsftpd и распространялся в течение короткого периода времени.

Samba 3.0.20 Remote Code Execution:

Сетевая служба: Samba (SMB/CIFS file sharing)
Версия: 3.0.20
Уязвимость: Samba 3.0.20 содержит уязвимость, позволяющую злоумышленнику выполнить произвольный код на сервере, отправив специально сформированный запрос.


DistCC Daemon Command Execution:

Сетевая служба: distccd (Distributed Compiler)
Версия: distccd v1 ((GNU) 4.2.4 (Ubuntu 4.2.4-1ubuntu4))
Уязвимость: distccd позволяет неавторизованным пользователям выполнять произвольные команды на сервере. Это связано с отсутствием аутентификации и проверки входящих соединений.
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 1](ссылка на скриншот 1)`


---

### Задание 2

`Приведите ответ в свободной форме........`

1. SYN Scan:
Отправляет SYN-пакеты.
Ждет ответа SYN/ACK (порт открыт), RST (порт закрыт) или отсутствие ответа (отфильтрован).
Полуоткрытое сканирование (не устанавливает полное TCP-соединение).
Минимальный сетевой след (менее заметен).
Требует привилегий root.
FIN Scan:
Отправляет FIN-пакеты.
Ожидает RST (порт закрыт).
Отсутствие ответа (порт открыт/отфильтрован)
Используется для обхода некоторых файерволлов.
Требует привилегий root.
Xmas Scan:
Отправляет пакеты с установленными флагами FIN, PSH и URG.
Логика ответа аналогична FIN-скану.
Попытка обойти файерволлы.
Требует привилегий root.
UDP Scan:
Отправляет UDP-пакеты.
Ожидает ICMP “Port Unreachable” (порт закрыт).
Отсутствие ответа (порт открыт/отфильтрован).
Более медленный и менее надежный, чем TCP-сканирование.
2. Ответ сервера зависит от режима сканирования и состояния порта:

Открытый порт:
SYN Scan: Отвечает SYN/ACK.
FIN, Xmas Scan: Ничего не отвечает (или может быть отправлен RST в старых ОС).
UDP Scan: Зависит от службы. Может вообще не отвечать.
Закрытый порт:
SYN Scan: Отвечает RST.
FIN, Xmas Scan: Отвечает RST.
UDP Scan: Отвечает ICMP “Port Unreachable”.
Отфильтрованный порт (файерволл):
SYN Scan: Ничего не отвечает (или может быть отправлен RST).
FIN, Xmas Scan: Ничего не отвечает.
UDP Scan: Ничего не отвечает (или может быть отправлен ICMP “Time Exceeded”).
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 2](ссылка на скриншот 2)`


---

### Задание 3

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

### Задание 4

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`
