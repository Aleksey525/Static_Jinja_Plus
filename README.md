# Static_Jinja_Plus Docker

Репозиторий содержит Dockerfile для сборки и запуска приложения [Static_Jinja_Plus.
](https://github.com/MrDave/StaticJinjaPlus)

## Как собрать образ

Перед сборкой образа требуется установить [Docker](https://www.docker.com/get-started/) и зарегистрироваться на [DockerHub](https://hub.docker.com/).

Далее скачать репозиторий с кодом, выбрать базовый образ `ubuntu` или `python-slim` и перейти в соответствующую папку:

```sh
cd python_dockerfile
```
или

```sh
cd ubuntu_dockerfile
```
Сборка Docker образа для разных версий приложения:

```sh
docker build --build-arg VERSION=0.1.0 -t yourusername/staticjinjaplus:0.1.0 .
```
или 

```sh
docker build --build-arg VERSION=0.1.1 -t yourusername/staticjinjaplus:0.1.1 .
```
## Как запустить контейнер

Для запуска контейнера использовать команду с указанием нужной версии:

```sh
docker run --rm -it yourusername/staticjinjaplus:0.1.1
```

## Цели проекта

Код написан в учебных целях — это урок в курсе по Python и веб-разработке на сайте [Devman.org](https://dvmn.org).









