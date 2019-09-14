# Visu+ MySQL Server

## Prerequisites

-  Windows 10 x64
-  [Visu+ 2.50](https://www.phoenixcontact.com/online/portal/ru/?uri=pxc-oc-itemdetail:pid=2988544&&tab=5)
-  [MySQL Installer 8.0.17](https://dev.mysql.com/downloads/installer/)

## MySQL 

### Установка

![image](images/4bc9cba53f7ca7b6f7356f2409a18ec8/image.png)
![image](images/384793b9d4cc5c6e5e860c84b9e216aa/image.png)

**Внимание!** Даже на 64-битных системах Visu+ работает только с **32-битным ODBC коннектором**. Рекомендуется установка [ODBC коннектора версии 5.3](http://dev.mysql.com/downloads/connector/odbc/5.3.html).

### Конфигурация MySQL Server

![image](images/2d9daa1d35ac3923718c77330e15cd81/image.png)
![image](images/f0a3610b71ca6f55a3c3a8b8847625c7/image.png)
![image](images/12596ed794cca41fd2bc6efe977fa9ab/image.png)
![image](images/2cd83c7c9b42c5a26d7318fd783b8d57/image.png)

![image](images/967b164c878ebb124bda0173828db524/image.png)

-  **root password** - пароль для администрирования MySQL Server
-  **user account** - новый аккаунт для пользователя visu (user role **DB Designer**)

Аккаунты в данном примере

| Пользователь | Пароль |
| ------------ | ------ |
| root | rootpassword |
| visu | visupassword |

![image](images/ea16fc1b306040efabac3ed89898ea25/image.png)
![image](images/e8120845045bdc22a5c58370d6041e1e/image.png)

### Создание базы данных

MySQL Workbench позволяет администрировать сервер базы данных с помощью графического интерфейса.

![image](images/8d6362b95ff3d080b5210a2bf54dcf1f/image.png)

Новая база данных создается кнопкой на панели управления, либо SQL командой
```sql
CREATE SCHEMA `visudb` DEFAULT CHARACTER SET utf8 ;
```

![image](images/b0a111d8f9ad1fea0c4b8d95ca87852f/image.png)
![image](images/e0d1e62e3afe678fb8298db8a9da0ef2/image.png)

Не лишним будет установить ее базой данных по-умолчанию

![image](images/156be060dbb4e5d412454aa9496ca4ec/image.png)

## Visu+

### Создание пользователя для доступа к базе данных

![image](images/dd7cc150f4909adace53529f8aa2b611/image.png)

### Historical Log Settings

**Historical Log** используется для хранения алармов (таблица **alarms**), системных сообщений (таблица **sysmsgs**) и сообщений драйверов (таблица **drivers**)

![image](images/955f0985a7cb827f6f4ce0c048012687/image.png)
![image](images/29393ee7822971f6417458439ebf6844/image.png)
![image](images/46dbc378ea9b1b6525481d8bee00c2ed/image.png)
![image](images/12a4b15e3d9703952bed5ce861bce2f4/image.png)    

**Внимание!** На этом этапе начиная с версии Visu+ 2.50 возможна ошибка загрузки ODBC коннектора (system error  182). Рекомендуется установка [ODBC коннектора версии 5.3](http://dev.mysql.com/downloads/connector/odbc/5.3.html).

![image](images/91d2298327ca5cc96636e64f4824e5a4/image.png)

Нажатие на кнопку Create DB Table должно создать таблицы **alarms**, **sysmsgs** и **drivers** в базе данных.

![image](images/3dfc665110f2548cfe4d9e782eca934d/image.png)
![image](images/37a28a76b48ef5961829e7b4b03be42f/image.png)

### Datalogger settings

Тот же коннектор с именем **MySQL ODBC DSN** указываается для всех даталоггеров. Нажатие на кнопку Create DB Table должно создать таблицу с именем даталоггера в базе данных.

![image](images/68eee1280664f42ac43bfc5cd9ae903d/image.png)
![image](images/2d1ff6bc5abc805a35fb8a3214434e27/image.png)

### Использование

#### Log Window

Позволяет отображать данные из таблиц **alarms**, **sysmsgs** и **drivers**

![image](images/fbffa2986a57230c1c4de1e6ceca38b9/image.png)

#### Datalogger Window

Позволяет отображать данные даталоггера в табличном виде

![image](images/ccbaf519ca9051a046233277c6be489e/image.png)

#### Trend

Позволяет отображать данные даталоггера в виде тренда

![image](images/0e139ed1f764e51b7e3151e51292df23/image.png)

#### Запуск

![image](images/540c994dee436d905a468a3f0b255bb5/image.png)