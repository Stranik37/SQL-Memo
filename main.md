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
  <p>SELECT col1, col2, ...colN
  FROM tableName
  WHERE [condition|expression];
  </p>
Существуют различные типы выражений: логические, числовые и выражения для работы с датами.
<h3>Логические</h3>
Логические выражения извлекают данные на основе совпадения с единичным значением.
  <p>
  SELECT col1, col2, ...colN
  FROM tableName
  WHERE выражение для поиска совпадения с единичным значением;
  </p>
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
<p>SELECT numericalExpression as operationName
[FROM tableName
WHERE condition];</p>
Простой пример использования числового выражения:
<p>SELECT (10 + 5) AS addition;
Результат: 15</p>
Существует несколько встроенных функций, таких как count(), sum(), avg(), min(), max() и др. для выполнения так называемых агрегирующих вычислений данных таблицы или колонки.
<p>SELECT COUNT(*) AS records FROM users;</p>
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
<p>SELECT CURRENT_TIMESTAMP;</p>
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
<p>
CREATE TABLE users (
  userId INT,
  userName VARCHAR(20)  NOT NULL,
  age INT           NOT NULL,
  city VARCHAR(20),
  status VARCHAR(8),
  PRIMARY KEY (id)
);
</p>
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
<h2 id="section21">Удаление таблицы</h2>
Для удаления таблицы используется инструкция DROP TABLE.
Обратите внимание: при удалении таблицы, навсегда удаляются все хранящиеся в ней данные, индексы, триггеры, ограничения и разрешения, так что будьте предельно внимательны при использовании данной команды.
Удаляем таблицу users:
DROP TABLE users;
Теперь, если мы попытаемся получить описание users, то получим ошибку:
<p>DESC users;
-- ERROR 1146 (42S02): Table 'testDB.users' doesn't exist
</p>
<h2 id="section22">Добавление колонок</h2>
Для добавления в таблицу колонок используется инструкция INSERT INTO.
<p>
INSERT INTO tableName (col1, col2, ...colN)
VALUES (val1, val2, ...valN);
</p>
Названия колонок можно не указывать, однако, в этом случае значения должны перечисляться в правильном порядке.
<p>
INSERT INTO tableName VALUES (val1, val2, ...valN);
</p>
Во избежание ошибок, рекомендуется всегда перечислять названия колонок.
Предположим, что мы не удаляли таблицу users. Заполним ее пользователями:
<p>
INSERT INTO users (userId, userName, age, city, status)
VALUES (1, 'Igor', 25, 'Moscow', 'active');
</p>
<p>
INSERT INTO users (userId, userName, age, city, status)
VALUES (2, 'Vika', 26, 'Ekaterinburg', 'inactive');
</p>
<p>
INSERT INTO users (userId, userName, age, city, status)
VALUES (3, 'Elena', 27, 'Ekaterinburg', 'active');
</p>
В таблицу можно добавлять несколько строк за один раз.
<p>
INSERT INTO users (userId, userName, age, city, status)
VALUES
(1, 'Igor', 25, 'Moscow', 'active'),
(2, 'Vika', 26, 'Ekaterinburg', 'inactive'),
(3, 'Elena', 27, 'Ekaterinburg', 'active');
</p>
Также, как было отмечено, при добавлении строки названия полей можно опускать:
<p>
INSERT INTO users
VALUES (4, 'Oleg', 28, 'Moscow', 'inactive');
</p>
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
<h3>Заполнение таблицы с помощью другой таблицы</h3>
<p>
INSERT INTO tableName [(col1, col2, ...colN)]
  SELECT col1, col2, ...colN
  FROM anotherTable
  [WHERE condition];
</p>
<h2 id="section23">Выборка полей</h2>
Для выборки полей из таблицы используется инструкция SELECT. Она возвращает данные в виде результирующей таблицы (результирующего набора, result-set).
<p>
SELECT col1, col2, ...colN
FROM tableName;
</p>
Для выборки всех полей используется такой синтаксис:
SELECT * FROM tableName;
Произведем выборку полей userId, userName и age из таблицы users:
SELECT userId, userName, age FROM users;
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>25</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Oleg</td>
                <td>28</td>
            </tr>
        </tbody>
    </table>
<h2 id="section24">Предложение WHERE</h2>
Предложение WHERE используется для фильтрации возвращаемых данных. Оно используется совместно с SELECT, UPDATE, DELETE и другими инструкциями.
<p>
SELECT col1, col2, ...col2
FROM tableName
WHERE condition;
</p>
Условие (condition), которому должны удовлетворять возвращаемые записи, определяется с помощью операторов сравнения или логических операторов типа >, <, =, NOT, LIKE и т.д.
Сделаем выборку полей userId, userName и age активных пользователей:
<p>
SELECT userId, userName, age
FROM users
WHERE status = 'active';
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>25</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
            </tr>
        </tbody>
    </table>
Сделаем выборку полей userId, age и city пользователя с именем Vika.
<p>
SELECT userId, age, city
FROM users
WHERE userName = 'Vika';
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>age</th>
                <th>city</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>2</td>
                <td>26</td>
                <td>Ekaterinburg</td>
            </tr>
        </tbody>
    </table>
Обратите внимание: строки в предложении WHERE должны быть обернуты в одинарные кавычки (''), а числа, напротив, указываются как есть.
<h2 id="section25">Операторы AND и OR</h2>
Конъюнктивный оператор AND и дизъюнктивный оператор OR используются для соединения нескольких условий при фильтрации данных.
<h3>AND</h3>
<p>
SELECT col1, col2, ...colN
FROM tableName
WHERE condition1 AND condition2 ...AND conditionN;
</p>
Возвращаемые записи должны удовлетворять всем указанным условиям.
Сделаем выборку полей userId, userName и age активных пользователей старше 26 лет:
<p>
SELECT userId, userName, age
FROM users
WHERE status = active AND age > 26;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>AGE</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
            </tr>
        </tbody>
    </table>
<h3>OR</h3>
<p>
SELECT col1, col2, ...colN
FROM tableName
WHERE condition1 OR condition2 ...OR conditionN;
</p>
Возвращаемые записи должны удовлетворять хотя бы одному условию.
Сделаем выборку тех же полей неактивных пользователей или пользователей, младше 27 лет:
<p>
SELECT userId, userName, age
FROM users
WHERE status = inactive OR age < 27;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>25</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
            </tr>
        </tbody>
    </table>
<h2 id="section26">Обновление полей</h2>
Для обновления полей используется инструкция UPDATE ... SET. Эта инструкция, обычно, используется в сочетании с предложением WHERE.
<p>
UPDATE tableName
SET col1 = val1, col2 = val2, ...colN = valN
[WHERE condition];
</p>
Обновим возраст пользователя с именем Igor:
<p>
UPDATE users
SET age = 30
WHERE username = 'Igor';
</p>
Если в данном случае опустить WHERE, то будет обновлен возраст всех пользователей.
<h2 id="section27">Удаление записей</h2>
Для удаления записей используется инструкция DELETE. Эта инструкция также, как правило, используется в сочетании с предложением WHERE.
<p>
DELETE FROM tableName
[WHERE condition];
</p>
Удалим неактивных пользователей:
<p>
DELETE FROM users
WHERE status = 'inactive';
</p>
Если в данном случае опустить WHERE, то из таблицы users будут удалены все записи.
<h2 id="section28">Предложения LIKE и REGEX</h2>
<h3>LIKE</h3>
Предложение LIKE используется для сравнения значений с помощью операторов с подстановочными знаками. Существует два вида таких операторов:
проценты (%)
нижнее подчеркивание (_)
% означает 0, 1 или более символов. _ означает точно 1 символ.
<p>
SELECT col1, col2, ...colN FROM tableName
WHERE col LIKE 'xxx%'
-- или
WHERE col LIKE '%xxx%'
-- или
WHERE col LIKE '%xxx'
-- или
WHERE col LIKE 'xxx_'
-- и т.д.
</p>
Примеры:
    <table>
        <thead>
            <tr>
                <th>N</th>
                <th>Инструкция</th>
                <th>Результат</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>WHERE col LIKE 'foo%'</td>
                <td>Любые значения, начинающиеся с foo</td>
            </tr>
            <tr>
                <td>2</td>
                <td>WHERE col LIKE '%foo%'</td>
                <td>Любые значения, содержащие foo</td>
            </tr>
            <tr>
                <td>3</td>
                <td>WHERE col LIKE '_oo%'</td>
                <td>Любые значения, содержащие oo на второй и третьей позициях</td>
            </tr>
            <tr>
                <td>4</td>
                <td>WHERE col LIKE 'f%%'</td>
                <td>Любые значения, начинающиеся с f и состоящие как минимум из 1 символа</td>
            </tr>
            <tr>
                <td>5</td>
                <td>WHERE col LIKE '%oo'</td>
                <td>Любые значения, оканчивающиеся на oo</td>
            </tr>
            <tr>
                <td>6</td>
                <td>WHERE col LIKE '_o%o'</td>
                <td>Любые значения, содержащие o на второй позиции и оканчивающиеся на o</td>
            </tr>
            <tr>
                <td>7</td>
                <td>WHERE col LIKE 'f_o'</td>
                <td>Любые значения, содержащие f и o на первой и третьей позициях, соответственно, и состоящие из трех символов</td>
            </tr>
        </tbody>
    </table>

Сделаем выборку неактивных пользователей:
<p>
SELECT * FROM users
WHERE status LIKE 'in%';
</p>
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
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
                <td>Ekaterinburg</td>
                <td>inactive</td>
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
Сделаем выборку пользователей 30 лет и старше:
<p>
SELECT * FROM users
WHERE age LIKE '3_';
</p>
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
                <td>30</td>
                <td>Moscow</td>
                <td>active</td>
            </tr>
        </tbody>
    </table>
<h3>REGEX</h3>
Предложение REGEX позволяет определять регулярное выражение, которому должна соответствовать запись.
<p>
SELECT col1, col2, ...colN FROM tableName
WHERE colName REGEXP регулярное выражение;
</p>
В регулярное выражении могут использоваться следующие специальные символы:
    <ul>
        <li><strong>^</strong> — начало строки</li>
        <li><strong>$</strong> — конец строки</li>
        <li><strong>.</strong> — любой символ</li>
        <li><strong>[символы]</strong> — любой из указанных в скобках символов</li>
        <li><strong>[начало-конец]</strong> — любой символ из диапазона</li>
        <li><strong>|</strong> — разделяет шаблоны</li>
    </ul>
Сделаем выборку пользователей с именами Igor и Vika:
<p>
SELECT * FROM users
WHERE userName REGEXP 'Igor|Vika';
</p>
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
                <td>30</td>
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
        </tbody>
    </table>
<h2 id="section29">Предложение TOP/LIMIT/ROWNUM</h2>
Данные предложения позволяют извлекать указанное количество или процент записей с начала таблицы. Разные СУБД поддерживают разные предложения.
<p>
SELECT TOP number|percent col1, col2, ...colN
FROM tableName
[WHERE condition];
</p>
Сделаем выборку первых трех пользователей:
SELECT TOP 3 * FROM users;
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
                <td>30</td>
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
        </tbody>
    </table>
В mysql:
<p>
SELECT * FROM users
LIMIT 3, [offset];
</p>
Параметр offset (смещение) определяет количество пропускаемых записей. Например, так можно извлечь первых двух пользователей, начиная с третьего:
<p>
SELECT * FROM users
LIMIT 2, 2;
</p>
В oracle:
<p>
SELECT * FROM users
WHERE ROWNUM <= 3;
</p>
<h2 id="section30">Предложения ORDER BY и GROUP BY</h2>
<h3>ORDER BY</h3>
Предложение ORDER BY используется для сортировки данных по возрастанию (ASC) или убыванию (DESC). Многие СУБД по умолчанию выполняют сортировку по возрастанию.
<p>
SELECT col1, col2, ...colN
FROM tableName
[WHERE condition]
[ORDER BY col1, col2, ...colN] [ASC | DESC];
</p>
Обратите внимание: колонки для сортировки должны быть указаны в списке колонок для выборки.
Сделаем выборку пользователей, отсортировав их по городу и возрасту:
<p>
SELECT * FROM users
ORDER BY city, age;
</p>
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
                <td>1</td>
                <td>Igor</td>
                <td>25</td>
                <td>Moscow</td>
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
Теперь выполним сортировку по убыванию:
<p>
SELECT * FROM users
ORDER BY city, age DESC;
</p>
Определим собственный порядок сортировки по убыванию:
<p>
SELECT * FROM users
ORDER BY (CASE city
  WHEN 'Ekaterinburg' THEN 1
  WHEN 'Moscow' THEN 2
ELSE 100 END) ASC, city DESC;
</p>
<h3>GROUP BY</h3>
Предложение GROUP BY используется совместно с инструкцией SELECT для группировки записей. Оно указывается после WHERE и перед ORDER BY.
<p>
SELECT col1, col2, ...colN
FROM tableName
WHERE condition
GROUP BY col1, col2, ...colN
ORDER BY col1, col2, ...colN;
</p>
Сгруппируем активных пользователей по городам:
<p>
SELECT city, COUNT(city) AS amount FROM users
WHERE status = active
GROUP BY city
ORDER BY city;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>city</th>
                <th>amount</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Ekaterinburg</td>
                <td>2</td>
            </tr>
            <tr>
                <td>Moscow</td>
                <td>2</td>
            </tr>
        </tbody>
    </table>
<h2 id="section31">Ключевое слово DISTINCT</h2>
Ключевое слово DISTINCT используется совместно с инструкцией SELECT для возврата только уникальных записей (без дубликатов).
<p>
SELECT DISTINCT col1, col2, ...colN
FROM tableName
[WHERE condition];
</p>
Сделаем выборку городов проживания пользователей:
<p>
SELECT DISTINCT city
FROM users;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>city</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Ekaterinburg</td>
            </tr>
            <tr>
                <td>Moscow</td>
            </tr>
        </tbody>
    </table>
<h2 id="section32">Соединения</h2>
Соединения (joins) используются для комбинации записей двух и более таблиц.
Предположим, что кроме users, у нас имеется таблица orders с заказами пользователей следующего содержания:
    <table>
        <thead>
            <tr>
                <th>orderId</th>
                <th>date</th>
                <th>userId</th>
                <th>amount</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>101</td>
                <td>2021-06-21 00:00:00</td>
                <td>2</td>
                <td>3000</td>
            </tr>
            <tr>
                <td>102</td>
                <td>2021-06-20 00:00:00</td>
                <td>2</td>
                <td>1500</td>
            </tr>
            <tr>
                <td>103</td>
                <td>2021-06-19 00:00:00</td>
                <td>3</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>104</td>
                <td>2021-06-18 00:00:00</td>
                <td>3</td>
                <td>1000</td>
            </tr>
        </tbody>
    </table>
Сделаем выборку полей userId, userName, age и amount из наших таблиц посредством их соединения:
<p>
SELECT userId, userName, age, amount
FROM users, orders
WHERE users.userId = orders.userId;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
                <th>amount</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
                <td>3000</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
                <td>1500</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
                <td>1000</td>
            </tr>
        </tbody>
    </table>
При соединении таблиц могут использоваться такие операторы, как =, <, >, <>, <=, >=, !=, BETWEEN, LIKE и NOT, однако наиболее распространенным является =.
Существуют разные типы объединений:
    <ul>
        <li><strong>INNER JOIN</strong> — возвращает записи, имеющиеся в обеих таблицах</li>
        <li><strong>LEFT JOIN</strong> — возвращает записи из левой таблицы, даже если такие записи отсутствуют в правой таблице</li>
        <li><strong>RIGHT JOIN</strong> — возвращает записи из правой таблицы, даже если такие записи отсутствуют в левой таблице</li>
        <li><strong>FULL JOIN</strong> — возвращает все записи объединяемых таблиц</li>
        <li><strong>CROSS JOIN</strong> — возвращает все возможные комбинации строк обеих таблиц</li>
        <li><strong>SELF JOIN</strong> — используется для объединения таблицы с самой собой</li>
    </ul>
<h2 id="section33">Предложение UNION</h2>
Предложение/оператор UNION используется для комбинации результатов двух и более инструкций SELECT. При этом, возвращаются только уникальные записи.
В случае с UNION, каждая инструкция SELECT должна иметь:
    <ul>
        <li>одинаковый набор колонок для выборки</li>
        <li>одинаковое количество выражений</li>
        <li>одинаковые типы данных колонок</li>
        <li>одинаковый порядок колонок</li>
    </ul>
Однако, они могут быть разной длины.
<p>
SELECT col1, col2, ...colN
FROM table1
[WHERE condition]

UNION

SELECT col1, col2, ...colN
FROM table2
[WHERE condition];
</p>
Объединим наши таблицы users и orders:
<p>
  SELECT userId, userName, amount, date
  FROM users
  LEFT JOIN orders
  ON users.useId = orders.userId
</p>
<p>
UNION
  SELECT userId, userName, amount, date
  FROM users
  RIGHT JOIN orders
  ON users.userId = orders.userId;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>amount</th>
                <th>date</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>NULL</td>
                <td>NULL</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>3000</td>
                <td>2021-06-21 00:00:00</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>1500</td>
                <td>2021-06-20 00:00:00</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>2000</td>
                <td>2021-06-19 00:00:00</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>1000</td>
                <td>2021-06-18 00:00:00</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Alex</td>
                <td>NULL</td>
                <td>NULL</td>
            </tr>
        </tbody>
    </table>
<h2 id="section34">Предложение UNION ALL</h2>
Предложение UNION ALL также используется для объединения результатов двух и более инструкций SELECT. При этом, возвращаются все записи, включая дубликаты.
<p>
SELECT col1, col2, ...colN
FROM table1
[WHERE condition]
</p>
UNION ALL
<p>
SELECT col1, col2, ...colN
FROM table2
[WHERE condition];
</p>
Существует еще два предложения, похожих на UNION:
    <ul>
        <li><strong>INTERSECT</strong> — используется для комбинации результатов двух и более SELECT, но возвращаются только строки из первого SELECT, совпадающие со строками из второго SELECT</li>
        <li><strong>EXCEPT|MINUS</strong> — возвращаются только строки из первого SELECT, отсутствующие во втором SELECT</li>
    </ul>
<h2 id="section35">Синонимы</h2>
Синонимы (aliases) позволяют временно изменять названия таблиц и колонок. "Временно" означает, что новое название используется только в текущем запросе, в БД название остается прежним.
Синтаксис синонима таблицы:
<p>
SELECT col1, col2, ...colN
FROM tableName AS aliasName
[WHERE condition];
</p>
Синтаксис синонима колонки:
<p>
SELECT colName AS aliasName
FROM tableName
[WHERE condition];
</p>
Пример использования синонимов таблиц:
<p>
SELECT U.userId, U.userName, U.age, O.amount
FROM users AS U, orders AS O
WHERE U.userId = O.userId;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>userId</th>
                <th>userName</th>
                <th>age</th>
                <th>amount</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
                <td>3000</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Vika</td>
                <td>26</td>
                <td>1500</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
                <td>1000</td>
            </tr>
        </tbody>
    </table>
Пример использования синонимов колонок:
<p>
SELECT userId AS user_id, userName AS user_name, age AS user_age
FROM users
WHERE status = active;
</p>
Результат:
    <table>
        <thead>
            <tr>
                <th>user_id</th>
                <th>user_name</th>
                <th>user_age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Igor</td>
                <td>30</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Elena</td>
                <td>27</td>
            </tr>
        </tbody>
    </table>
<h2 id="section36">Индексы</h2>
<h3>Создание индексов</h3>
Индексы — это специальные поисковые таблицы (lookup tables), которые используются движком БД в целях более быстрого извлечения данных. Проще говоря, индекс — это указатель или ссылка на данные в таблице.
Индексы ускоряют работу инструкции SELECT и предложения WHERE, но замедляют работу инструкций UPDATE и INSERT. Индексы могут создаваться и удаляться, не оказывая никакого влияния на данные.
Для создания индекса используется инструкция CREATE INDEX, позволяющая определять название индекса, индексируемые колонки и порядок индексации (по возрастанию или по убыванию).
К индексам можно применять ограничение UNIQUE для того, чтобы обеспечить их уникальность.
Синтаксис создания индекса:
CREATE INDEX indexName ON tableName
Синтаксис создания индекса для одной колонки:
<p>
CREATE INDEX indexName
ON tableName (colName);
</p>
Синтакис создания уникальных индексов (такие индексы используются не только для повышения производительности, но и для обеспечения согласованности данных):
<p>
CREATE UNIQUE INDEX indexName
ON tableName (colName);
</p>
Синтаксис создания индексов для нескольких колонок (композиционный индекс):
<p>
CREATE INDEX indexName
ON tableName (col1, col2, ...colN);
</p>
Решение о создании индексов для одной или нескольких колонок следует принимать на основе того, какие колонки будут часто использоваться в запросе WHERE в качестве условия для сортировки строк.
Для ограничений PRIMARY KEY и UNIQUE автоматически создаются неявные индексы.
<h3>Удаление индексов</h3>
Для удаления индексов используется инструкция DROP INDEX:
DROP INDEX indexName;
Несмотря на то, что индексы предназначены для повышения производительности БД, существуют ситуации, в которых их использования лучше избегать.
К таким ситуациям относится следующее:
    <ul>
        <li>индексы не должны использоваться в маленьких таблицах</li>
        <li>в таблицах, которые часто и в большом объеме обновляются или перезаписываются</li>
        <li>в колонках, которые содержат большое количество нулевых значений</li>
        <li>в колонках, над которыми часто выполняются операции</li>
    </ul>
<h2 id="section37">Обновление таблицы</h2>
Команда ALTER TABLE используется для добавления, удаления и модификации колонок существующей таблицы. Также эта команда используется для добавления и удаления ограничений.
Синтаксис:
    
    <p>-- добавление новой колонки</p>
    <p>ALTER TABLE tableName ADD colName datatype;</p>
    
    <p>-- удаление колонки</p>
    <p>ALTER TABLE tableName DROP COLUMN colName;</p>
    
    <p>-- изменение типа данных колонки</p>
    <p>ALTER TABLE tableName MODIFY COLUMN colName newDatatype;</p>
    
    <p>-- добавление ограничения `NOT NULL`</p>
    <p>ALTER TABLE tableName MODIFY colName datatype NOT NULL;</p>
    
    <p>-- добавление ограничения `UNIQUE`</p>
    <p>ALTER TABLE tableName</p>
    <p>ADD CONSTRAINT myUniqueConstraint UNIQUE (col1, col2, ...colN);</p>
    
    <p>-- добавление ограничения `CHECK`</p>
    <p>ALTER TABLE tableName</p>
    <p>ADD CONSTRAINT myUniqueConstraint CHECK (condition);</p>
    
    <p>-- добавление первичного ключа</p>
    <p>ALTER TABLE tableName</p>
    <p>ADD CONSTRAINT myPrimaryKey PRIMARY KEY (col1, col2, ...colN);</p>
    
    <p>-- удаление ограничения</p>
    <p>ALTER TABLE tableName</p>
    <p>DROP CONSTRAINT myUniqueContsraint;</p>
    
    <p>-- mysql</p>
    <p>ALTER TABLE tableName</p>
    <p>DROP INDEX myUniqueContsraint;</p>
    
    <p>-- удаление первичного ключа</p>
    <p>ALTER TABLE tableName</p>
    <p>DROP CONSTRAINT myPrimaryKey;</p>
    
    <p>-- mysql</p>
    <p>ALTER TABLE tableName</p>
    <p>DROP PRIMARY KEY;</p>

Добавляем в таблицу users новую колонку — пол пользователя:
ALTER TABLE users ADD sex char(1);
Удаляем эту колонку:
ALTER TABLE users DROP sex;
<h2 id="section38">Очистка таблицы</h2>
Команда TRUNCATE TABLE используется для очистки таблицы. Ее отличие от DROP TABLE состоит в том, что сохраняется структура таблицы (DROP TABLE полностью удаляет таблицу и все ее данные).
TRUNCATE TABLE tableName;
<p>
Очищаем таблицу users:
TRUNCATE TABLE users;
</p>
<p>
Проверяем, что users пустая:
SELECT * FROM users;
-- Empty set (0.00 sec)
</p>
<h2 id="section39">Представления</h2>
Представление (view) — это не что иное, как инструкция, записанная в БД под определенным названием. Другими словами, представление — это композиция таблицы в форме предварительно определенного запроса.
Представления могут содержать все или только некоторые строки таблицы. Представление может быть создано на основе одной или нескольких таблиц (это зависит от запроса для создания представления).
Представления — это виртутальные таблицы, позволяющие делать следующее:
Создание представления.
Для создания представления используется инструкция CREATE VIEW. Как было отмечено, представления могут создаваться на основе одной или нескольких таблиц, и даже на основе другого представления.
<p>
CREATE VIEW viewName AS
SELECT col1, col2, ...colN
FROM tableName
[WHERE condition];
</p>
Создаем представление для имен и возраста пользователей:
<p>
CREATE VIEW usersView AS
SELECT userName, age
FROM users;
</p>
Получаем данные с помощью представления:
    <ul>
        <li>структурировать данные способом, который пользователи находят наиболее естественным или интуитивно понятным</li>
        <li>ограничивать доступ к данным таким образом, что пользователь может просматривать и (иногда) модифицировать только то, что ему нужно и ничего более</li>
        <li>объединять данные из нескольких таблиц для формирования отчетов</li>
    </ul>
SELECT * FROM usersView;
Результат:
    <table>
        <thead>
            <tr>
                <th>userName</th>
                <th>age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Igor</td>
                <td>30</td>
            </tr>
            <tr>
                <td>Vika</td>
                <td>26</td>
            </tr>
            <tr>
                <td>Elena</td>
                <td>27</td>
            </tr>
            <tr>
                <td>Oleg</td>
                <td>28</td>
            </tr>
        </tbody>
    </table>
<h3><WITH CHECK OPTION/h3>
WITH CHECK OPTION — это настройка инструкции CREATE VIEW. Она позволяет обеспечить соответствие всех UPDATE и INSERT условию, определенном в представлении.
Если условие не удовлетворяется, выбрасывается исключение.
<p>
CREATE VIEW usersView AS
SELECT userName, age
FROM users
WHERE age IS NOT NULL
WITH CHECK OPTION;
</p>
<h3>Обновление представления</h3>
Представление может быть обновлено при соблюдении следующих условий:
    <ul>
        <li>SELECT не содержит ключевого слова DISTINCT</li>
        <li>SELECT не содержит агрегирующих функций</li>
        <li>SELECT не содержит функций установки значений</li>
        <li>SELECT не содержит операций установки значений</li>
        <li>SELECT не содержит предложения ORDER BY</li>
        <li>FROM не содержит больше одной таблицы</li>
        <li>WHERE не содержит подзапросы</li>
        <li>запрос не содержит GROUP BY или HAVING</li>
        <li>вычисляемые колонки не обновляются</li>
        <li>все ненулевые колонки из базовой таблицы включены в представление в том же порядке, в каком они указаны в запросе INSERT</li>
    </ul>
Пример обновления возраста пользователя с именем Igor в представлении:
<p>
UPDATE usersView
SET age = 31
WHERE userName = 'Igor';
</p>
Обратите внимание: обновление строки в представлении приводит к ее обновлению в базовой таблице.
В представление могут добавляться новые строки с помощью команды INSERT. При выполнении этой команды должны соблюдаться те же правила, что и при выполнении команды UPDATE.
С помощью команды DELETE можно удалять строки из представления.
Удаляем из представления пользователя, возраст которого составляет 26 лет:
<p>
DELETE FROM usersView
WHERE age = 26;
</p>
Обратите внимание: удаление строки в представлении приводит к ее удалению в базовой таблице.
<h3>Удаление представления</h3>
Для удаления представления используется инструкция DROP VIEW:
DROP VIEW viewName;
Удаляем представление usersView:
DROP VIEW usersView;
<h2 id="section40">HAVING</h2>
Предложение HAVING используется для фильтрации результатов группировки. WHERE используется для применения условий к колонкам, а HAVING — к группам, созданным с помощью GROUP BY.
HAVING должно указываться после GROUP BY, но перед ORDER BY (при наличии).
<p>
SELECT col1, col2, ...colN
FROM table1, table2, ...tableN
[WHERE condition]
GROUP BY col1, col2, ...colN
HAVING condition
ORDER BY col1, col2, ...colN;
</p>
<h2 id="section41">Транзакции</h2>
Транзакция — это единица работы или операции, выполняемой над БД. Это последовательность операций, выполняемых в логическом порядке. Эти операции могут запускаться как пользователем, так и какой-либо программой, функционирующей в БД.
Транзакция — это применение одного или более изменения к БД. Например, при создании/обновлении/удалении записи мы выполняем транзакцию. Важно контролировать выполнение таких операций в целях обеспечения согласованности данных и обработки возможных ошибок.
На практике, запросы, как правило, не отправляются в БД по одному, они группируются и выполняются как часть транзакции.
Свойства транзакции
Транзакции имеют 4 стандартных свойства (ACID):
    <ul>
        <li><strong>атомарность (atomicity)</strong> — все операции транзакции должны быть успешно завершены. В противном случае, транзакция прерывается, а все изменения отменяются (происходит откат к предыдущему состоянию)</li>
        <li><strong>согласованность (consistency)</strong> — состояние должно изменться в полном соответствии с операциями транзакции</li>
        <li><strong>изоляция или автономность (isolation)</strong> — транзакции не зависят друг от друга и не оказывают друг на друга никакого влияния</li>
        <li><strong>долговечность (durability)</strong> — результат завершенной транзакции должен сохраняться при поломке системы</li>
    </ul>
<h3>Управление транзакцией</h3>
Для управления транзакцией используются следующие команды:
    <ul>
        <li><strong>BEGIN|START TRANSACTION</strong> — запуск транзакции</li>
        <li><strong>COMMIT</strong> — сохранение изменений</li>
        <li><strong>ROLLBACK</strong> — отмена изменений</li>
        <li><strong>SAVEPOINT</strong> — контрольная точка для отмены изменений</li>
        <li><strong>SET TRANSACTION</strong> — установка характеристик текущей транзакции</li>
    </ul>
Команды для управления транзакцией могут использоваться только совместно с такими запросами как INSERT, UPDATE и DELETE. Они не могут использоваться во время создания и удаления таблиц, поскольку эти операции автоматически отправляются в БД.
Удаляем пользователя, возраст которого составляет 26 лет, и отправляем изменения в БД:
<p>
BEGIN TRANSACTION
DELETE FROM users
WHERE age = 26;
COMMIT;
</p>
Удаляем пользователя с именем Oleg и отменяем эту операцию:
<p>
BEGIN
  DELETE FROM users
  WHERE username = 'Oleg';
ROLLBACK;
</p>
Контрольные точки создаются с помощью такого синтаксиса:
SAVEPOINT savepointName;
Возврат к контрольной точке выполняется так:
ROLLBACK TO savepointName;
Выполняем три запроса на удаление данных из users, создавая контрольные точки перед каждый удалением:
<p>
START TRANSACTION
SAVEPOINT sp1;
DELETE FROM users
WHERE age = 26;
</p>
<p>
SAVEPOINT sp2;
DELETE FROM users
WHERE userName = 'Oleg';
</p>
<p>
SAVEPOINT sp3;
DELETE FROM users
WHERE status = 'inactive';
</p>
Отменяем два последних удаления, возвращаясь к контрльной точке sp2, созданной после первого удаления:
ROLLBACK TO sp2;
Делаем выборку пользователей:
SELECT * FROM users;
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
                <td>31</td>
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
            <tr>
                <td>4</td>
                <td>Oleg</td>
                <td>28</td>
                <td>Moscow</td>
                <td>inactive</td>
            </tr>
        </tbody>
    </table>
Как видим, из таблицы был удален только пользователь с возрастом 26 лет.
Для удаление контрольной точки используется команда RELEASE SAVEPOINT. Естественно, после удаления контрольной точки, к ней нельзя будет вернуться с помощью ROLLBACK TO.
Команда SET TRANSACTION используется для инициализации транзакции, т.е. начала ее выполнения. При этом, можно определять некоторые характеристики транзакции. Например, так можно определить уровень доступа транзакции (доступна только для чтения или для записи тоже):
SET TRANSACTION [READ WRITE | READ ONLY];
<h2 id="section42">Временные таблицы</h2>
Некоторые СУБД поддерживают так называемые временные таблицы (temporary tables). Такие таблицы позволяют хранить и обрабатывать промежуточные результаты с помощью таких же запросов, как и при работе с обычными таблицами.
Временные таблицы могут быть очень полезными при необходимости хранения временных данных. Одной из главных особенностей таких таблиц является то, что они удаляются по завершении текущей сессии. При запуске скрипта временная таблица удаляется после завершения выполнения этого скрипта. При доступе к БД с помощью клиентской программы, такая таблица будет удалена после закрытия этой программы.
Временная таблица создается с помощью инструкции CREATE TEMPORARY TABLE, в остальном синтаксис создания таких таблиц идентичен синтаксису создания обычных таблиц.
Временная таблица удаляется точно также, как и обычная таблица, с помощью инструкции DROP TABLE.
<h2 id="section43">Клонирование таблицы</h2>
Может возникнуть ситуация, когда потребуется получить точную копию существующей таблицы, а CREATE TABLE или SELECT окажется недостаточно в силу того, что мы хотим получить не только идентичную структуру, но также индексы, значения по умолчанию и т.д. копируемой таблицы.
В mysql, например, это можно сделать так:
    <ul>
        <li>вызываем команду SHOW CREATE TABLE для получения инструкции, выполненной при создании таблицы, включая индексы и прочее</li>
        <li>меняем название таблицы и выполняем запрос. Получаем точную копию таблицы</li>
        <li>опционально: если требуется содержимое копируемой таблицы, можно также использовать инструкции INSERT INTO или SELECT</li>
    </ul>
<h2 id="section44">Подзапросы</h2>
Подзапрос — это внутренний (вложенный) запрос другого запроса, встроенный (вставленный) с помощью WHERE или других инструкций.
Подзапрос используется для получения данных, которые будут использованы основным запросом в качестве условия для фильтрации возвращаемых записей.
Подзапросы могут использоваться в инструкциях SELECT, INSERT, UPDATE и DELETE, а также с операторами =, <, >, >=, <=, IN, BETWEEN и т.д.
Правила использования подзапросов:
    <ul>
        <li>они должны быть обернуты в круглые скобки</li>
        <li>подзапрос должен содержать только одну колонку для выборки, если основной запрос не содержит несколько таких колонок, которые сравниваются в подзапросе</li>
        <li>в подзапросе нельзя использовать команду ORDER BY, это можно сделать в основном запросе. В подзапросе для замены ORDER BY можно использовать GROUP BY</li>
        <li>подзапросы, возвращающие несколько значений, могут использоваться только с операторами, которые работают с наборами значений, такими как IN</li>
        <li>список SELECT не может содержать ссылки на значения, которые оцениваются (вычисляются) как BLOB, ARRAY, CLOB или NCLOB</li>
        <li>подзапрос не может быть сразу передан в функцию для установки значений</li>
        <li>команду BETWEEN нельзя использовать совместно с подзапросом. Тем не менее, в самом подзапросе указанную команду использовать можно</li>
    </ul>
Подзапросы, обычно, используются в инструкции SELECT.
<p>
SELECT col1, col2, ...colN
FROM table1, table2, ...tableN
WHERE colName operator
  (SELECT col1, col2, ...colN
  FROM table1, table2, tableN
  [WHERE condition]);
</p>
Пример:
<p>
SELECT * FROM users
WHERE userId IN (
  SELECT userId FROM users
  WHERE status = 'active'
);
</p>
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
                <td>30</td>
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

Подзапросы могут использоваться в инструкции INSERT. Эта инструкция добавляет в таблицу данные, возвращаемые подзапросом. При этом, данные, возвращаемые подзапросом, могут быть модифицированы любыми способами.
<p>
INSERT INTO tableName col1, col2, ...colN
SELECT col1, col2, ...colN
FROM table1, table2, ...tableN
[WHERE operator [value]];
</p>
Подзапросы могут использоваться в инструкции UPDATE. При этом, данные из подзапроса могут использоваться для обновления любого количества колонок.
<p>
UPDATE tableName
SET col = newVal
[WHERE operator [value]
  (
    SELECT colName
    FROM tableName
    [WHERE condition]
  )
];
</p>
Данные, возвращаемые подзапросом, могут использоваться и для удаления записей.
<p>
DELETE FROM tableName
[WHERE operator [value]
  (
    SELECT colName
    FROM tableName
    [WHERE condition]
  )
];
</p>
<h2 id="section44">Последовательности</h2>
Последовательность — это набор целых чисел (1, 2, 3 и т.д.), генерируемых автоматически. Последовательности часто используются в БД, поскольку многие приложения нуждаются в уникальных значениях, используемых для идентификации строк.
Приведенные ниже примеры рассчитаны на mysql.
Простейшим способом определения последовательности является использование AUTO_INCREMENT при создании таблицы:
<p>
CREATE TABLE tableName (
  id INT UNSIGNED NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (id),
  -- другие строки
);
</p>
Для того, чтобы заново пронумеровать строки с помощью автоматически генерируемых значений (например, при удалении большого количества строк), можно удалить колонку, содержащую такие значения и создать ее заново. Обратите внимание: такая таблица не должна быть частью объединения.
<p>
ALTER TABLE tableName DROP id;
ALTER TABLE tableName
ADD id INT UNSIGNED NOT NULL AUTO_INCREMENT FIRST,
ADD PRIMARY KEY (id);
</p>
По умолчанию значения, генерируемые с помощью AUTO_INCREMENT, начинаются с 1. Для того, чтобы установить другое начальное значение достаточно указать, например, AUTO_INCREMENT = 100 — в этом случае нумерация строк начнется со 100.
