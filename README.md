# DZ_3_ZFS


РАБОТА СО СНАПШОТАМИ, ПОИСК СООБЩЕНИЯ:

скачиваем файл:

root@koka-pc:~# wget -O otus_task2.file --no-check-certificate https://drive.usercontent.google.com/download?id=1wgxjih8YZ-cqLqaZVa0lA3h3Y029c3oI&export=download


root@koka-pc:~# file otus_task2.file
otus_task2.file: ZFS snapshot (little-endian machine), version 17, type: ZFS, destination GUID: FFFFFFB5 FFFFFFB7 FFFFFFB8 78 35 30 FFFFFF92 FFFFFFFC, name: 'otus/test@today'


восстановление файловой системы из снимка:

ZFS receive — команда, которая создаёт снимки файловой системы на основе потока данных, предоставляемого на стандартном входе. Если получен полный поток, то создаётся и новая файловая система.

root@koka-pc:~# zfs receive otus/test@today < otus_task2.file


поиск файла:

root@koka-pc:/otus/test# find -name "secret_message"
./task1/file_mess/secret_message

root@koka-pc:/otus/test# cat task1/file_mess/secret_message
https://otus.ru/lessons/linux-hl/

