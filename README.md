# Конспект книги Николенко "Глубокое обучение"

[Николенко С.И. на wikipedia](https://ru.wikipedia.org/wiki/Николенко,_Сергей_Игоревич "Николенко Сергей Игоревич")

## Часть I. Как обучать нейронные сети
### Глава 1. От биологии к информатике, *или We need to go deeper*
#### 1.1. Революция обучения глубоких сетей

> В 2005–2006 годах группы исследователей под руководством
> Джеффри Хинтона (Geoffrey Hinton) в университете Торонто и Йошуа Бенджи (Yoshua Bengio)
> в университете Монреаля научились обучать глубокие нейронные сети.

> Решение, предложенное группой Хинтона в середине 2000-х годов, пришло
> в виде предобучения без учителя, когда сеть сначала обучается на большом наборе
> данных без разметки, а потом уже дообучается на размеченных данных, используя
> это приближение. Например, если мы хотим распознавать человеческие лица, то
> давайте сначала пообучаем нейронную сеть на фотографиях с людьми вообще, без
> разметки (таких фотографий можно легко набрать сколь угодно много), а уже
> потом, когда сеть «насмотрится» на неразмеченные фотографии, дообучим ее на
> имеющемся размеченном наборе данных. Оказалось, что при этом конечный результат
> становится намного лучше, а хорошие и интересные признаки сеть начинает
> выделять еще на этапе предобучения без учителя.

#### 1.2. Искусственный интеллект и машинное обучение
#### 1.3. Немного о словах: каким бывает машинное обучение
#### 1.4. Особенности человеческого мозга
#### 1.5. Пределы нейробиологии: что мы на самом деле знаем?
#### 1.6. Блеск и нищета современных нейронных сетей
### Глава 2. Предварительные сведения, *или Курс молодого бойца*
#### 2.1. Теорема Байеса
#### 2.2. Функции ошибки и регуляризация
#### 2.3. Расстояние Кульбака — Лейблера и перекрестная энтропия
#### 2.4. Градиентный спуск: основы
#### 2.5. Граф вычислений и дифференцирование на нем
#### 2.6. И о практике: введение в TensorFlow и Keras
### Глава 3. Перцептрон, *или Эмбрион мудрого компьютера*
#### 3.1. Когда появились искусственные нейронные сети
#### 3.2. Как работает перцептрон
#### 3.3. Современные перцептроны: функции активации
#### 3.4. Как же обучаются настоящие нейроны
#### 3.5. Глубокие сети: в чем прелесть и в чем сложность?
#### 3.6. Пример: распознавание рукописных цифр на TensorFlow
## Часть II. Основные архитектуры
### Глава 4. Быстрее, глубже, сильнее, *или Об оврагах, долинах и трамплинах*
#### 4.1. Регуляризация в нейронных сетях
#### 4.2. Как инициализировать веса
#### 4.3. Нормализация по мини-батчам
#### 4.4. Метод моментов: Ньютон, Нестеров и Гессе
#### 4.5. Адаптивные варианты градиентного спуска
### Глава 5. Сверточные нейронные сети и автокодировщики, *или Не верь глазам своим*
#### 5.1. Зрительная кора головного мозга
#### 5.2. Свертки и сверточные сети
#### 5.3. Свертки для распознавания цифр
#### 5.4. Современные сверточные архитектуры
#### 5.5. Автокодировщики
#### 5.6. Пример: кодируем рукописные цифры
### Глава 6. Рекуррентные нейронные сети, *или Как правильно кусать себя за хвост*
#### 6.1. Мотивация: обработка последовательностей
#### 6.2. Распространение ошибки и архитектуры RNN
#### 6.3. LSTM
#### 6.4. GRU и другие варианты
#### 6.5. SCRN и другие: долгая память в обычных RNN
#### 6.6. Пример: порождаем текст символ за символом
## Часть III. Новые архитектуры и применения
### Глава 7. Как научить компьютер читать, *или Математик - Мужчина + Женщина =*
#### 7.1. Интеллектуальная обработка текстов
#### 7.2. Распределенные представления слов: word2vec
#### 7.3. Русскоязычный word2vec на практике
#### 7.4. GloVe: раскладываем матрицу правильно
#### 7.5. Вверх и вниз от представлений слов
#### 7.6. Рекурсивные нейронные сети и синтаксический разбор
### Глава 8. Современные архитектуры, *или Как в споре рождается истина*
#### 8.1. Модели с вниманием и encoder-decoder
#### 8.2. Порождающие модели и глубокое обучение
#### 8.3. Состязательные сети
#### 8.4. Практический пример и трюк с логистическим сигмоидом
#### 8.5. Архитектуры, основанные на GAN
### Глава 9. Глубокое обучение с подкреплением, *или Удивительное происшествие с чемпионом*
#### 9.1. Обучение с подкреплением
#### 9.2. Марковские процессы принятия решений
#### 9.3. От TDGammon к DQN
#### 9.4. Бамбуковая хлопушка
#### 9.5. Градиент по стратегиям и другие применения
### Глава 10. Нейробайесовские методы, *или Прошлое и будущее машинного обучения*
#### 10.1. Теорема Байеса и нейронные сети
#### 10.2. Алгоритм EM
#### 10.3. Вариационные приближения
#### 10.4. Вариационный автокодировщик
#### 10.5. Байесовские нейронные сети и дропаут
#### 10.6. Заключение: что не вошло в книгу и что будет дальше