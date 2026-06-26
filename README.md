# 🔍 Классификатор токсичных комментариев

Бинарная классификация русскоязычных комментариев на токсичные и нормальные.  
Финальный проект по курсу «Машинное обучение», программа «Языковые технологии».

## 📋 Описание задачи

**Цель:** предсказать, является ли комментарий токсичным (бинарная классификация).  
**Целевая переменная:** `target` — 0 (нормальный) / 1 (токсичный).  
**Признаки:** TF-IDF на словарном и символьном уровне.  
**Датасет:** 248 290 русскоязычных комментариев (NORMAL / INSULT / THREAT / OBSCENITY).  
**Метрика:** F1-macro (из-за дисбаланса классов ~82/18).

## 🗂️ Структура репозитория

```
toxic-comment-classifier/
├── data/
│   └── dataset.txt          # датасет (FastText-формат)
├── src/
│   ├── data/
│   │   └── preprocess.py    # функции очистки текста
│   └── models/
│       └── train.py         # обучение и сохранение моделей
├── outputs/                 # графики EDA и сравнения моделей
├── models/                  # сохранённые .pkl артефакты
├── toxic_comment_classifier.ipynb  # основной ноутбук (Google Colab)
├── requirements.txt
├── .gitignore
└── README.md
```

## 🚀 Запуск

### В Google Colab
1. Откройте `toxic_comment_classifier.ipynb` через Google Colab.
2. Поместите `data/dataset.txt` в папку `data/` в Colab-сессии (или смонтируйте Google Drive).
3. Запустите все ячейки последовательно.

### Локально
```bash
git clone https://github.com/ritaveab/toxic-comment-classifier.git
cd toxic-comment-classifier
pip install -r requirements.txt
jupyter notebook toxic_comment_classifier.ipynb
```

## 📊 Результаты

| Модель | F1-macro | F1 (токсичный) |
|--------|----------|----------------|
| Baseline: LogReg + TF-IDF (слова) | ~0.87 | ~0.80 |
| Improved: LinearSVC + TF-IDF (слова + символы) | ~0.90 | ~0.85 |

## 👥 Авторы

| Участник | Вклад |
|----------|-------|
| Rita | EDA, препроцессинг, baseline модель, анализ ошибок |
| [Партнёр] | Улучшенная модель, сравнение, визуализация, README |
