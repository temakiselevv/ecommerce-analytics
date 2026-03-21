# Amazon India E-commerce Sales Analysis & Demand Forecasting

**Анализ продаж Amazon India (март–июнь 2022) + предсказание спроса**

Полный пет-проект, включающий EDA, RFM-сегментацию клиентов, ABC-анализ и построение модели машинного обучения.

## Цели проекта

- Провести глубокий разведочный анализ продаж
- Выявить ключевые драйверы выручки и паттерны поведения клиентов
- Сегментировать клиентов с помощью RFM-анализа
- Построить модель предсказания количества продаж (`qty`)
- Сформулировать бизнес-рекомендации

## Основные результаты

### EDA
- Общая выручка за 4 месяца: **75.4 млн INR**
- Продано **116 479 единиц** товаров
- Категория **Set** приносит **49.95%** всей выручки
- Две категории (**Set** + **kurta**) обеспечивают **77.07%** оборота
- Товары в наличии продаются на **26.6%** лучше
- Amazon Fulfillment даёт средний чек **в 3+ раза выше**, чем Merchant

### RFM-анализ клиентов
- **Champions** (23.4% клиентов) генерируют основную долю выручки
- **Loyal Customers** (19.4% клиентов) добавляют +8.2% выручки
- Вместе два верхних сегмента обеспечивают **более 91%** выручки
- 61.2% клиентов (сегменты Lost, At Risk, Hibernating и др.) приносят менее 9% выручки

### Моделирование
- Модель: RandomForestRegressor
- **MAE**: 5.73 шт.
- **RMSE**: 12.87 шт.
- **R²**: 0.1608
- Ключевой драйвер — наличие и объём стока (`stock_log`)

## Структура проекта
ecommerce-analytics/  
├── dashboards/  
├── data/  
│   ├── cleaned/  
│   ├── features/  
│   └── raw/  
├── notebooks/  
│   ├── 01_data_overview.ipynb  
│   ├── 02_clean_amazon_sales.ipynb  
│   ├── 03_clean_stock.ipynb  
│   ├── 04_feature_engineering.ipynb  
│   ├── 05_eda.ipynb  
│   ├── 06_rfm_customer_segmentation.ipynb    
│   └── 07_modeling.ipynb  
├── presentation.pdf  
├── requirements.txt  
└── README.md  

## Что было сделано

### 1. Data Cleaning (02_clean_amazon_sales.ipynb, 03_clean_stock.ipynb)
- Очистка пропусков, приведение типов, обработка дат
- Объединение продаж и стоков

### 2. Feature Engineering (04_feature_engineering.ipynb)
- Агрегация данных по `sku` + месяц
- Создание временных признаков (month, weekday, weekend)
- Признаки стока (`stock_sum`, `in_stock`, `stock_log`)
- Target encoding: `category_avg_qty`

### 3. Exploratory Data Analysis (05_eda.ipynb)
- Распределение `qty` и `revenue`
- Динамика выручки по месяцам
- Топ-категории и SKU
- Примитивный ABC-анализ по SKU
- Корреляционный анализ

### 4. RFM Customer Segmentation (06_rfm_customer_segmentation.ipynb)
- Создание прокси `CustomerID` на основе гео-данных
- Расчёт Recency, Frequency, Monetary
- Сегментация клиентов на 7 групп (Champions, Loyal Customers, At Risk, Lost и др.)
- Анализ вклада каждого сегмента в выручку

### 5. Demand Forecasting (07_modeling.ipynb)
- Модель `RandomForestRegressor` для предсказания `qty`
- Оценка качества (MAE, RMSE)
- Feature Importance
- Визуализация предсказаний

## Ключевые insights

- Топ-категория `Set` приносит 49.95% всей выручки
- Размеры L, XL и XXL доминируют в продажах
- 42,8% клиентов относятся к сегментам **Champions + Loyal Customers**, но дают 91,5% выручки
- Модель прогнозирования показывает MAE = 5.73
- Наличие стока — критически важный фактор продаж
- Amazon Fulfillment значительно повышает средний чек.

## Бизнес-рекомендации

1. **Клиентская стратегия**:
   - Разработать программу лояльности для сегмента **Champions** и **Loyal Customers**
   - Запустить реактивационные кампании для **At Risk** и **Hibernating**
   - Минимизировать маркетинговые затраты на **Lost**

2. **Ассортимент**:
   - Увеличить сток и рекламу размеров L–XXL в категории Set
   - Сократить ассортимент категории C по ABC-анализу

3. **Операционка**:
   - Стимулировать fulfilment через Amazon
   - Оптимизировать прогнозирование спроса для снижения out-of-stock


## Стек технологий

- **Язык**: Python 3.10
- **Анализ**: pandas, numpy
- **Визуализация**: plotly, matplotlib, seaborn
- **Машинное обучение**: scikit-learn, xgboost
- **Дополнительно**: RFM-анализ, ABC-анализ, Feature Engineering

## Стек технологий

- **Язык**: Python 3.10
- **Анализ**: pandas, numpy
- **Визуализация**: plotly, matplotlib, seaborn
- **Машинное обучение**: scikit-learn, xgboost
- **Дополнительно**: RFM-анализ, ABC-анализ, Feature Engineering

## Данные
Сырые данные не включены в репозиторий из-за объёма.

Скачайте датасет по ссылке:  
https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data

Распакуйте архив и положите файлы в папку `data/raw/`.

## Как запустить проект

```bash
pip install -r requirements.txt
```
Запуск ноутбуков в порядке:  
1. 02_clean_amazon_sales.ipynb  
2. 03_clean_stock.ipynb  
3. 04_feature_engineering.ipynb  
4. 05_eda.ipynb  
5. 06_rfm_customer_segmentation.ipynb  
6. 07_modeling.ipynb  

## Автор  
Киселев Артём — Junior Data Analyst  
GitHub: Tema Kiselev (temakiselevv) | Telegram: @tema_kiselev





