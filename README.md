# vk_intern_spam_detect
# Задача
Классифицировать текста сообщений на СПАМ и НЕ СПАМ.
# Решение
## CatBoost + LighGBM
Для начала я решил использовать классические методы для решения данной задачи. 
Я взял две модели - CatBoost и LightGBM. Для CatBoost я использовал text_features, а для LightGBM - TFiDF Vectorizer.

После кросс-валидации модель показала качество ROC-AUC - 0.9601

## Transformers
Далее я решил использовать Transformers. Обучил обычный bert и получил такой же результат, как классическими методами. После этого решил использовать предобученную модель на СПАМ текстах.

# Результаты
Метод | ROC-AUC |
--- | --- |  
CatBoost + Text Features | 0.934  |
TF-IDF LightGBM + CatBoost + Text Features | 0.9601 | 
BERT-base |  0.960  |
distilBERT(trained on spam text) |  0.965  |

Лучший результат должен быть методом Transformers - submission_distilbert.csv
