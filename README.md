# Домашнее задание к занятию «3.1. Docker»

## Решения
### Задание 1
 * <a href="https://github.com/Nephedov/8.1.Automated-Testing/blob/main/docker-compose.yml">docker-compose.yml</a> - с PostgreSQL DB.
 * <a href="https://github.com/Nephedov/8.1.Automated-Testing/blob/main/application.properties">application.properties</a> - данные для логина в DB.

<a href="https://github.com/Nephedov/8.1.Automated-Testing">Репозиторий</a> с проектом.
### Задание 2
 * <a href="https://github.com/Nephedov/8.2.Automated-Testing/blob/main/docker-compose.yml">docker-compose.yml</a> - собирающий образ из Dockerfile.
 * <a href="https://github.com/Nephedov/8.2.Automated-Testing/blob/main/Dockerfile">Dockerfile</a> - с настройками порта, командой запуска приложения и образом Java 8.

<a href="https://github.com/Nephedov/8.2.Automated-Testing">Репозиторий</a> с проектом.
## Что было сделано
* Задание 1
  * Реализован <a href="https://github.com/Nephedov/8.1.Automated-Testing/blob/main/docker-compose.yml">docker-compose.yml</a> - разворачивающий PostgreSQL DB.
  * Реализован <a href="https://github.com/Nephedov/8.1.Automated-Testing/blob/main/application.properties">application.properties</a> - с данными логина в DB.
* Задание 2
  * Реализован <a href="https://github.com/Nephedov/8.2.Automated-Testing/blob/main/Dockerfile">Dockerfile</a> с командой запуска тестового приложения на указанном порту и использованием образа Java 8.
  * Реализован <a href="https://github.com/Nephedov/8.2.Automated-Testing/blob/main/docker-compose.yml">docker-compose.yml</a> для сборки образа из Dockerfile.
## Описание Задания №1: PostgreSQL

Вам необходимо подготовить приложение к тестированию на СУБД PostgreSQL. Используйте образ 13-alpine, если он недоступен, то берите последний опубликованный на Docker Hub.

Вам нужно дописать остальные настройки: хост, порт, БД, имя пользователя и пароль.         

Кроме того, вам нужно подготовить файл `docker-compose.yml`, в котором прописать настройки для запуска контейнера PostgreSQL. Всю информацию о его запуске вы найдёте на официальной странице [образа на Docker Hub](https://hub.docker.com/_/postgres). Рекомендуем также изучить документацию по [СУБД PostgreSQL](https://www.postgresql.org/docs/12/index.html) для получения информации о данном продукте. 


В результате выполнения этой задачи вы должны положить в репозиторий следующие три файла (других файлов не должно быть):
* .gitignore
* db-api.jar,
* application.properties,
* docker-compose.yml,
* README.md со скриншотом ответа приложения.

## Описание Задания №2: докеризация приложения (необязательная)

Приложение можно упаковать в Docker-образ, чтобы затем запускать из него контейнеры.

Сделать это, в принципе, несложно: достаточно создать файл `Dockerfile`, в котором описать правила сборки образа.   

Теперь ваша задача — взять готовое приложение для контейнеризации `db-api-for-docker.jar` (оно без зависимостей, никакая СУБД ему не нужна) и упаковать в образ, то есть создать `Dockerfile` и `docker-compose.yml`.

Общие условия:
* приложению для работы нужна Java 8, используйте в качестве базового образа openjdk:8-slim;
* никаких внешних файлов, кроме самого JAR-ника не требуется;
* JAR-ник запускается командой `java -jar db-api-for-docker.jar` и поднимает сервер на порту 9999. Для теста сделайте `GET http://localhost:9999/api/cards`.

В результате выполнения этой задачи вы должны положить в репозиторий следующие файлы:
* .gitignore
* db-api-for-docker.jar,
* Dockerfile,
* docker-compose.yml,
* README.md со скриншотом ответа приложения.
