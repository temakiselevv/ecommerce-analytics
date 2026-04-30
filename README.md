# Amazon India E-commerce Sales Analysis & Demand Forecasting

[![Python 3.10](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/downloads/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Used-success)](https://pandas.pydata.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-Used-success)](https://scikit-learn.org/)

**Анализ продаж Amazon India + прогнозирование спроса с помощью машинного обучения**

Полноценный end-to-end аналитический проект: от очистки данных до RFM-сегментации клиентов и построения модели прогнозирования спроса.

---

## 🎯 О проекте

Проект посвящён глубокому анализу продаж на Amazon India (март–июнь 2022) и разработке модели прогнозирования количества продаж (`qty`).

**Основная цель** — выявить ключевые драйверы выручки, сегментировать клиентов и построить полезную модель demand forecasting, которая поможет оптимизировать сток и продажи.

### Ключевые результаты

- **Общая выручка** за 4 месяца: **75.4 млн INR**
- Продано **116 479** единиц товаров
- Категория **Set** приносит **49.95%** всей выручки
- **RFM-анализ**: сегменты **Champions** + **Loyal Customers** (42.8% клиентов) генерируют **91.5%** выручки
- Модель: **RandomForestRegressor**
- **MAE**: 5.73 шт.
- **RMSE**: 12.87 шт.
- **R²**: 0.1608

**Самый важный фактор** — наличие и объём стока товара.

---

## 📊 Основные insights из EDA

- Две категории (**Set** + **kurta**) обеспечивают **77.07%** оборота
- Товары в наличии продаются на **26.6%** лучше
- Amazon Fulfillment даёт средний чек **в 3+ раза выше**, чем Merchant
- Размеры **L, XL, XXL** значительно доминируют в продажах
- Более 61% клиентов относятся к низкоценным сегментам и приносят менее 9% выручки

**Бизнес-выводы и рекомендации** находятся в презентации (`Amazon India E-commerce Analysis presentation.pdf`).

---

## 🛠 Технологический стек

- **Язык**: Python 3.10
- **Анализ данных**: Pandas, NumPy
- **Визуализация**: Plotly, Matplotlib, Seaborn
- **Машинное обучение**: Scikit-learn, RandomForestRegressor
- **Аналитика клиентов**: RFM-анализ, ABC-анализ
- **Дополнительно**: Feature Engineering, временные признаки

---

## 📁 Структура проекта

```text
ecommerce-analytics/
├── dashboards/                    # Интерактивные дашборды
├── data/                          # raw + processed данные
├── models/                        # Сохранённые модели (joblib)
├── notebooks/                     # Основные этапы анализа
│   ├── 01_data_overview.ipynb
│   ├── 02_clean_amazon_sales.ipynb
│   ├── 03_clean_stock.ipynb
│   ├── 04_feature_engineering.ipynb
│   ├── 05_eda.ipynb
│   ├── 06_rfm_customer_segmentation.ipynb
│   └── 07_modeling.ipynb
├── utils/                         # Вспомогательные скрипты
├── Amazon India E-commerce Analysis presentation.pdf
├── requirements.txt
└── README.md
```

## 🚀 Как запустить проект

**1. Клонируйте репозиторий**  
```console
git clone https://github.com/temakiselevv/ecommerce-analytics.git
cd telco-churn-project
```

**2. Создайте и активируйте виртуальное окружение**
```console
py -m venv venv
```
```console
# Linux/macOS
source venv/bin/activate
```
```console
# Windows
venv\Scripts\activate
```

**3. Установите необходиые зависимости:**
```console
pip install -r requirements.txt
```

**4. Скачайте датасет с Kaggle по ссылке:**  
https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data

Распакуйте архив и положите файлы `Amazon Sale Report.csv` и `Sale Report.csv` в папку `data/raw/`.

> Примечание: остальные файлы не были включены в анализ из-за некачественности данных.

**5. Запустите Jupyter Notebooks последовательно:** :  
1. 02_clean_amazon_sales.ipynb  
2. 03_clean_stock.ipynb  
3. 04_feature_engineering.ipynb  
4. 05_eda.ipynb  
5. 06_rfm_customer_segmentation.ipynb  
6. 07_modeling.ipynb  

## 📈 Методология

- Очистка и объединение данных продаж и стоков
- Feature Engineering (временные признаки, признаки стока, target encoding)
- Разведочный анализ данных (EDA)
- RFM-сегментация клиентов
- Примитивный ABC-анализ
- Построение модели прогнозирования спроса (qty)
- Анализ важности признаков и бизнес-рекомендации

## 📌 Ключевые особенности проекта

- Полный цикл анализа: от сырых данных до бизнес-рекомендаций
- Качественная RFM-сегментация клиентов
- Комбинация продуктового и клиентского анализа
- Практически применимая модель прогнозирования спроса
- Чёткие бизнес-инсайты и рекомендации

## Дополнительные материалы

- Презентация — Amazon India E-commerce Analysis presentation.pdf
- Jupyter notebooks — подробный разбор каждого этапа

**Хотите увидеть проект в действии?
Открывайте ноутбуки или презентацию — там вся ценность.
⭐ Если проект был полезен — ставьте звезду!**

## Автор  
Киселев Артём — Junior Data Analyst  
GitHub: Tema Kiselev (temakiselevv) | Telegram: @tema_kiselev

*Проект создан как демонстрация навыков в анализе продаж, RFM-сегментации, feature engineering и построении моделей demand forecasting.*