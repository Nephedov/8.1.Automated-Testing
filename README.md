# Домашнее задание к занятию «3.1. Docker»

## Решения
### Задание 1
 * <a href="https://github.com/Nephedov/8.1.Automated-Testing/blob/80336577edd74a888ede06eddbd309445d83112d/docker-compose.yml">docker-compose.yml</a>.
 * <a href="https://github.com/Nephedov/8.1.Automated-Testing/blob/80336577edd74a888ede06eddbd309445d83112d/application.properties">application.properties</a>.
### Задание 2
 * <a href="https://github.com/Nephedov/8.2.Automated-Testing/blob/76996bf175daca610c78f04cd205b918ba96ab58/docker-compose.yml">docker-compose.yml</a>.
 * <a href="https://github.com/Nephedov/8.2.Automated-Testing/blob/76996bf175daca610c78f04cd205b918ba96ab58/Dockerfile">Dockerfile</a>.
## Что было сделано
* Задание 1
  * Реализован docker-compose.yml.
  * Реализован application.properties.
* Задание 2
  * Реализован Dockerfile.
  * Реализован docker-compose.yml для сборки образа из Dockerfile.
## Задача №1: PostgreSQL

Вам необходимо подготовить приложение к тестированию на СУБД PostgreSQL. Используйте образ 13-alpine, если он недоступен, то берите последний опубликованный на Docker Hub.

Вам нужно дописать остальные настройки: хост, порт, БД, имя пользователя и пароль.         

Кроме того, вам нужно подготовить файл `docker-compose.yml`, в котором прописать настройки для запуска контейнера PostgreSQL. Всю информацию о его запуске вы найдёте на официальной странице [образа на Docker Hub](https://hub.docker.com/_/postgres). Рекомендуем также изучить документацию по [СУБД PostgreSQL](https://www.postgresql.org/docs/12/index.html) для получения информации о данном продукте. 


В результате выполнения этой задачи вы должны положить в репозиторий следующие три файла (других файлов не должно быть):
* .gitignore
* db-api.jar,
* application.properties,
* docker-compose.yml,
* README.md со скриншотом ответа приложения.

## Задача №2: докеризация приложения (необязательная)

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
