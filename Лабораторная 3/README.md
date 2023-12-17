
# Задание 3
Наше задание - сделать так, чтобы после пуша в репозиторий автоматически собирался докер образ и результат сборки сохранялся

Сделаем workflow. Для этого создадим в pycharm файл yml внутри workflow

Наш код:
![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-1.png)

-Checkout Code:
Использует действие actions/checkout, чтобы получить код из репозитория.
Далее делаем коммит и пуш в наш репозиторий, открываем github и проверяем в разделе Actions появление workflow. Далее нужно чтобы появилась галочка, которая означает об успешной работе.

-Build Docker Image:
Выполняет команду для сборки Docker-образа с использованием указанного Dockerfile

-Run Docker Image:
Запускает созданный Docker-образ

-Login to Dockerhub:
Авторизуется на Dockerhub, используя предоставленное имя пользователя 

-Create Tag for Docker:
Создает новый тег для Docker-образа

-Push Image to Dockerhub:
Отправляет Docker-образ с созданным тегом на Dockerhub 

![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-2.png)

![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-3.png)

Также можно проверить наличие dockerfile на сайте dockerhub

![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-4.png)

# Вывод

С помощью github actions мы настроили автоматическую сборку и выгрузку docker образа
