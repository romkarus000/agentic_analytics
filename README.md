# Agentic Analytics MVP

Монорепозиторий для пошаговой разработки MVP AI-native аналитической платформы.

## Структура проекта

- `frontend/` — будущий frontend на Next.js.
- `backend/` — будущий backend на FastAPI.
- `infra/` — инфраструктурные артефакты и вспомогательные конфиги.
- `docs/` — документация проекта.
- `dbt/` — будущие dbt-проекты и трансформации.
- `cube/` — будущая semantic layer конфигурация.

На текущем шаге в репозитории создан только каркас проекта и минимальная инфраструктура для локального запуска PostgreSQL. Бизнес-логика, backend и frontend приложения пока не инициализированы.

## Предварительные требования

- Docker
- Docker Compose

## Быстрый старт

1. Создайте локальный env-файл из шаблона:

   ```bash
   cp .env.example .env
   ```

2. Поднимите PostgreSQL:

   ```bash
   docker compose up -d
   ```

3. Проверьте состояние контейнера:

   ```bash
   docker compose ps
   ```

4. При необходимости посмотрите логи:

   ```bash
   docker compose logs postgres
   ```

5. Остановите окружение:

   ```bash
   docker compose down
   ```

## Проверка доступности PostgreSQL

После старта контейнера можно выполнить:

```bash
docker compose exec postgres pg_isready -U "$POSTGRES_USER" -d "$POSTGRES_DB"
```

Ожидаемый результат: PostgreSQL сообщает, что принимает подключения.

## Ограничения текущего шага

- В `docker-compose.yml` подключен только PostgreSQL.
- FastAPI, Next.js, ClickHouse, Redis, Cube и LangGraph пока не добавлены.
- В репозитории отсутствует бизнес-логика и код приложений.
