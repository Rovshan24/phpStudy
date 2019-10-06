# phpStudy
   Знак операции, такой как + это **оператор**, а числа это **операнды**. Операции, которые требуют наличия двух операндов, называются **бинарными**. Операции бывают не только бинарными, но и *унарными* (с одним операндом) и даже *тернарными* (с тремя операндами)!  
**Коммутативный закон** - от перемены мест слагаемых сумма не меняется.

## Линтер  
[**PSR-1:** Базовый стандарт написания кода](https://www.php-fig.org/psr/psr-1/) - Это набор правил, определяющих как следует оформлять программный код.  
[**PSR-2:** Руководство по оформлению кода](https://www.php-fig.org/psr/psr-2/) - Во-первых, этот стандарт требует выполнения правил PSR-1. Во-вторых, он добавляет множество новых требований.  
Повсеместно используемым линтером в PHP является [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer).


## Типы данных
1. Примитивные типы - простые типы, они встроены в сам язык PHP.
   1. Строка - описывает набор символов (иными словами текст).
   2. Целые числа
   3. Рациональные числа
*Тип данных опеределяет, что можно делать с элеменатми конкретного множества элементов.*


PHP - это язык со слабой типизацией. Во многиз ситуациях лучше делать преобразование явно, используя специальный синтаксис.

## Переменные
**Переменная** - способ сохранить информацию и дать ей имя для последуюзщего использования в коде.
Для имени переменной испоьзуется любой набор допустимых символов, к которому относятся буквы английского алфавита, цифры, знак _. При этом цифру нельзя ставить вначале. Имена переменных регистрозависимы. Количество создаваемых переменных никак не ограничено. Переменные принято создавать как можно ближе к тому месту где они используются.

### Именование переменных
1. kebab-case
2. snake_case
3. CamelCase  
В PHP используется *CamelCase* и его вариация *lowerCamelCase*, при котором первая буква первого слова — строчная. Именно **lowerCamelCase применяется для переменных**.  
#### Ошибки при работе с переменными
Переменная должна быть объявлена до ее использования.  
Все что справа от знака равно выражение. Любая строка выражение. Конкатенация строк - тоже выражение. Когда интерпретатор видит выражение, он обрабатывает его и генерирует результат - **значение выражения**. Правила построения кода таковы, что в тех метсах где, ожидается выражение, можно поставить любое вычисление (как математическое, так и строковое).
> Любая переменная может быть частью любого вывражения. В момент вычисления имени переменнной подставляется её значение.

#### Константы
1. Ключевое слово *const* (знак доллара не нужен).
2. Принято именовать буквами в верхнем регистре с _в качестве разделителя.

**[Предопределеные константы](https://www.php.net/manual/ru/reserved.constants.php)**. В PHP очень много **встроенных** констант. Некоторые из них:
- **PHP_VERSION** - текущая версия PHP
- **PHP_MAXPATHLEN** - максимальная разрешенная длина имени файла
- **PHP_INT_MAX** - максимальное возможное значение чисел (integer)

**Магические константы** - они не очень постоянные, но их изменения четко реглпментированы.
- Невозможно определить самомму, можно пользоваться только существующими
- Начинаются и заканчиваются символами "__"(два подчеркивания)
- Имеют одно и то же значение в пределах определенной части программы  
Например:
* __LINE__ - содержит текущую строку файла, в котором она используется
* __FILE__ - путь до текущего файла
* __DIR__ - путь до дериктории, в которой находится текущий файл

**Интерполяция** - способ соединения строк через вставку значений переменных в строку-шаблон с помощью фигурных скобок. Например, "Hi, {$name}!".  
В одной строке количество блоков с фигурными скобками не ограничено.

#### Извлечение символов из строки
Осущестляется с помощью *квадратных скобок с цифрой* - это специальный оператор извлечения строки. Эта цифра называется **индексом** - позицией символа внутри строки. Индексы начинаются с **0**.  *Отрицательные индексы* - обращение с символам начиная с конца строки. В отличие от прямой индексации, обратный отсчет идет от **-1**.  
Индексом м.б. также значения переменной. ($index = 0).  


**Herecod** - это использование herecod-синтаксиса: <<<. После этого оператора необходимо указать идентификатор, а затем перевод строки. Такой способ удобен для задания длинных строк, внутри которых встречаются и переводы строк, и разнотипные кавычки. Не нужно экранировать одинарные ' и двойные " кавычки.


## Функции
### Функции и их вызов
Функция - операция, способная принимать данные и возвращать результат.
Аргумент - информация, которую функция получает при вызове.
Вызов функции всегда обозначается скобками (), идущими сразу за именем фунции. В скобках может быть любое количество аргументов (часто говорят параметр), а иногда - вообще ни одного.  
> Любая функция возвращает всегда только одно значение. Это ограничение существует на уровне языка и не может быть нарушено.
**Сигнатура функции** — формальное описание типов аргументов и типа возвращаемого значения функции.


**Стандартная библиотека** - набор полезных функций.
*Советы о том, как узнавать о новых функциях*:
1. Всегда чётко отслеживайте, с чем вы сейчас работаете (какой тип данных). Например, для работы со строками нужно изучать строковые функции.
2. Периодически открывать раздел со стандартными функциями по изучаемой тематике и пробегаться по ним, изучая сигнатуры и способы использования.  
3. Чаще читайте чужой код, особенно код библиотек, которые вы используете.  
> Особенность функций PHP из стандартной библиотеки в том, что они доступны *глобально*.
**Аргумент по умолчанию** - необязательный аргумент функции.
**Выражение** - это код, который при выполнении программы превращается в значение.  
> **!Вызов функции тоже выражение**. А значит мы можем положить вызов функции в вызов функции.  
> Все что работает, как выражение, может быть использовано в других выражениях, а также во всех местах, где на вход ожидаются выражения.  
Если вычисление совсем простое и неглубокое (не больше одного вложения функции), то смело можно вкладывать вызов в вызов. В остальных ситуациях предпочтительно разбивать вызовы на промежуточные вычисления.
- Во первых, промежуточные переменные своими названиями отражают суть операций.
- Во вторых, такой код легче отлаживать, а промежуточные данные проще исследовать.
- В третьих, глубокие вложенные вызовы сложно читать.  
PHP является языком с **жадными вычислениями**. PHP пытается сначала вычислить максимально глубокий уровень вызова, затем менее глубокий и так далее.  
**Побочный эффект** - действие, которое изменяет внешнее окружение (среду выполнения). Например, вывод на экран или отправка письма.


### Создание (определение) функции
Код в котором создается функция, называетя **опеределением функции**.
**Аргумент должен быть переменной**, иначе он не сможет быть аргументом, то есть чем-то, что принимает значение при вызове.  
> Если нужна какая-то информация в функции, и заранее известно, какая именно, то аргумент для этого не нужен - достаточно создать переменную в самом теле.  
Символ `;` ставится в конце выражений. **Определение функции - не выражение, а инструкция** (указание интерпретатору). Соответственно, мы не можем его использовать в составе других выражений и ему не нужна `;` в конце.


**rand** - функция которая генерирует и возвращает случайное число.
** - оператор возведения в степень.




**Определения**
1. *Инструкция (statement)* - Код на PHP — это набор инструкций, разделенных (чаще всего) символом ;.
2. *Parse error (ошибка парсинга)* - тип ошибок в PHP, возникающих при наличии синтаксических ошибок в коде.
3. *Оператор* - специальный символ, создающий операцию.  
    Операции бывают не только *бинарными*, но и *унарными* (с одним операндом) и даже *тернарными* (с тремя операндами)!
4. *Операнд* - объект, который участвует в операции.
5. *Коммутативность* — свойство операции, когда изменения порядка операндов не влияет на результат.
6. *Экранирующая последовательность* - специальная комбинация символов в тексте (\n).
7. *Конкатенация* - склеивание строк.
8. *Стандарт кодирования* - набор синтаксических и стилистических правил написания кода.

**Ошибки**
1. *Undefined variable* - это ошибка обращения, она означает, что в коде используется имя (говорят идентификатор), который не определен.
2. *PHP Warning: pow() expects exactly 2 parameters, 0 given in php shell code on line 1* - функция ожидает 2 параметра, а вы вызвали её без параметров.
3. PHP Warning: A non-numeric value encountered in php shell code on line 1 - передаваемы параметр всегда число.
