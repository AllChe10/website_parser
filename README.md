# Books to Scrape — парсер каталога книг

[![Tests](https://github.com/AllChe10/website_parser/actions/workflows/tests.yml/badge.svg)](https://github.com/AllChe10/website_parser/actions/workflows/tests.yml)

Учебный Python-проект для сбора данных из открытого демонстрационного каталога [Books to Scrape](https://books.toscrape.com/).

## Возможности

- Загружает страницы каталога с помощью `requests`.
- Разбирает HTML через `BeautifulSoup`.
- Собирает название книги, цену, рейтинг от 1 до 5 и ссылку на книгу.
- Переходит по страницам каталога с ограничением количества страниц.
- Повторяет запрос до трёх раз при сетевой ошибке.
- Сохраняет результаты в `result.csv`.
- Проверяет парсинг, загрузку страниц и обработку ошибок с помощью `pytest`.
- Запускает тесты в GitHub Actions при push и pull request.

## Технологии

- Python
- requests
- Beautiful Soup 4
- csv из стандартной библиотеки
- pytest
- GitHub Actions

## Установка

```powershell
git clone https://github.com/AllChe10/website_parser.git
Set-Location .\website_parser
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

## Запуск парсера

```powershell
.\.venv\Scripts\python.exe main.py
```

По умолчанию парсер обрабатывает до четырёх страниц. Результат сохраняется в `result.csv` в текущей папке.

## Запуск тестов

```powershell
.\.venv\Scripts\python.exe -m pytest -v
```

## Структура проекта

```text
website_parser/
├── .github/
│   └── workflows/
│       └── tests.yml
├── .gitignore
├── main.py
├── requirements.txt
├── test_parser.py
└── README.md
```

Проект использует демонстрационный сайт Books to Scrape, предназначенный для практики парсинга. Файл `result.csv` создаётся при запуске и не хранится в репозитории.
