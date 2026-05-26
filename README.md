В рамках проекта реализован полный аналитический pipeline:

PostgreSQL → ETL → MinIO → ML/Data Marts → Superset

Проект включает:

обработку данных добычи;
анализ телеметрии оборудования;
прогнозирование дебита;
поиск аномалий;
аналитику логистики и поставок.

Основной код проекта

Весь основной код проекта находится в файле:

notebooks/pipeline.ipynb

Notebook содержит:

ETL-процесс;
загрузку данных из PostgreSQL;
обработку и очистку данных;
feature engineering;
агрегации;
экспорт данных в MinIO;
создание parquet файлов;
ML-модели;
расчёт метрик;
создание аналитических витрин;

Использование MinIO

MinIO использовался как S3-совместимое объектное хранилище (Data Lake).

Подготовленные данные выгружались из PostgreSQL, преобразовывались в Jupyter Notebook и сохранялись в MinIO в формате parquet с partitioning по скважинам.

Пример partitioning:

well_1/
well_2/
well_3/
well_4/
well_5/

Инфраструктура

В docker-compose.yml разворачиваются:

PostgreSQL
MinIO
Jupyter Notebook
Apache Superset

ETL и Data Processing

ETL-процесс реализован в Jupyter Notebook.

Выполнены:

извлечение данных из PostgreSQL;
обработка NULL;
фильтрация выбросов;
агрегация данных;
feature engineering;
загрузка parquet файлов в MinIO;
создание аналитических витрин.

BI / Dashboards

Все аналитические графики и dashboards построены в Apache Superset.

Скриншоты находятся в папке:

Seperset/
