# Homework_12
Перейти к основному содержимому
Тобі необхідно створити проєкт - систему для зберігання нотаток (Todo List). Створювати цю систему будемо за допомогою Spring Boot, додаючи почергово різні модулі.

В проєкті буде лише одна сутність - Note (нотатка). Користувач зможе управляти цими нотатками - дивитись список нотаток, додавати нові, та редагувати існуючі.

Завдання №1 - створити новий проєкт на Spring Boot
Створи новий Spring Boot проєкт. Як систему збірки використовуй Gradle.

Не додавай до проєкту модулі Spring MVC, Spring Data та Spring Security. Ці модулі додамо пізніше.

Для створення Spring Boot проєкту можна використати сайт Spring Boot Initializr - https://start.spring.io/

Завдання №2 - створити сутність Note
Створи сутність Note - нотатка. В цій сутності мають бути наступні поля:

id - унікальний ідентифікатор, ціле автогенероване число
title - назва нотатки. Рядок (String).
content - контент нотатки. Рядок (String).
Оскільки в проєкті поки немає підключеного модулю Spring Data, не додавай до сутності анотацію @Entity.

Завдання №3 - створити CRUD сервіс NoteService
Створи новий клас з назвою NoteService. Це клас для управління нотатками. В майбутньому нотатки будуть зберігатись в БД, наразі використай колецію (List<Note> або Map<Long, Note>) для зберігання цих нотаток.

В сервісі мають бути наступні методи:

List<Note> listAll() - повертає список всіх нотаток
Note add(Note note) - додає нову нотатку, генеруючи для цієї нотатки унікальний (випадковий) числовий ідентифікатор, повертає цю ж нотатку з згенерованим ідентифікатором.
void deleteById(long id) - видаляє нотатку з вказаним ідентифікатором. Якщо нотатки з ідентифікатором немає - викидає виключення.
void update(Note note) - шукає нотатку по note.id. Якщо нотатка є - оновлює для неї title та content. Якщо нотатки немає - викидає виключення.
Note getById(long id) - повертає нотатку по її ідентифікатору. Якщо нотатки немає - викидає виключення.
Використай анотацію @Service, щоб зробити цей клас Spring Bean.

Запусти програму, і переконайсь, що вона успішно запускається (без помилок в консолі).

Завдання №4 - залити весь код в Github репозиторій
Залий код на Github репозиторій. Переконайсь, що файл .gitignore налаштований коректно, і в репозиторій потрапили лише потрібні файли.

Результат ДЗ - посилання на репозиторій.

# Homework_13

Перейти к основному содержимому
Як основу візьми проєкт з попереднього ДЗ. Поточне ДЗ можна виконувати в цьому ж репозиторії, або створити новий репозиторій - це на твій розсуд.

Завдання №1 - додай модуль Spring MVC
Додай до проєкту модуль Spring MVC.

Створи тестовий контролер (наприклад, TestControler), створи у цьому контролері тестовий метод (зі шляхом, наприклад, /test) та переконайсь, що програма запускається, та за адресою на кшталт http://localhost:8080/test в браузері можна доступитись до метода контролера.

Завдання №2 - додай бібліотеку Thymeleaf
Додай до проєкту бібліотеку Thymeleaf (достатньо додати Spring Boot Starter spring-boot-starter-thymeleaf).

Створий тестовий шаблон (наприклад, test.html з контентом <h1>Hello, World</h1>), та створи тестовий контролер, який завантажуватиме цей шаблон і повертатиме користувачу. Переконайсь, що програма запускається, і за адресою в браузері на кшталт http://localhost:8080/test можна отримати контент шаблону.

Завдання №3 - створи на pure HTML UI для управління нотатками
Створи контролер NoteController. Створи на pure HTML UI для управління нотатками.

Обов'язково мають бути наступні сторінки:

GET /note/list - отримати список нотаток. Виводиться список нотаток (title та content), кожну нотатку можна видалити або редагувати
POST /note/delete - видалити нотатку по ID. Після видалення нотатки відбувається редирект на /note/list
GET /note/edit?id=xxx - сторінка редагування нотатку (відкривається по натисненню на кнопку Редагувати на списку нотаток).
POST /note/edit - сюди відправляється запит на редагування нотатки. Після збереження оновленого контенту нотатки відбувається редирект на /note/list
Необов'язкове завдання
Додай до проєкту бібліотеку bootstrap (за допомогою CDN посилання). Стилізуй програму за допомогою bootstrap компонентів.

Завдання №4 - залий код на Github
Залий код на Github репозиторій. Переконайсь, що файл .gitignore налаштований коректно, і в репозиторій потрапили лише потрібні файли.

Результат ДЗ - посилання на репозиторій.

# Homework_14

Перейти к основному содержимому
Як основу візьми проєкт з попереднього ДЗ. Поточне ДЗ можна виконувати в цьому ж репозиторії, або створити новий репозиторій - це на твій розсуд.

Завдання №1 - додай модуль Spring Data
Додай до проєкту модуль Spring Data. Для цього достатньо додати стартер spring-boot-starter-data-jpa.

Завдання №2 - додай СУБД H2
Додай до проєкту СУБД H2.

Переконайсь, що проєкт успішно запускається (що СУБД H2 та модуль Spring Data коректно працюють разом).

Завдання №3 - додай бібліотеку Flyway та напиши міграцію
Додай до проєкту бібліотеку flyway. Напиши міграцію для створення таблиці note.

Переконайсь, що проєкт успішно запускається та міграція виконується (у консолі мають бути відповідні логи про виконання міграції).

Завдання №4 - виправ модуль NoteService
Додай анотацію @Entity до сутності Note. Напиши репозиторій NoteRepository для роботи з сутностями типу Note.

Зміни сервіс NoteService, щоб зберігати нотатки в БД, замість того, щоб зберігати їх в колеції як це було реалізовано раніше.

Запусти всю програму в зборі, та переконайсь, що за допомогою web інтерфейсу в браузері все працює коректно.

Завдання №5 - залий код на Github
Залий код на Github репозиторій. Переконайсь, що файл .gitignore налаштований коректно, і в репозиторій потрапили лише потрібні файли.

Результат ДЗ - посилання на репозиторій.