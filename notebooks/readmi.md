## Лабораторная работа №2

### Что сделано:
- Настроен Docker Compose с Airflow, SeaweedFS и PostgreSQL
- Исправлен проброс переменных окружения по замечаниям ревью
- DAG `ingest_raw` выполняет:
  - DAG реализован в fallback режиме. Основной http источник недоступен, используется резервный сценарий.
  - Скачивание файла без изменения байтов (Pull)
  - Проверку идемпотентности (защита от дубликатов через `check_for_key`)
- Проверено чтение данных через DuckDB из SeaweedFS (порт 8333)

### Чек-лист самопроверки:
- [x] Инфраструктура поднимается командой `docker compose up -d`
- [x] Airflow доступен на http://127.0.0.1:8080
- [x] DAG `ingest_raw` выполняется успешно 
- [x] Резервный снимок `hour.csv` лежит в `data/source/`
- [x] Данные читаются через DuckDB из SeaweedFS

### Скриншоты:
<img width="1851" height="587" alt="screenshot-2026-10-14_00-13-19" src="https://github.com/user-attachments/assets/aee734c0-75a3-4d54-9c32-4c65d37b5daf" />
<img width="923" height="196" alt="screenshot-2026-10-06_21-56-58" src="https://github.com/user-attachments/assets/f8e9090b-4fa5-45b1-8f15-781c0fbf45a4" />
<img width="287" height="120" alt="image" src="https://github.com/user-attachments/assets/756d9245-f7fa-4b45-8b41-d5154d965486" />


