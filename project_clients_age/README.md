# Определение тональности пользовательских комментариев
Cупермаркет внедряет систему компьютерного зрения для обработки фотографий покупателей. Фотофиксация в прикассовой зоне поможет определять возраст клиентов, чтобы:
Анализировать покупки и предлагать товары, которые могут заинтересовать покупателей этой возрастной группы;
Контролировать добросовестность кассиров при продаже алкоголя.
Необходимо построить модель, которая по фотографии определит приблизительный возраст человека. В вашем распоряжении набор фотографий людей с указанием возраста.
## План проекта
- Шаг 1. Исследовательский анализ данных
- Шаг 2. Обучение модели
- Шаг 3. Анализ обученной модели
## Использованные библиотеки
Pandas, keras, matplotlib

### Шаг 1. Исследовательский анализ данных
Выбросов в данных не выявлено. Исходя из объема выборки (она большая) не замораживаем часть сети (т.к. не грозит переобучение). Сами фотографии бывают повернутыми, лица находятся в центре. Соответственно, чтобы модель лучше обучалась, проведем аугментацию - отразим изображения в обучающей выборке по горизонтали и вертикали.
### Шаг 2. Обучение модели
Обучена модель ResNet. Применена аугментация. Модель обучена на 5ти эпохах
### Шаг 3. Анализ обученной модели 
Использована предобученна модель ResNet. Т.к. у нас задача регрессии, то на выходе нужен только один нейрон, предсказывающий возраст. При количестве эпох 5 мы смогли получить требуемуемое качество предсказания возраста.

## Результаты и выводы
Мы смогли построить модель, которая справляется с поставленной задачей, с метрикой качества MAE: 7.8546
