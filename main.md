<h1>Памятка/шпаргалка по SQL</h1>
<h2>Содержание</h2>
<ol>
  <li><a href="section1">Что такое SQL?</a></li>
  <li>Почему SQL?</li>
  <li>Процесс SQL</li>
  <li>Команды SQL</li>
  <li>Что такое таблица?</li>
  <li>Что такое поле?</li>
  <li>Что такое запись или строка?</li>
  <li>Что такое колонка?</li>
  <li>Что такое NULL?</li>
  <li>Ограничения</li>
  <li>Целостность данных</li>
  <li>Нормализация БД</li>
  <li>Синтаксис SQL</li>
  <li>Типы данных</li>
  <li>Операторы</li>
  <li>Выражения</li>
  <li>Создание БД</li>
  <li>Удаление БД</li>
  <li>Выбор БД</li>
  <li>Создание таблицы</li>
  <li>Удаление таблицы</li>
  <li>Добавление колонок</li>
  <li>Выборка полей</li>
  <li>Предложение WHERE</li>
  <li>Операторы AND и OR</li>
  <li>Обновление полей</li>
  <li>Удаление записей</li>
  <li>Предложения LIKE и REGEX</li>
  <li>Предложение TOP/LIMIT/ROWNUM</li>
  <li>Предложения ORDER BY и GROUP BY</li>
  <li>Ключевое слово DISTINCT</li>
  <li>Соединения</li>
  <li>Предложение UNION</li>
  <li>Предложение UNION ALL</li>
  <li>Синонимы</li>
  <li>Индексы</li>
  <li>Очистка таблицы</li>
  <li>Представления</li>
  <li>HAVING</li>
  <li>Транзакции</li>
  <li>Временные таблицы</li>
  <li>Клонирование таблицы</li>
  <li>Подзапросы</li>
  <li>Последовательности</li>
</ol>
<h2 id="section1">Что такое SQL?</h2>
<p>SQL — это язык структурированных запросов (Structured Query Language), позволяющий хранить, манипулировать и извлекать данные из реляционных баз данных (далее — РБД, БД).</p>
<h2 id="section2">Почему SQL?</h2>
<p>SQL позволяет:</p>
<ul>
  <li>получать доступ к данным в системах управления РБД</li>
  <li>описывать данные (их структуру)</li>
  <li>определять данные в БД и управлять ими</li>
  <li>взаимодействовать с другими языками через модули SQL, библиотеки и предваритальные компиляторы</li>
  <li>создавать и удалять БД и таблицы</li>
  <li>создавать представления, хранимые процедуры (stored procedures) и функции в БД</li>
  <li>устанавливать разрешения на доступ к таблицам, процедурам и представлениям</li>
</ul>
<h2 id="section3">Процесс SQL</h2>
<p>При выполнении любой SQL-команды в любой RDBMS (Relational Database Management System — система управления РБД, СУБД, например, PostgreSQL, MySQL, MSSQL, SQLite и др.) 
система определяет наилучший способ выполнения запроса, а движок SQL определяет способ интерпретации задачи.
В данном процессе участвует несколького компонентов:
<ul>
  <li>диспетчер запросов (Query Dispatcher)</li>
  <li>движок оптимизации (Optimization Engines)</li>
  <li>классический движок запросов (Classic Query Engine)</li>
  <li>движок запросов SQL (SQL Query Engine) и т.д.</li>
</ul>
Классический движок обрабатывает все не-SQL-запросы, а движок SQL-запросов не обрабатывает логические файлы.
</p>
<h2 id="section4">Команды SQL</h2>
<p>
  Стандартными командами для взаимодействия с РБД являются CREATE, SELECT, INSERT, UPDATE, DELETE и DROP. Эти команды могут быть классифицированы следующим образом:
  <ul>
    <li>DDL — язык определения данных (Data Definition Language)</li>
    <table border="1">
      <tr>
        <th>N</th>
        <th>Команда</th>
        <th>Описание</th>
      </tr>
      <tr>
        <td>1</td>
        <td>CREATE</td>
        <td>Создает новую таблицу, представление таблицы или другой объект в БД</td>
      </tr>
      <tr>
        <td>2</td>
        <td>ALTER</td>
        <td>Модифицирует существующий в БД объект, такой как таблица</td>
      </tr>
      <tr>
        <td>3</td>
        <td>DROP</td>
        <td>Удаляет существующую таблицу, представление таблицы или другой объект в БД</td>
      </tr>
    </table>
    <li>DML — язык изменения данных (Data Manipulation Language)</li>
    <table border="1">
      <tr>
        <th>N</th>
        <th>Команда</th>
        <th>Описание</th>
      </tr>
      <tr>
        <td>1</td>
        <td>SELECT</td>
        <td>Извлекает записи из одной или нескольких таблиц</td>
      </tr>
      <tr>
        <td>2</td>
        <td>INSERT</td>
        <td>Создает записи</td>
      </tr>
      <tr>
        <td>3</td>
        <td>UPDATE</td>
        <td>Модифицирует записи</td>
      </tr>
       <tr>
        <td>4</td>
        <td>DELETE</td>
        <td>Удаляет записи</td>
      </tr>
    </table>
    <li>DCL — язык управления данными (Data Control Language)</li>
    <table border="1">
      <tr>
        <th>N</th>
        <th>Команда</th>
        <th>Описание</th>
      </tr>
      <tr>
        <td>1</td>
        <td>GRANT</td>
        <td>Наделяет пользователя правами</td>
      </tr>
      <tr>
        <td>2</td>
        <td>REVOKE</td>
        <td>Отменяет права пользователя</td>
      </tr>
    </table>
  </ul>
  Обратите внимание: использование верхнего регистра в названиях команд SQL — это всего лишь соглашение, большинство СУБД нечувствительны к регистру. 
  Тем не менее, форма записи инструкций, когда названия команд пишутся большими буквами, 
  а названия таблиц, колонок и др. — маленькими, позволяет быстро определять назначение производимой с данными операции.
</p>
<h2 id="section5">Что такое таблица?</h2>
<p>
Данные в СУБД хранятся в объектах БД, называемых таблицами (tables). Таблица, как правило, представляет собой коллекцию связанных между собой данных и состоит из определенного количества колонок и строк.
Таблица — это самая распространенная и простая форма хранения данных в РБД. Вот пример таблицы с пользователями (users):
<table border="1" cellpadding="5" cellspacing="0">
  <tr>
    <th>userId</th>
    <th>userName</th>
    <th>age</th>
    <th>city</th>
    <th>status</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Igor</td>
    <td>25</td>
    <td>Moscow</td>
    <td>active</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Vika</td>
    <td>26</td>
    <td>Ekaterinburg</td>
    <td>inactive</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Elena</td>
    <td>27</td>
    <td>Ekaterinburg</td>
    <td>active</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Oleg</td>
    <td>28</td>
    <td>Moscow</td>
    <td>inactive</td>
  </tr>
</table>
</p>
<h2 id="section6">Что такое поле?</h2>
<p>
Каждая таблица состоит из небольших частей — полей (fields). Полями в таблице users являются userId, userName, age, city и status. 
Поле — это колонка таблицы, предназначенная для хранения определенной информации о каждой записи в таблице.
Обратите внимание: вместо userId и userName можно было бы использовать id и name, соответственно. 
Но при работе с несколькими объектами, содержащими свойство id, бывает сложно понять, какому объекту принадлежит идентификатор, особенно, если вы, как и я, 
часто прибегаете к деструктуризации. Что касается слова name, то оно часто оказывается зарезервизованным, 
т.е. уже используется в среде, в которой выполняется код, поэтому я стараюсь его не использовать.
</p>
<h2 id="section7">Что такое запись или строка?</h2>
<p>
Запись или строка (record/row) — это любое единичное вхождение (entry), существующее в таблице. В таблице users 5 записей. Проще говоря, запись — это горизонтальное вхождение в таблице.
</p>
<h2 id="section8">Что такое колонка?</h2>
<p>Колонка (column) — это вертикальное вхождение в таблице, содержащее всю информацию, связанную с определенным полем. 
В таблице users одной из колонок является city, которая содержит названия городов, в которых проживают пользователи.
</p>
<h2 id="section9">Что такое нулевое значение?</h2>
<p>
Нулевое значение (NULL) — это значение поля, которое является пустым, т.е. нулевое значение — это значение поля, не имеющего значения. 
Важно понимать, что нулевое значение отличается от значения 0 и от значения поля, содержащего пробелы (`). Поле с нулевым значением - это такое поля, которое осталось пустым при создании записи. 
Также, следует учитывать, что в некоторых СУБД пустая строка ('') — этоNULL`, а в некоторых — это разные значения.
</p>
<h2 id="section10">Ограничения</h2>
<p>
Ограничения (constraints) — это правила, применяемые к данным. Они используются для ограничения данных, которые могут быть записаны в таблицу. Это обеспечивает точность и достоверность данных в БД.
Ограничения могут устанавливаться как на уровне колонки, так и на уровне таблицы.
Среди наиболее распространенных ограничений можно назвать следующие:
<ul>
  <li><b>NOT NULL</b> — колонка не может иметь нулевое значение</li>
  <li><b>DEFAULT</b> — значение колонки по умолчанию</li>
  <li><b>UNIQUE</b> — все значения колонки должны быть уникальными</li>
  <li><b>PRIMARY KEY</b> — первичный или основной ключ, уникальный идентификатор записи в текущей таблице</li>
  <li><b>FOREIGN KEY</b> — внешний ключ, уникальный идентификатор записи в другой таблице (таблице, связанной с текущей)</li>
  <li><b>CHECK</b> — все значения в колонке должны удовлетворять определенному условию</li>
  <li><b>INDEX</b> — быстрая запись и извлечение данных</li>
</ul>
Любое ограничение может быть удалено с помощью команды ALTER TABLE и DROP CONSTRAINT + название ограничения. 
Некоторые реализации предоставляют сокращения для удаления ограничений и возможность отключать ограничения вместо их удаления.
</p>
<h2 id="section11">Целостность данных</h2>
<p>
В каждой СУБД существуют следующие категории целостности данных:
<ul>
  <li>целостность объекта (Entity Integrity) — в таблице не должно быть дубликатов (двух и более строк с одинаковыми значениями)</li>
  <li>целостность домена (Domain Integrity) — фильтрация значений по типу, формату или диапазону</li>
  <li>целостность ссылок (Referential integrity) — строки, используемые другими записями (строки, на которые в других записях имеются ссылки), не могут быть удалены</li>
  <li>целостность, определенная пользователем (User-Defined Integrity) — дополнительные правила</li>
</ul>
</p>
<h2 id="section12">Нормализация БД</h2>
<p>Нормализация — это процесс эффективной организации данных в БД. 
Существует две главных причины, обуславливающих необходимость нормализации:
<ul>
  <li>предотвращение записи в БД лишних данных, например, хранения одинаковых данных в разных таблицах</li>
  <li>обеспечение "оправданной" связи между данными</li>
</ul> 
Нормализация предполагает соблюдение нескольких форм. Форма — это формат структурирования БД. 
Существует три главных формы: первая, вторая и, соответственно, третья. 
Я не буду вдаваться в подробности об этих формах, при желании, вы без труда найдете необходимую информацию.
</p>
<h2 id="section13">Синтаксис SQL</h2>
<p>
Синтаксис — это уникальный набор правил и рекомендаций. Все инструкции SQL должны начинаться с ключевого слова, 
такого как SELECT, INSERT, UPDATE, DELETE, ALTER, DROP, CREATE, USE, SHOW и т.п. и заканчиваться точкой с запятой (;) 
(точка с запятой не входит в синтаксис SQL, но ее наличия, как правило, требуют консольные клиенты СУБД для обозначения окончания ввода команды). 
SQL не чувствителен к регистру, т.е. SELECT, select и SeLeCt являются идентичными инструкицями. Исключением из этого правила является MySQL, где учитывается регистр в названии таблицы.
<ul>
  <h3>Примеры синтаксиса</h3>
  <h3>Выборка данных</h3>
    <li>SELECT col1, col2, ...colN FROM tableName;</li>
    <li>SELECT DISTINCT col1, col2, ...colN FROM tableName;</li>
    <li>SELECT col1, col2, ...colN FROM tableName WHERE condition;</li>
    <li>SELECT col1, col2, ...colN FROM tableName WHERE condition1 AND|OR condition2;</li>
    <li>SELECT col2, col2, ...colN FROM tableName WHERE colName IN (val1, val2, ...valN);</li>
    <li>SELECT col1, col2, ...colN FROM tableName WHERE colName BETWEEN val1 AND val2;</li>
    <li>SELECT col1, col2, ...colN FROM tableName WHERE colName LIKE pattern;</li>
    <li>SELECT col1, col2, ...colN FROM tableName WHERE condition ORDER BY colName [ASC|DESC];</li>
    <li>SELECT SUM(colName) FROM tableName WHERE condition GROUP BY colName;</li>
    <li>SELECT COUNT(colName) FROM tableName WHERE condition;</li>
    <li>SELECT SUM(colName) FROM tableName WHERE condition GROUP BY colName HAVING (function condition);</li>
  <h3>Создание таблицы</h3>
    <li>CREATE TABLE tableName (
            col1 datatype,
            col2 datatype,
            ...
            colN datatype,
            PRIMARY KEY (одна или более колонка)
    );</li>
  <h3>Удаление таблицы</h3>
      <li>DROP TABLE tableName;</li>
  <h3>Работа с индексами</h3>
      <li>CREATE UNIQUE INDEX indexName ON tableName (col1, col2, ...colN);</li>
      <li>ALTER TABLE tableName DROP INDEX indexName;</li>
  <h3>Описание структуры таблицы</h3>
      <li>DESC tableName;</li>
  <h3>Очистка таблицы</h3>
      <li>TRUNCATE TABLE tableName;</li>
  <h3>Изменение структуры таблицы</h3>
      <li>ALTER TABLE tableName ADD|DROP|MODIFY colName [datatype];</li>
      <li>ALTER TABLE tableName RENAME TO newTableName;</li>
  <h3>Вставка значений</h3>
      <li>INSERT INTO tableName (col1, col2, ...colN) VALUES (val1, val2, ...valN);</li>
  <h3>Обновление записей</h3>
      <li>UPDATE tableName SET col1 = val1, col2 = val2, ...colN = valN [WHERE condition];</li>
  <h3>Удаление записей</h3>
      <li>DELETE FROM tableName WHERE condition;</li>
  <h3>Работа с базами данных</h3>
      <li>CREATE DATABASE [IF NOT EXISTS] dbName;</li>
      <li>DROP DATABASE [IF EXISTS] dbName;</li>
      <li>USE dbName;</li>
  <h3>Транзакции</h3>
      <li>COMMIT;</li>
      <li>ROLLBACK;</li>
</ul>
</p>
<h2 id="section14">Типы данных</h2>
<p>Каждая колонка, переменная и выражение в SQL имеют определенный тип данных (data type).
Основные категории типов данных:
<h3>Точные числовые</h3>
    <table>
        <thead>
            <tr>
                <th>Тип данных</th>
                <th>От</th>
                <th>До</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>bigint</td>
                <td>-9,223,372,036,854,775,808</td>
                <td>9,223,372,036,854,775,807</td>
            </tr>
            <tr>
                <td>int</td>
                <td>-2,147,483,648</td>
                <td>2,147,483,647</td>
            </tr>
            <tr>
                <td>smallint</td>
                <td>-32,768</td>
                <td>32,767</td>
            </tr>
            <tr>
                <td>tinyint</td>
                <td>0</td>
                <td>255</td>
            </tr>
            <tr>
                <td>bit</td>
                <td>0</td>
                <td>1</td>
            </tr>
            <tr>
                <td>decimal</td>
                <td>-10^38 +1</td>
                <td>10^38 -1</td>
            </tr>
            <tr>
                <td>numeric</td>
                <td>-10^38 +1</td>
                <td>10^38 -1</td>
            </tr>
            <tr>
                <td>money</td>
                <td>-922,337,203,685,477.5808</td>
                <td>+922,337,203,685,477.5807</td>
            </tr>
            <tr>
                <td>smallmoney</td>
                <td>-214,748.3648</td>
                <td>+214,748.3647</td>
            </tr>
        </tbody>
    </table>
<h3>Приблизительные числовые</h3> 
<table>
        <thead>
            <tr>
                <th>Тип данных</th>
                <th>От</th>
                <th>До</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>float</td>
                <td>-1.79E + 308</td>
                <td>1.79E + 308</td>
            </tr>
            <tr>
                <td>real</td>
                <td>-3.40E + 38</td>
                <td>3.40E + 38</td>
            </tr>
        </tbody>
</table>
<h3>Дата и время</h3>
<table>
        <thead>
            <tr>
                <th>Тип данных</th>
                <th>От</th>
                <th>До</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>datetime</td>
                <td>Jan 1, 1753</td>
                <td>Dec 31, 9999</td>
            </tr>
            <tr>
                <td>smalldatetime</td>
                <td>Jan 1, 1900</td>
                <td>Jun 6, 2079</td>
            </tr>
            <tr>
                <td>date</td>
                <td colspan="2">Дата сохраняется в виде June 30, 1991</td>
            </tr>
            <tr>
                <td>time</td>
                <td colspan="2">Время сохраняется в виде 12:30 P.M.</td>
            </tr>
        </tbody>
</table>
<h3>Строковые символьные</h3>
    <table>
        <thead>
            <tr>
                <th>N</th>
                <th>Тип данных</th>
                <th>Описание</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>char</td>
                <td>Строка длиной до 8,000 символов (не-юникод символы, фиксированной длины)</td>
            </tr>
            <tr>
                <td>2</td>
                <td>varchar</td>
                <td>Строка длиной до 8,000 символов (не-юникод символы, переменной длины)</td>
            </tr>
            <tr>
                <td>3</td>
                <td>text</td>
                <td>Не-юникод данные переменной длины, длиной до 2,147,483,647 символов</td>
            </tr>
        </tbody>
    </table>
<h3>Строковые символьные (юникод)</h3>
    <table>
        <thead>
            <tr>
                <th>N</th>
                <th>Тип данных</th>
                <th>Описание</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>nchar</td>
                <td>Строка длиной до 4,000 символов (юникод символы, фиксированной длины)</td>
            </tr>
            <tr>
                <td>2</td>
                <td>nvarchar</td>
                <td>Строка длиной до 4,000 символов (юникод символы, переменной длины)</td>
            </tr>
            <tr>
                <td>3</td>
                <td>ntext</td>
                <td>Юникод данные переменной длины, длиной до 1,073,741,823 символов</td>
            </tr>
        </tbody>
    </table>
<h3>Бинарные</h3>
    <table>
        <thead>
            <tr>
                <th>N</th>
                <th>Тип данных</th>
                <th>Описание</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>binary</td>
                <td>Данные размером до 8,000 байт (фиксированной длины)</td>
            </tr>
            <tr>
                <td>2</td>
                <td>varbinary</td>
                <td>Данные размером до 8,000 байт (переменной длины)</td>
            </tr>
            <tr>
                <td>3</td>
                <td>image</td>
                <td>Данные размером до 2,147,483,647 байт (переменной длины)</td>
            </tr>
        </tbody>
    </table>
<h3>Смешанные</h3>
    <table>
        <thead>
            <tr>
                <th>N</th>
                <th>Тип данных</th>
                <th>Описание</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>timestamp</td>
                <td>Уникальные числа, обновляющиеся при каждом изменении строки</td>
            </tr>
            <tr>
                <td>2</td>
                <td>uniqueidentifier</td>
                <td>Глобально-уникальный идентификатор (GUID)</td>
            </tr>
            <tr>
                <td>3</td>
                <td>cursor</td>
                <td>Объект курсора</td>
            </tr>
            <tr>
                <td>4</td>
                <td>table</td>
                <td>Промежуточный результат, предназначенный для дальнейшей обработки</td>
            </tr>
        </tbody>
    </table>
</p>
<h2 id="section15">Операторы</h2>
<p>
Оператор (operators) — это ключевое слово или символ, которые, в основном, используются в инструкциях WHERE для выполнения каких-либо операций. 
Они используются как для определения условий, так и для объединения нескольких условий в инструкции.
В дальнейших примерах мы будем исходить из предположения, что переменная a имеет значение 10, а b — 20.
<h3>Арифметические</h3>
    <table>
        <thead>
            <tr>
                <th>Оператор</th>
                <th>Описание</th>
                <th>Пример</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>+ (сложение)</td>
                <td>Сложение значений</td>
                <td>a + b = 30</td>
            </tr>
            <tr>
                <td>— (вычитание)</td>
                <td>Вычитание правого операнда из левого</td>
                <td>b — a = 10</td>
            </tr>
            <tr>
                <td>* (умножение)</td>
                <td>Умножение значений</td>
                <td>a * b = 200</td>
            </tr>
            <tr>
                <td>/ (деление)</td>
                <td>Деление левого операнда на правый</td>
                <td>b / a = 2</td>
            </tr>
            <tr>
                <td>% (деление с остатком/по модулю)</td>
                <td>Деление левого операнда на правый с остатком (возвращается остаток)</td>
                <td>b % a = 0</td>
            </tr>
        </tbody>
    </table>
<h3>Операторы сравнения</h3>
    <table>
        <thead>
            <tr>
                <th>Оператор</th>
                <th>Описание</th>
                <th>Пример</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>=</td>
                <td>Определяет равенство значений</td>
                <td>a = b -> false</td>
            </tr>
            <tr>
                <td>!=</td>
                <td>Определяет НЕравенство значений</td>
                <td>a != b -> true</td>
            </tr>
            <tr>
                <td>&lt;&gt;</td>
                <td>Определяет НЕравенство значений</td>
                <td>a &lt;&gt; b -> true</td>
            </tr>
            <tr>
                <td>&gt;</td>
                <td>Значение левого операнда больше значения правого операнда?</td>
                <td>a &gt; b -> false</td>
            </tr>
            <tr>
                <td>&lt;</td>
                <td>Значение левого операнда меньше значения правого операнда?</td>
                <td>a &lt; b -> true</td>
            </tr>
            <tr>
                <td>&gt;=</td>
                <td>Значение левого операнда больше или равно значению правого операнда?</td>
                <td>a &gt;= b -> false</td>
            </tr>
            <tr>
                <td>&lt;=</td>
                <td>Значение левого операнда меньше или равно значению правого операнда?</td>
                <td>a &lt;= b -> true</td>
            </tr>
            <tr>
                <td>!&lt;</td>
                <td>Значение левого операнда НЕ меньше значения правого операнда?</td>
                <td>a !&lt; b -> false</td>
            </tr>
            <tr>
                <td>!&gt;</td>
                <td>Значение левого операнда НЕ больше значения правого операнда?</td>
                <td>a !&gt; b -> true</td>
            </tr>
        </tbody>
    </table>
<h3>Логические операторы</h3>
    <table>
        <thead>
            <tr>
                <th>N</th>
                <th>Оператор</th>
                <th>Описание</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>ALL</td>
                <td>Сравнивает все значения</td>
            </tr>
            <tr>
                <td>2</td>
                <td>AND</td>
                <td>Объединяет условия (все условия должны совпадать)</td>
            </tr>
            <tr>
                <td>3</td>
                <td>ANY</td>
                <td>Сравнивает одно значение с другим, если последнее совпадает с условием</td>
            </tr>
            <tr>
                <td>4</td>
                <td>BETWEEN</td>
                <td>Проверяет вхождение значения в диапазон от минимального до максимального</td>
            </tr>
            <tr>
                <td>5</td>
                <td>EXISTS</td>
                <td>Определяет наличие строки, соответствующей определенному критерию</td>
            </tr>
            <tr>
                <td>6</td>
                <td>IN</td>
                <td>Выполняет поиск значения в списке значений</td>
            </tr>
            <tr>
                <td>7</td>
                <td>LIKE</td>
                <td>Сравнивает значение с похожими с помощью операторов подстановки</td>
            </tr>
            <tr>
                <td>8</td>
                <td>NOT</td>
                <td>Инвертирует (меняет на противоположное) смысл других логических операторов, например, NOT EXISTS, NOT IN и т.д.</td>
            </tr>
            <tr>
                <td>9</td>
                <td>OR</td>
                <td>Комбинирует условия (одно из условий должно совпадать)</td>
            </tr>
            <tr>
                <td>10</td>
                <td>IS NULL</td>
                <td>Определяет, является ли значение нулевым</td>
            </tr>
            <tr>
                <td>11</td>
                <td>UNIQUE</td>
                <td>Определяет уникальность строки</td>
            </tr>
        </tbody>
    </table>
</p>
<h2 id="section16">Выражения</h2>
<p>
Выражение (expression) — это комбинация значений, операторов и функций для оценки (вычисления) значения. 
Выражения похожи на формулы, написанные на языке запросов. Они могут использоваться для извлечения из БД определенного набора данных.
Базовый синтаксис выражения выглядит так:
SELECT col1, col2, ...colN
FROM tableName
WHERE [condition|expression];
Существуют различные типы выражений: логические, числовые и выражения для работы с датами.
<h3>Логические</h3>
Логические выражения извлекают данные на основе совпадения с единичным значением.
SELECT col1, col2, ...colN
FROM tableName
WHERE выражение для поиска совпадения с единичным значением;
Предположим, что в таблице users имеются следующие записи:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
                <th>city</th>
                <th>status</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>25</td>
                <td>Moscow</td>
                <td>active</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
                <td>Ekaterinburg</td>
                <td>inactive</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
                <td>Ekaterinburg</td>
                <td>active</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Oleg</td>
                <td>28</td>
                <td>Moscow</td>
                <td>inactive</td>
            </tr>
        </tbody>
    </table>

Выполняем поиск активных пользователей:
SELECT * FROM users WHERE status = active;
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
                <th>city</th>
                <th>status</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>25</td>
                <td>Moscow</td>
                <td>active</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
                <td>Ekaterinburg</td>
                <td>active</td>
            </tr>
        </tbody>
    </table>
<h3>Числовые</h3>

Используются для выполнения арифметических операций в запросе.
SELECT numericalExpression as operationName
[FROM tableName
WHERE condition];
Простой пример использования числового выражения:
SELECT (10 + 5) AS addition;
Результат: 15
Существует несколько встроенных функций, таких как count(), sum(), avg(), min(), max() и др. для выполнения так называемых агрегирующих вычислений данных таблицы или колонки.
SELECT COUNT(*) AS records FROM users;
Результат:4
<ul>
        <li><strong>AVG</strong> — вычисляет среднее значение</li>
        <li><strong>SUM</strong> — вычисляет сумму значений</li>
        <li><strong>MIN</strong> — вычисляет наименьшее значение</li>
        <li><strong>MAX</strong> — вычисляет наибольшее значение</li>
        <li><strong>COUNT</strong> — вычисляет количество записей в таблице</li>
</ul>
Также существует несколько встроенных функций для работы со строками:
<ul>
        <li><strong>CONCAT</strong> — объединение строк</li>
        <li><strong>LENGTH</strong> — возвращает количество символов в строке</li>
        <li><strong>TRIM</strong> — удаляет пробелы в начале и конце строки</li>
        <li><strong>SUBSTRING</strong> — извлекает подстроку из строки</li>
        <li><strong>REPLACE</strong> — заменяет подстроку в строке</li>
        <li><strong>LOWER</strong> — переводит символы строки в нижний регистр</li>
        <li><strong>UPPER</strong> — переводит символы строки в верхний регистр и т.д.</li>
</ul>
с числами:
<ul>
        <li><strong>ROUND</strong> — округляет число</li>
        <li><strong>TRUNCATE</strong> — обрезает дробное число до указанного количества знаков после запятой</li>
        <li><strong>CEILING</strong> — возвращает наименьшее целое число, которое больше или равно текущему значению</li>
        <li><strong>FLOOR</strong> — возвращает наибольшее целое число, которое меньше или равно текущему значению</li>
        <li><strong>POWER</strong> — возводит число в указанную степень</li>
        <li><strong>SQRT</strong> — возвращает квадратный корень числа</li>
        <li><strong>RAND</strong> — генерирует случайное число с плавающей точкой в диапазоне от 0 до 1</li>
</ul>
<h3>Выражения для работы с датами</h3>
Эти выражения, как правило, возвращают текущую дату и время.
SELECT CURRENT_TIMESTAMP;
Результат:2021-06-20 12:45:00
CURRENT_TIMESTAMP — это и выражение, и функция (CURRENT_TIMESTAMP()). Другая функция для получения текущей даты и времени — NOW().
Другие функции для получения текущей даты и времени:
<ul>
        <li><strong>CURDATE/CURRENT_DATE</strong> — возвращает текущую дату</li>
        <li><strong>CURTIME/CURRENT_TIME</strong> — возвращает текущее время и т.д.</li>
</ul>
Функции для разбора даты и времени:
<ul>
        <li><strong>DAYOFMONTH(date)</strong> — возвращает день месяца в виде числа</li>
        <li><strong>DAYOFWEEK(date)</strong> — возвращает день недели в виде числа</li>
        <li><strong>DAYOFYEAR(date)</strong> — возвращает номер дня в году</li>
        <li><strong>MONTH(date)</strong> — возвращает месяц</li>
        <li><strong>YEAR(date)</strong> — возвращает год</li>
        <li><strong>LAST_DAY(date)</strong> — возвращает последний день месяца в виде даты</li>
        <li><strong>HOUR(time)</strong> — возвращает час</li>
        <li><strong>MINUTE(time)</strong> — возвращает минуты</li>
        <li><strong>SECOND(time)</strong> — возвращает секунды и др.</li>
</ul>
Функции для манипулирования датами:
<ul>
        <li><strong>DATE_ADD(date, interval)</strong> — выполняет сложение даты и определенного временного интервала</li>
        <li><strong>DATE_SUB(date, interval)</strong> — выполняет вычитание из даты определенного временного интервала</li>
        <li><strong>DATEDIFF(date1, date2)</strong> — возвращает разницу в днях между двумя датами</li>
        <li><strong>TO_DAYS(date)</strong> — возвращает количество дней с 0-го дня года</li>
        <li><strong>TIME_TO_SEC(time)</strong> — возвращает количество секунд с полуночи и др.</li>
</ul>
Для форматирования даты и времени используются функции DATE_FORMAT(date, format) и TIME_FORMAT(date, format), соответственно.
</p>
<h2 id="section17">Создание БД</h2>
<p>
Для создания БД используется инструкция CREATE DATABASE.
CREATE DATABASE dbName;
-- или
CREATE DATABASE IF NOT EXISTS dbName;
Условие IF NOT EXISTS позволяет избежать получения ошибки при попытке создания БД, которая уже существует.
Название БД должно быть уникальным в пределах СУБД.
Создаем БД testDB:
CREATE DATABASE testDB;
Получаем список БД:
SHOW DATABASES;
Результат:
    <table>
        <thead>
            <tr>
                <th>Database</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>information_schema</td>
            </tr>
            <tr>
                <td>postgres</td>
            </tr>
            <tr>
                <td>testDB</td>
            </tr>
        </tbody>
    </table>
</p>
<h2 id="section18">Удаление БД</h2>
<p>
Для удаления БД используется инструкция DROP DATABASE.
DROP DATABASE dbName;
-- или
DROP DATABASE IF EXISTS dbName;
Условие IF EXISTS позволяет избежать получения ошибки при попытке удаления несуществующей БД.
Удаляем testDB:
DROP DATABASE testDB;
Обратите внимание: при удалении БД уничтожаются все данные, которые в ней хранятся, так что будьте предельно внимательны при использовании данной команды.
Проверяем, что БД удалена:
SHOW DATABASES;
Для получения списка таблиц используется инструкция SHOW TABLES.
Результат:
    <table>
        <thead>
            <tr>
                <th>Database</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>information_schema</td>
            </tr>
            <tr>
                <td>postgres</td>
            </tr>
        </tbody>
    </table>
</p>
<h2 id="section19">Выбор БД</h2>
<p>
При наличии нескольких БД, перед выполнением каких-либо операций, необходимо выбрать БД. Для этого используется инструкция USE.
USE dbName;
Предположим, что мы не удаляли testDB. Тогда мы можем выбрать ее так:
USE testDB;
</p>
<h2 id="section20">Создание таблицы</h2>
<p>
Создание таблицы предполагает указание названия таблицы и определение колонок таблицы и их типов данных. Для создания таблицы используется инструкция CREATE TABLE.
CREATE TABLE tableName (
  col1 datatype,
  col2 datatype,
  ...
  colN datatype,
  PRIMARY KEY (хотя бы одна колонка)
);
Для создания таблицы путем копирования другой таблицы используется сочетание CREATE TABLE и SELECT.
Пример создания таблицы users, где первичным ключом являются идентификаторы пользователей, а поля для имени и возраста пользователя не могут быть нулевыми:
CREATE TABLE users (
  userId INT,
  userName VARCHAR(20)  NOT NULL,
  age INT           NOT NULL,
  city VARCHAR(20),
  status VARCHAR(8),
  PRIMARY KEY (id)
);
Проверяем, что таблица была создана:
DESC users;
Результат:
    <table>
        <thead>
            <tr>
                <th>Field</th>
                <th>Type</th>
                <th>Null</th>
                <th>Key</th>
                <th>Default</th>
                <th>Extra</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>userId</td>
                <td>int(11)</td>
                <td>NO</td>
                <td>PRI</td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>userName</td>
                <td>varchar(20)</td>
                <td>NO</td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>age</td>
                <td>int(11)</td>
                <td>NO</td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>city</td>
                <td>varchar(20)</td>
                <td>NO</td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>status</td>
                <td>varchar(8)</td>
                <td>YES</td>
                <td></td>
                <td>NULL</td>
                <td></td>
            </tr>
        </tbody>
    </table>
</p>
