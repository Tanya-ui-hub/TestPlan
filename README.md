# План тестирования возможности записи на обучение профессии "Тестировщик ПО" [веб-сайт Нетологии](https://netology.ru/)

## 1. Перечень автоматизируемых сценариев.
  ### Первый способ записи на обучение:
  1. Перейти на сайт [Нетология](https://netology.ru/)
  2. На главной странице в хедере сайта выбрать меню "Каталог курсов".
  3. В разделе программирование выбрать "Тестировщик ПО"
  4. Перейти к форме записи нажав на кнопку "Записаться" вверху страницы, либо пролистав страниц

  ### Второй способ записи на обучение:
  1. Перейти на сайт [Нетология](https://netology.ru/)
  2. На главной странице сайта выбрать раздел "НЕО для начинающих"
  3. Из списка профессий выбрать "Тестировщик ПО"
  4. Перейти к форме записи нажав на кнопку "Записаться" вверху страницы, либо пролистав страницу

  ### Третий способ записи на обучение:
  1. Перейти на сайт [Нетология](https://netology.ru/)
  2. На главной странице сайта выбрать раздел "Актуальные темы".
  3. В разделе программирование выбрать "Тестировщик ПО"
  4. Перейти к форме записи нажав на кнопку "Записаться" вверху страницы, либо пролистав страницу

  ## Тестовые сценарии:
  **1. Ввод валидных данных:**
   * Ввести имя на кириллице или латинице без спецсимволов и цифр;
   * Ввести номер телефона из 11 цифр в формате +79005009999;
   * Ввести email латиницей test@test.ru;
   * Нажать кнопку записаться.

  **Ожидаемый результат:**
   * Форма отправляется;
     * Появляется сообщение об успешной записи.

  **2. Ввод невалидного имени:**
   * Ввести в поле имя цифры или спецсимволы.

  **Ожидаемый результат:**
   * Появляется сообщение о том, что поле "имя" - "Должно состоять из букв".
   * Формы невозможно отправить

  **3. Ввод невалидного номера телефона:**
   * Ввести в поле телефон номер в формате: +7928888888888
      или спецсимволы --++++

  **Ожидаемый результат:**
   * Появляется сообщение о "Номер в формате +7(999)999-99-99"

  **4. Ввод невалидного email:**
   * Ввести email в формате email или цифры 12345.

  **Ожидаемый результат:**
   *Появляется сообщение "неверный email".
   * Форму невозможно отправить.

  **5. Отправка пустой формы**
  
  **Ожидаемый результат:**
   * Под каждым полем появляется сообщение "Обязательное поле"
   * Формы невозможно отправить

## 2. Перечень используемых инструментов с обоснованием выбора:
* **IntelliJ IDEA** - интегрированная среда разработки программного обеспечения, в которой будет выполняться написание автоматизированных сценариев; 
  
  Преимущество: 
  * Подсветка кода;
  * Автоматическое завершение строки;
  * Настраиваемые горячие клавиши;
  * Настройка шрифтов;
  * Выбор цветовой схемы редактора кода.

  
* **Java (JDK 11)** - объектно-ориентированный язык программирования, на котором будет выполняться написание автоматизированных сценариев;

  Преимущество:
  * Простота;
  * Объектно-ориентированный подход (ООП);
  * Безопасность;
  * Производительность;
  * Надёжность;
  * Независимость от аппаратной части и ОС;
  * Динамичность и адаптируемость;
  * Удобные и эффективные сетевые возможности;


* **Gradle** - система автоматической сборки;

  Преимущество:
  * Версия нового поколения, основанная на инструменте сборки JVM, который сочетает в себе преимущества Ant и Maven;
  * Использует основанный на Groovy DSL, который отказывается от XML и является более мощным и выразительным;
  * Предоставляет набор методов управления зависимостями, которые не только хорошо настраиваются, но и совместимы с Maven и Ivy;
  * Поддерживает плавную миграцию проектов сборки Ant и Maven.
  

* **JUnit5** - библиотека для тестирования программного обеспечения;
  Преимущество:
  * Использует функционал Java 8 или более поздних релизов;
  * Добавлено функций для описания, организации и выполнения тестов; 
  * Возможность использовать более одного процесса тестирования за раз, чего нельзя сделать в JUnit4.


* **Lombok** - библиотека генерации кода;
  Преимущество:
  * Просто генерирует код;
  * Нет семантики;
  * Работает для любой версии начиная с Java 6


* **Selenide** - инструмент для тестирования Web-приложений;
  Преимущество:
  * Встроенное неявное ожидание
  * Автоматически закрытие браузера после запуска варианта использования
  * Код прост и удобен для чтения
  * Автоматически делать скриншоты неудачных тестов 
  * Можно использовать с селеном.
  

* **AppVeyor** - веб-сервис непрерывной интеграции, предназначенный для сборки и тестирования;
  Преимущество:
  * Поддерживается несколько систем управления версиями:
    * GitHub.com и GitHub Enterprise
    * Bitbucket.com и сервер Bitbucket
    * GitLab.com и GitLab Enterprise
    * Azure DevOps (репозитории Git и TFVC)
  * Настройка CI проектов через пользовательский интерфейс или в точечном файле appveyor.yml.
  * Полный sud доступ к виртуальной машине под управлением сборки
  * SQL Server 2017 для Linux.
  * Bash и ядро PowerShell для управления потоком сборки.
  * Параллельная конфигурация как для Windows, так и для Linux-сборок.
  * Предустановленный сервис Docker.
  * Встроенный сервер NuGet.
  * Единый кросс-платформенный Build Worker API как в Windows (сообщения, результаты тестов).
  

* **Allure** - инструмент построения отчетов авто-тестов;
  Преимущество:
  * Гибкий легкий многоязычный инструмент отчета о тестировании;
  * Сокращает общий жизненный цикл дефектов;
  * Модульность и расширяемость.  


## 3. Перечень необходимых разрешений/данных/доступов:
* Разрешение на автоматизированное тестирование определенных страниц сайта Нетология;
* Разрешение на создание тестового пользователя;
* Доступ к приложению для тестирования;
* Доступ к СУБД для проверки создания и сохранения записей о данных, введенных при заполнении анкеты на запись курса "Тестировщик ПО",
  а также для получения консультации.

## 4. Перечень и описание возможных рисков при автоматизации:
* Ошибки при написании авто-тестов;
* Ошибки в авто-тестах, связанные с техническим сбоем;
* Ошибки в авто-тестах, в связи с изменением кода;
* Неоправданная стоимость и затраты на авто-тесты.

## 5. Перечень необходимых специалистов для автоматизации:
* Специалист по автоматизированному тестированию (QA Automation engineer).

## 6. Интервальная оценка с учётом рисков (в часах):
  * Время, необходимое для тестирования составляет ~24 часа.
  * Устранение последствий наступления рисков +15%-25% времени для реализации проекта ~3-6 часов.