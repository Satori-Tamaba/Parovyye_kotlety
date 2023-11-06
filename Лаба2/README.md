# Лабораторная работа 2
## Цель работы
Написать два Dockerfile – плохой и хороший. Плохой должен запускаться и работать корректно, но в нём должно быть не менее 3 “bad practices”. В хорошем Dockerfile они должны быть исправлены. В Readme описать все плохие практики из кода Dockerfile и почему они плохие, как они были исправлены в хорошем  Dockerfile, а также две плохие практики по использованию этого контейнера

Для примера будем контейнеризировать веб-приложение на Flask, которое открывает страничку с текстом "Это для крутой лабы"
## Хорошая практика

### Хорошая практика №1: Использование минимального базового образа Python

    FROM python:3.8-slim

### Хорошая практика №2: Установка зависимостей с использованием файла зависимостей

    WORKDIR /app
    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt

### Хорошая практика №3: Копирование только необходимых файлов

    COPY app.py /app/

### Хорошая практика №4: Запуск приложения от непривилегированного пользователя

    USER nobody
    
    CMD ["python", "app.py"]

### В общем виде: 
  

    FROM python:3.8-slim  
      
    WORKDIR /app  
    COPY requirements.txt .  
    RUN pip install --no-cache-dir -r requirements.txt  
      
    COPY app.py /app/  
    EXPOSE 5000  
      
    USER nobody  
      
    CMD ["python", "app.py"]

## Плохая практика
### Плохая практика №1: Использование последней версии базового образа Python без явного указания версии.  

    FROM python:latest  
    RUN pip install Flask  

### Плохая практика №2: Копирование всего приложения в одном слое  

    WORKDIR /app  
    COPY . /app/  
      
    EXPOSE 5000  
      

### Плохая практика №3 Запуск от суперпользователя  

    USER root  
      
    CMD ["python", "app.py"]

### В общем виде:

    FROM python:latest  
    RUN pip install Flask  
    WORKDIR /app  
    COPY . /app/  
      
    EXPOSE 5000  
      
    USER root  
      
    CMD ["python", "app.py"]

# Итог 
#### Запуск :  `run -p 5000:5000 my_image`
Хороший докер: ![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/%D0%9B%D0%B0%D0%B1%D0%B02/images/%D1%85%D0%BE%D1%80%D0%BE%D1%88.png?raw=true)

Плохой докер:![Image alt](https://github.com/Satori-Tamaba/Parovyye_kotlety/blob/main/%D0%9B%D0%B0%D0%B1%D0%B02/images/%D0%BF%D0%BB%D0%BE%D1%85.png)


