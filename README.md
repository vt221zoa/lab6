# Проєкт Чат-бота

## Опис

Цей проєкт реалізує простого чат-бота, який може взаємодіяти з користувачем, обробляти повідомлення та надавати відповіді на певні запитання.

## Функціонал

- Користувач може відправляти повідомлення чат-боту через веб-інтерфейс.
- Чат-бот може реагувати на повідомлення користувача та відповідати на них відповідно до заданих правил.
- Чат-бот може обробляти привітальні повідомлення, запити про свою ідентичність та задавати питання на відповідні теми.

## Процес запуску
1. Запустіть PyCharm та завантажте Flask python3 -m pip install Flask
2. Запустіть файл chatbot.py з вашого обраного середовища виконання Python.
3. Відкрийте ваш браузер та перейдіть за посиланням http://127.0.0.1:5000 для відображення веб-інтерфейсу чат-бота.



# Принципи програмування

1. **Принцип єдиного обов'язку (Single Responsibility Principle)**: Кожен клас повинен мати лише одну причину для зміни. Наприклад, клас  [ChatBot(singleton)](https://github.com/Marianzzz/lab6/blob/master/patterns/singleton.py) відповідає за взаємодію з користувачем і обробку повідомлень.

2. **Принцип відкритості/закритості (Open/Closed Principle)**: Сутності повинні бути відкритими для розширення, але закритими для змін. У моєму коді, нові функціональності можуть бути додані через додавання нових класів, які наслідуються від існуючих.

3. **Принцип підстановки Барбари Лісков (Liskov Substitution Principle)**: Об'єкти базового класу повинні бути замінними об'єктами похідних класів. У моєму коді, будь-який клас, який реалізує інтерфейс [MessageProcessingStrategy](https://github.com/Marianzzz/lab6/blob/master/patterns/strategy.py), може бути використаний для обробки повідомлень.

4. **Принцип інтерфейсу (Interface Segregation Principle)**: Клієнти не повинні залежати від інтерфейсів, які вони не використовують. У моєму коді, [класи-стратегії](https://github.com/Marianzzz/lab6/blob/master/patterns/strategy.py) можуть використовувати лише ті методи, які потрібні для їх функціонування.

5. **Принцип інверсії залежностей (Dependency Inversion Principle)**: Модулі високого рівня не повинні залежати від модулів низького рівня. Вони повинні залежати від абстракцій, а не від конкретних реалізацій. Мій код використовує принцип інверсії залежностей через використання інтерфейсу [MessageProcessingStrategy](https://github.com/Marianzzz/lab6/blob/master/patterns/strategy.py) для обробки повідомлень.

# Патерни проєктування

1. **Патерн Одинак (Singleton)**: Використовується для забезпечення того, що клас має лише один екземпляр і надає глобальну точку доступу до цього екземпляра. У моєму коді, клас [ChatBot(singleton)](https://github.com/Marianzzz/lab6/blob/master/patterns/singleton.py) реалізує паттерн Одинака, щоб забезпечити наявність лише одного екземпляра бота.

2. **Патерн Спостерігач (Observer)**: Використовується для встановлення зв'язку один до багатьох між об'єктами, де один об'єкт надсилає повідомлення про події і всі інші об'єкти, які підписалися на нього, автоматично отримують оновлення. У моєму коді, я використовуємо патерн [Спостерігача](https://github.com/Marianzzz/lab6/blob/master/patterns/observer.py) для повідомлення передплатників про нові повідомлення.

3. **Патерн Стратегія (Strategy)**: Використовується для визначення сімейства алгоритмів, інкапсуляції кожного з них і робить їх взаємозамінними. У моєму коді, класи [BasicMessageProcessingStrategy і AdvancedMessageProcessingStrategy](https://github.com/Marianzzz/lab6/blob/master/patterns/strategy.py) реалізують різні стратегії обробки повідомлень.
  


# Техніки рефакторингу

### Composing Methods

Функція receive_message була розділена на дві окремі функції process_user_message та get_processing_strategy [chatbot](https://github.com/Marianzzz/lab6/blob/master/chatbot.py), щоб кожна виконувала лише одну конкретну задачу.

### Organizing Data

Поля та методи класу [ChatBot(singleton)](https://github.com/Marianzzz/lab6/blob/master/patterns/singleton.py) були організовані таким чином, щоб пов'язані елементи були разом, спрощуючи розуміння та модифікацію коду.

### Simplifying Conditional Expressions

Умовні вирази були спрощені для покращення зрозуміння коду та зменшення повторюваності.

### Simplifying Method Calls

У викликах методів були видалені зайві аргументи та методи, щоб полегшити їх використання та зробити код більш зрозумілим [singleton](https://github.com/Marianzzz/lab6/blob/master/patterns/singleton.py).

### Dealing with Generalization

Класи були розроблені таким чином, щоб бути загальними та більш гнучкими, дозволяючи змінювати їх поведінку без необхідності змінювати виклики зовнішніх функцій.

