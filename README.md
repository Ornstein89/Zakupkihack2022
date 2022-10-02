# Zakupkihack2022
Решение команды Foxhound на хакатоне Zakupki Hack 2022

# FoxТорг
Площадка для поиска и аналитики по товарам, работам, услгугам (ТРУ) для производителей/поставщиков и заказчиков.

# Описание приложения
Решение команды Foxhound представляет собой веб-приложение для поиска товаров и производителей. Здесь предусмотрены следующие возможности:
1. Поиск товаров в базе данных:
   1. По названию
   2. По категории продукции
   3. По параметрам
2. Поиск товаров и их производителей, используя веб-скраппер
3. Поиск производителей в базе данных по ИНН, названию и/или категории продукции
4. Просмотр производителей для конкретного товара
5. Просмотр товаров, производимых конкретной организацией
6. Добавление/модерирование категорий, их атрибутов и товаров

В приложении предусмотрено две роли пользователей:
- Предприятие. Обладает правами на добавление новой категории (со статусом "Ожидает подтверждения"), добавления товара (с аналогичным статусом) и добавления цены для своего товара. Также пользователь с данной ролью может редактировать стоимость своих товаров.
- Администратор. Может добавлять категории и товары, редактировать их и подтверждать.

# Инструкция по запуску
Демо решение расположено по адресу [](адрес)

Логин: admin

Пароль: 1234

Для запуска локально, см. [Развертывание через docker-compose](#развертывание-через-docker-compose)

# Описание системы
Интерфейс содержит следующие вкладки:
  - [Поиск производителей](#поиск-производителей)
  - [Добавление товаров](#добавление-товаров)
  - [Модерирование товаров](#модерирование-товаров)
  - [Модерирование категорий](#модерирование-категорий)
  - [Просмотр карточки товара](#просмотр-карточки-товара)
  - [Просмотр карточки производителя](#просмотр-карточки-производителя)
  - [Состав команды Foxhound на MoscowCityHack 2022](#состав-команды-foxhound-на-moscowcityhack-2022)

## Поиск товаров
Позволяет искать товары по названию, категории и критериям среди товаров в базе или по введенной строке через скраппер.

## Поиск производителей
Позволяет искать производителей по ИНН, названию и категории, производимой продукции.

## Добавление товаров
Страница, доступная только авторизованному предприятию, где можно добавлять категории, товары и указывать для них цену.

## Модерирование товаров
Страница, доступная только для администратора. Здесь можно также добавлять товары и редактировать их.

## Модерирование категорий
Страница, доступная только для администратора. Здесь можно также добавлять категории и редактировать их.

## Просмотр карточки товара
Карточка товара отображает основную информацию по товару, а также список производителей данного товара.

## Просмотр карточки производителя
В карточке предприятия представлена основная информация о предприяти, а также список производимых им товаров.

# Развертывание через docker-compose
1. Установить [docker](https://docs.docker.com/engine/install/ubuntu/)
2. В папке compose создать файл .env и [заполнить](#описание-переменных-окружения) его в соответствии с примерами
3. Запустить команду docker compose up -d с правами суперпользователя
```bash
sudo docker compose up -d
```
5. Настроить внешний nginx, который будет пересылать все запросы на порт приложения

# Описание переменных окружения

## HTTP_PORT
Файлы: .env

Тип: целое число

Назначение: порт на котором будет крутиться приложение
## JWT_SECRET
Файлы: .env

Тип: строка

Назначение: секретное значение для генерации JWT токенов

# Команды docker-compose 
Все команды необходимо выполнять в папке compose
- Остановить все контейнеры
```bash
sudo docker-compose stop
```
- Перезапустить контейнер
```bash
sudo docker-compose restart {container_name}
```
- Запуск ipython
```bash
sudo docker-compose exec backend ipython
```

# Состав команды Foxhound на MoscowCityHack 2022
  - Недогарок Антон (капитан, ML/NLP) [nk260an@gmail.com]
  - Перевозникова Ксения (web scraping, прикладная python-разработка, ML/NLP)
  - Петров Антон (фронтенд, Vuetify)
  - Романчук Юрий (бекенд, FastAPI)
  - Семенников Кирилл (web scraping, прикладная python-разработка)
