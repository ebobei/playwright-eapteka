## Требования

Для запуска тестов требуется последняя версия Node.js (20.x).
Перед запуском тестов необходимо создать файл с переменными окружения `.env`, содержащий данные из описания `.env_example`.

## Запуск в Docker

Если ранее тесты запускались на локальной машине, то перед первым запуском требуется удалить директорию `node_modules`.
При первом запуске будут установлены необходимые зависимости, что может занять некоторое время.
После запуска управление передаётся в контейнер и можно запускать тесты из его командной строки.

## Команда запуска Docker
### Сборка контейнера
```bash
docker-compose build
```
### Запуск контейнера и выполнение тестов Playwright
```bash
docker-compose run --rm playwright npx playwright test
```

## Команда для запуска всех тестов. Если требуется запуск в конкретном браузере - то необходимо дописать в конце команды конкретный "--project"

```bash
npx playwright test

 --project googleChrome
 --project mobileChrome
 --project mobileSafari
```

## Фильтры для запуска по тегам.Нужно добавить в конце команды запуска тестов.

```bash
--grep "@smoke"
--grep "@bitrix_errors"
--grep "@mobile"
--grep "@regression"
--grep "@orders_sanity_test"
```


## Команда запуска отчета

```bash
npx playwright show-report
```

## Команда запуска записи теста

```bash
npx playwright codegen
```
