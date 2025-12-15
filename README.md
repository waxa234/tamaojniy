
# Таможенный калькулятор — Полный продукт (MVP → Production-ready scaffold)

Этот архив содержит готовую структуру проекта «Таможенный калькулятор» на FastAPI + PostgreSQL.
Включены:
- FastAPI backend с эндпоинтом `/api/calculate`
- SQLAlchemy модели и база
- Alembic (структура) для миграций
- Парсер `.docx` для загрузки TN VED кодов
- Воркеры для обновления курсов валют и заготовки парсера Lex.uz
- Docker + docker-compose
- Минималистичный фронтенд
- Тесты pytest и CI конфигурация (GitHub Actions)

## Быстрый старт (локально с Docker)
1. Скопируйте репозиторий или распакуйте архив.
2. Соберите и поднимите сервис:
3. Откройте Swagger UI: `http://localhost:8000/docs`
4. Мини-фронтенд: `http://localhost:8000/static/index.html`

## Замечания
- Подробные настройки и интеграции (реальные endpoins CBU, lex.uz) нужно заполнить в `app/config.py`.
- Alembic содержит шаблон — выполните миграции при необходимости.
- Чтобы загрузить TN VED из `.docx`, используйте `python -m app.workers.parse_tnved_docx path/to/file.docx`.
