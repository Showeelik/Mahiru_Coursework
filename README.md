# Проект Mahiru
# Описание проекта:
### Курсовая работа школы Skypro
Приложение для работы с файлом, в котором находятся данные о транзакциях.
- Представленые задачи:
1. Веб-страницы: События
2. Сервисы: Простой поиск, Поиск переводов физическим лицам
3. Отчеты: Траты по категории

## Установка
1. Клонирование репозитория

```
git clone https://github.com/Showeelik/Mahiru_Coursework.git
```

2. Установите зависимостей проекта

```
poetry install
```

## Работа виджета
Запуск демонстрации работы
```
python main.py
```

## Функционал
Приложение умеет:
- Создавать DataFrame или список словарей на основе Excel файла.
- Фильтровать данные по строке, которая содержится в Категориях или Описании транзакции.
- Фильтровать данные по переводам физическим лицам.
- Фильтровать по дате и показывать вариативный список транзакций(за неделю, за месяц, за год, все транзакции до указанного числа).
- Фильтровать по категории и показывать данные по заданной категории за последние 3 месяца от заданой даты(если дата не передана - за основу берется текущее число).
- Возвращать json ответ с данными о тратах, поступлениях, ценами на заданные котировки и валюты.

## Подробнее о важных функциях
- **views.post_events_response** - Главная функция. Собирает данные(траты, поступления, стоимости валют и акций) из других функций и возвращает готовый JSON ответ
- **services.search_by_persons** - Функция возвращает список операций физическим лицам
- **services.simple_searching** - Функция для поиска операций по полю поиска в описании операции или в категории.
- **reports.spending_by_category** - Функция возвращает траты по заданной категории за последние три месяца (от переданной даты)


## Тесты

Запуск всех тестов
```
pytest
```

Запуск всех тестов с данными о покрытии
```
pytest --cov
```
Запуск всех тестов с данными о покрытии и информацией о непокрытых тестами строках
```
pytest --сov --cov-report term-missing
```

## Конфиденциальные данные
Должны быть в файле .env. Пример данных для работы хранится в .env_template