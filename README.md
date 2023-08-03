# Домашнее задание к занятию "`Кластеризация и балансировка нагрузки`" - `Стрекозов Владимир`

### Задание 1
* Запустите два simple python сервера на своей виртуальной машине на разных портах
* Установите и настройте HAProxy, воспользуйтесь материалами к лекции по ссылке
* Настройте балансировку Round-robin на 4 уровне.
* На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy.
### Решение
(Конфигурационный файл HAProxy)[https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/haproxy_L4.cfg]  
![Запрос к HAProxy](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z1_1.PNG])  
![Часть лога сервера с получением запроса и перенаправлением на разные сервера](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z1_2.PNG)  
### Задание 2
* Запустите три simple python сервера на своей виртуальной машине на разных портах
* Настройте балансировку Weighted Round Robin на 7 уровне, чтобы первый сервер имел вес 2, второй - 3, а третий - 4
* HAproxy должен балансировать только тот http-трафик, который адресован домену example.local
* На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него.
### Решение
(Конфигурационный файл HAProxy)[https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/haproxy_L7.cfg]  
![Запрос к HAProxy с использованием домена](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z2_1.PNG)  
![Запрос к HAProxy без использования домена](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z2_2.PNG)  

---
## Дополнительные задания (со звездочкой*)

### Задание 3
* Настройте связку HAProxy + Nginx как было показано на лекции.
* Настройте Nginx так, чтобы файлы .jpg выдавались самим Nginx (предварительно разместите несколько тестовых картинок в директории /var/www/), а остальные запросы переадресовывались на HAProxy, который в свою очередь переадресовывал их на два Simple Python server.
* На проверку направьте конфигурационные файлы nginx, HAProxy, скриншоты с запросами jpg картинок и других файлов на Simple Python Server, демонстрирующие корректную настройку.
### Решение
(Конфигурационный файл nginx в conf.d)[https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/nginx_.jpg%2BHAProxy_L4-balancing.conf]  
(Конфигурационный файл nginx основной)[https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/nginx_main.conf]  
(Конфигурационный файл HAPRoxy такой же как в З1)[https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/haproxy_L4.cfg]  
![Скриншот с запросом картинки, который обрабатывается сервером nginx](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z3_1.PNG)  
![Скриншот без запроса картинки, который перенаправляется на HAProxy](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z3_2.PNG)  
### Задание 4
* Запустите 4 simple python сервера на разных портах.
* Первые два сервера будут выдавать страницу index.html вашего сайта example1.local (в файле index.html напишите example1.local)
* Вторые два сервера будут выдавать страницу index.html вашего сайта example2.local (в файле index.html напишите example2.local)
* Настройте два бэкенда HAProxy
* Настройте фронтенд HAProxy так, чтобы в зависимости от запрашиваемого сайта example1.local или example2.local запросы перенаправлялись на разные бэкенды HAProxy
* На проверку направьте конфигурационный файл HAProxy, скриншоты, демонстрирующие запросы к разным фронтендам и ответам от разных бэкендов.
### Решение
(Конфигурационный файл HAProxy)[https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/haproxy_L7_double_back-front.conf]  
![Скриншот запроса к размы фронтэндам и ответ от разных бэкэндов](https://github.com/Svalker1989/Clusterization-Load_Balacing/blob/main/Z4.PNG)  
