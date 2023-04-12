# Финальный тестовый проект SkillFactory курса QAP»


Автоматизированное тестирование сайта: https://b2c.passport.rt.ru с использованием PyTest и Selenium.
Selenium является самым популярным инструментом тестирования автоматизации для выполнения функциональных тестов в веб-приложениях. Selenium облегчает запись тестовых сценариев. При создании автотестов для получения локаторов использовался инструмент разработчика DevTools.

В файле test_rostelecom.py находятся тесты по страницам Авторизация и Регистрация.

В файле settings.py указаны валидный лицевой счет и невалидный пароль, применяемые для тестирования

Папка Pages содержит следующие файлы:

       base_page.py - находится конструктор webdriver и общие для всех тестируемых страниц методы

       auth_page.py - содержит элементы и методы для страницы "Авторизация"

       reg_page.py - содержит элементы и методы для страницы "Регистрация"

       locators.py - содержит локаторы для поиска элементов на странице


Запуск тестов: pytest -v -s -q --driver Chrome --driver-path C:/Users/User/PycharmProjects/pythonProject/FinalProject/chromedriver.exe test_rostelecom.py


Тесты разделены на 2 блока:
1. Тестирование страницы Авторизация (1-8 тест):
- проверка соответствия ТЗ и элементов, ссылок и кнопок на странице - Статическое тестирование
- проверка соответствия ТЗ и отображаемых ошибок, действий при нажатии кнопок, ссылок - Динамическое тестирование с использованием техники черного ящика. При этом использовалась техника тест-дизайна "Причины и следствия"

2. Тестирование страницы Регистрация (9-18 тест):
- проверка соответствия ТЗ и элементов, ссылок и кнопок на странице - Статическое тестирование
 - отображение ошибки при вводе некорректного имени - Динамическое тестирование с использованием техники черного ящика. Т.к. есть ограничение по количеству символов в имени, использовались техники тест-дизайна эквивалентного разбиения и граничных значений. А также методы тест-дизайна "Предугадывание ошибок", позитивные и негативные тесты. Применена параметризация теста с помощью фикстуры
 - отображение ошибки при вводе некорректного пароля - Динамическое тестирование с использованием техники черного ящика, применялись методы тест-дизайна "Причины и следствия", "Предугадывание ошибок", позитивные и негативные тесты. Применена параметризация теста с помощью декоратора.
