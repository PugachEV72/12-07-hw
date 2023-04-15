# Домашнее задание к занятию 12.7 «Репликация и масштабирование. Часть 2» - Пугач Евгений.


---

## `Задание 1`

### Ответ:

1. master-slave: преимущество состоит в том, что есть резервный (slave) сервер,  
   который работает только в режиме чтения. При выходе из строя master-сервера,  
   резервный занимает его место. 
2. master-slave-…-slave: уменьшает в разы нагрузку и увеличивает скорость чтения  
   информации пропорционально увеличению количества slave-серверов.
3. master-drbd: по сути, преимущество только в увеличении отказоустойчивости,  
   master-сервер за счет drbd периодически делает копию базы на другом сервере.
4. SAN-кластер: основное приложение и все необходимые для его работы ресурсы,  
   такие как файловые ресурсы или сетевое подключение, определяются в общую кластерную группу,  
   что позволяет увеличить быстродействие, повысить масштабируемость, получить  
   центральное управление и резервирование данных без загрузки локальной сети и серверов.

---

## `Задание 2`

### Ответ:

### Вертикальный шардинг

 Каждая таблица находится на отдельном сервере.

![Скриншот 1](https://github.com/PugachEV72/Images/blob/master/2023-04-15_17-10-58.png)

---

### Горизонтальный шардинг

 Таблица Books разделена на 2 сервера по году написания книги,  
 таблица Users разделена на 2 сервера по данным пользователя и аутентификации пользователя,  
 таблица Stores разделена на 2 сервера по порядковому номеру от 1 до 20 и от 21 до 40  
 (при допущении, что у нас 40 магазинов).

![Скриншот 2](https://github.com/PugachEV72/Images/blob/master/2023-04-15_17-39-09.png)

---
