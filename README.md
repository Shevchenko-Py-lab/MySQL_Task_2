# MySQL_Task_2
#1 my.cnf создал, положил в папку Windows

C:\Users\zekto>mysql
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 21
Server version: 8.0.26 MySQL Community Server - GPL

Copyright (c) 2000, 2021, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>exit

Задание 2: Создайте базу данных example, разместите в ней таблицу users, состоящую из двух столбцов, числового id и строкового name. 
Task_2_2.sql в master

Задание 3: Создайте дамп базы данных example из предыдущего задания, разверните содержимое дампа в новую базу данных sample.
C:\Program Files\MySQL\MySQL Server 8.0\bin>mysqldump -u root -p example > C:\MySQL_Dump\sample.sql
Enter password: ********

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u root -p

mysql> CREATE DATABASE sample;
Query OK, 1 row affected (0.00 sec)
mysql> exit

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u root -p sample < C:\MySQL_Dump\sample.sql
Enter password: ********

mysql> DESCRIBE sample.users;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| id    | int          | YES  |     | NULL    |       |
| name  | varchar(100) | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
2 rows in set (0.00 sec)

Задание №4:
C:\Program Files\MySQL\MySQL Server 8.0\bin>mysqldump -u root -p --where="true limit 100" mysql help_keyword > C:\MySQL_Dump\fourthtask.sql
Enter password: ********

mysql> CREATE DATABASE test_100;

А вот записать в другую БД не получилось, ошибка 3723.
