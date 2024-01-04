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

![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-1.png)

## Задание 2
Установите поддержку LUKS.  
Создайте небольшой раздел, например, 100 Мб.  
Зашифруйте созданный раздел с помощью LUKS.  
В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.  

### Ответ 2

На входе имеем вот такие устройства и разделы:  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-21.png)

Задача - зашифровать раздел sdb1 с помощью LUKS.  

Далее поэтапно: подготавливаем/монтируем/форматируем раздел...  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-22.png)

После того, как поработали с зашифрованным разделом - завершаем работу:
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-23.png)

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале  

## Задание 3 *
Установите apparmor.  
Повторите эксперимент, указанный в лекции.  
Отключите (удалите) apparmor.  
В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.  

### Ответ 3
(Выполнить задание 3 получилось только на 16-й Убунте. На более поздних версиях ping, переименованный в man, не работал, а на более ранних были проблемы с установкой AppArmor)  

Делаем копию man, потом ping с переименованием в man копируем на место man и убеждаемся, что теперь man работает как ping:  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-31.png)

Далее устанавливаем AppArmor:  
sudo apt install apparmor-profiles apparmor-utils apparmor-profiles-extra  

Смотрим статус:  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-32.png)  

И видим, что загружено 70 профилей, среди которых нет профиля man.  
В этом также можно убедиться, попытавшись перевести профиль man в режим enforce и получив ошибку:  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-33.png)   

При этом в пакете apparmor-profiles-extra профиль man присутствует:  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-34.png)  

Поэтому копируем профиль man в /etc/apparmor.d/  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-35.png)   

После этого повторяем эксперимент из лекции:  
![image](https://github.com/denniskostyuk/hostprotection/blob/main/task-36.png) 
