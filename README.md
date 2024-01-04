# Домашнее задание к занятию «Защита хоста» - `Костюк Денис`

## Задание 1
Установите eCryptfs.  
Добавьте пользователя cryptouser.  
Зашифруйте домашний каталог пользователя с помощью eCryptfs.  
В качестве ответа пришлите снимки экрана домашнего каталога пользователя с исходными и зашифрованными данными.  

### Ответ 1
На скриншоте ниже: 
- переключаемся на пользователя cryptouser,  
- создаем в домашнем каталоге этого пользователя файлы file-111 и file-222,  
- просматриваем домашний каталог пользователя cryptouser под пользователем cryptouser и видим созданные файлы file-111 и file-222,  
- переключаемся на пользователя kostyuk,  
- просматриваем домашний каталог пользователя cryptouser под пользователем kostyuk и видим, что данные в каталоге зашифрованы  

![image](https://github.com/denniskostyuk/security1/blob/main/task-1.png)

## Задание 2
Установите поддержку LUKS.  
Создайте небольшой раздел, например, 100 Мб.  
Зашифруйте созданный раздел с помощью LUKS.  
В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.  

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале  

## Задание 3 *
Установите apparmor.  
Повторите эксперимент, указанный в лекции.  
Отключите (удалите) apparmor.  
В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.  
