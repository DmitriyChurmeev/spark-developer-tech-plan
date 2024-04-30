Тема проектной работы - "Анализ и прогнрозирование дорожного трафика"

Стек технологий:
Scala
Hadoop
Apache Kafka
Apache Spark (Core, SQL. ML)
Apache Airflow
Docker
K8S

Схема:
https://app.diagrams.net/#HDmitriyChurmeev%2Fspark-developer-tech-plan%2Fmain%2F%D0%94%D0%B8%D0%B0%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B0%20%D0%B1%D0%B5%D0%B7%20%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F.drawio#%7B%22pageId%22%3A%22plByRppV0Iz8zn7RaR1O%22%7D


Описание:
Используемые типы данных
Погода (Дата, температура, влажность воздуха и т.д) - список параметров может расширится, источник kaggle
Дорожный трафик (Дата, Адрес улицы, Уровень троафика, дорожные происшествия и т.д) - список параметров может расширится, источник kaggle
Стоимость такси (Дата, стоимость, адрес начала поездки, адрес назнвчения и т.д) - список параметров может расширится, источник kaggle
города Нью-ЙОрк

Каждый тип данных стримится (Kafka Stream) отдельным инстансом приложения.
Основное приложение читает данные для фильтрации и трансформации в удобный формат для записи в отдельную тадлицу HDFS.

Планировщик задач (Apache Airflow) по заданному времени запускает две такси

1) Анализ дорожного трафика
   Чтение таблиц для нахождения связующих данных (дата и распололжения) для получения
   средней стоимости такси в зависимости от параметров
   среднего дорожного трафика в зависимости от параметров

2) Моделирование и прогнозирование дорожного трафика
   Построение модели для прогнозирования
   расчета стоимости такси в зависимости от дорожного трафика и погоды
   прогнозирования дорожных происшествий в зависимости от дорожного трафика и погоды