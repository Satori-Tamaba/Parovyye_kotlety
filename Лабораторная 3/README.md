
Задание 3
Наше задание - сделать так, чтобы после пуша в репозиторий автоматически собирался докер образ и результат сборки сохранялся

Сделаем workflow. Для этого создадим в pycharm файл yml внутри workflow

Наш код:
![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-1.png)

Далее делаем коммит и пуш в наш репозиторий, открываем github и проверяем в разделе Actions появление workflow. Далее нужно чтобы появилась галочка, которая означает об успешной работе.

![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-2.png)

![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-3.png)

Также можно проверить наличие dockerfile на сайте dockerhub

![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/Лабораторная%203/img/img-4.png)

####Вывод

С помощью github actions мы настроили автоматическую сборку и выгрузку docker образа
