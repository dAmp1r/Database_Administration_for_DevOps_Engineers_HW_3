# Database_Administration_for_DevOps_Engineers_HW_3

*MySQL - Горбунов Д.Н.*

Задание 1. 

```
version: '3'
services:
  mysql:
    image: mysql:8.0
    container_name: mysql
    restart: unless-stopped
    volumes:
      - /home/gorbunov/hw_mysql/db:/var/lib/mysql
      - /home/gorbunov/hw_mysql/backup:/var/backup_mysql
    environment:
      - MYSQL_ROOT_PASSWORD=123
    ports:
      - "3306:3306"
```                
```mysql> create databases orders;```              
```bash-4.4# mysql -u root -p orders < test_dump.sql ```           
![mysql> status]()               
![show tables]()                    
![price > 300]()            

Задание 2.

```create user 'test'@'localhost' identified with mysql_native_password by '123' with max_queries_per_hour 100 password expire interval 180 day failed_login_attempts 3 attribute '{"first_name": "James", "last_name":"Pretty"}';```                                    
```grant select on orders.* to 'test'@'localhost';```                
```select * from information_schema.user_attributes where user='test';```                
![вывод команды]()             
![show engine]()
![change engine]()

Задание 3.

![show profiles]()                

Задание 4.
