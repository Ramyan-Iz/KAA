Cognitive Bias Detection with DeBERTa-v3
Модель для мультиклассовой классификации когнитивных искажений в англоязычных текстах.

https://colab.research.google.com/drive/1tjqOq2jJUUlSsFfQDnXUpte8cmXNMPqi?usp=sharing

О проекте
Проект выполнен в рамках выпускной квалификационной работы. Разработана модель на основе DeBERTa-v3 для автоматического обнаружения 7 типов когнитивных искажений в текстах пользователей.

Классы классификации:

Метка	Тип искажения
0.0	Overgeneralization
1.0	Personalization
2.0	Emotional Reasoning
3.0	Labeling
4.0	Mind Reading
5.0	Should Statements
6.0	Catastrophizing
Архитектура
Модель: DebertaV2ForSequenceClassification (microsoft/deberta-v3-base)

Количество классов: 7

Максимальная длина последовательности: 165 токенов

Функция потерь: CrossEntropyLoss с весами классов

FP16: включено

Среда выполнения
Проект разработан в Google Colab с использованием GPU T4. Это позволило выполнять обучение без необходимости в локальном GPU.

Этапы работы
Подготовка окружения и установка зависимостей

Загрузка и предобработка данных из Excel

Анализ и визуализация датасета

Токенизация текстов

Обучение модели DeBERTa-v3

Оценка качества (матрица ошибок, classification report)

Инференс на новых текстах

Подробные графики обучения и матрица ошибок представлены в ноутбуке.
<img width="797" height="701" alt="image" src="https://github.com/user-attachments/assets/707cec3c-3f04-4eb1-816d-a7e98be256c2" />

Запуск в Colab
Открыть ноутбук по ссылке выше

Выполнить все ячейки последовательно

При необходимости загрузить свой файл с данными

Данные
Формат входных данных: Excel-файл с колонкой raw_data, где текст и метка разделены запятой.

Пример строки:

text
I cannot believe I ate that cake. This overwhelming shame...,2.0
Примеры предсказаний
Текст	Класс	Уверенность
My friend didn't laugh at my joke—they must think I'm not funny.	Labeling (3.0)	99.85%
My headache must be a brain tumor.	Catastrophizing (6.0)	87.80%

Автор: Сарапулов Роман
Тема ВКР: Идентификация когнитивных искажений в текстах с помощью нейронной сети
