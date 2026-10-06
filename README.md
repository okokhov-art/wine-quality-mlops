# Wine Quality Classification + MLOps Service

Проект по классификации качества красного вина с развёртыванием модели в виде сервиса и мониторингом.

## Задача

Определить, является ли вино «хорошим» (quality ≥ 6) или «плохим» на основе физико-химических характеристик.

## Модель

- Алгоритм: **Random Forest**
- Метрики на тестовой выборке:
  - Accuracy ≈ 0.79–0.80
  - F1-score ≈ 0.81–0.82
  - Precision ≈ 0.81
  - Recall ≈ 0.82

## MLOps-часть

Реализован полноценный сервис:

- **Flask API**
  - `/predict` — получение предсказания
  - `/retrain` — дообучение модели на новых данных
- **Мониторинг**
  - Экспорт метрик в **Prometheus**
  - Дашборд в **Grafana** (Accuracy, F1, Precision, Recall, количество предсказаний)
- Сохранение модели и scaler через `joblib`
- Возможность периодического обновления метрик

## Структура проекта

```
wine-quality-mlops/
├── notebooks/
│   └── wine_quality_service.ipynb
├── model.pkl
├── scaler.pkl
├── prometheus.yml
├── requirements.txt
└── README.md
```

## Установка и запуск

```bash
pip install -r requirements.txt
```

Запуск сервиса (пример):

```bash
python app.py
```

Метрики будут доступны по адресу: `http://localhost:5000/metrics`

## Автор

Олег Кохов  
Data Scientist / ML Engineer
