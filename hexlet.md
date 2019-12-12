# PHP:Основы
## Основные конструкции языка
### Типы данных и переменные
```php

# Числа

$one = 1;
$number = -100;

# Строки

$str1 = 'i am a string';
$str2 = 'i am a string too';

# Логические значения

$yes = true;
$no = false;

```

### Преобразование типов

```php

# Числа

$one = (int) '234';
$two = (string) 34;

```

### Операции

```php

// Арифметические операции
1 + 5 -8 * 6 / 2 ** 3 % 4;

// Логические операции
true || false && !true

// Создание переменных
$str = 'i am a string';

// Обращение к символам строки
$str[0]; // i
print_r("{$str}"); // => i am a string
print_r($str); // => i am a string

```

### Условные конструкции

```php

if ($a > $b) {
  echo 'а больше, чем b';
} elseif ($a == $b) {
  echo 'a равен b';
} else {
  echo 'a меньше, чем b';
}

$result = $a > $b ? 'yes' : 'no';

switch ($i) {
    case 0:
        echo "i равно 0";
        break;
    case 1:
        echo "i равно 1";
        break;
    case 2:
        echo "i равно 2";
        break;
    default:
       echo "i не равно 0, 1 или 2";
}

```

### Циклы

```php

$i = 1;
while ($i <= 10) {
    echo $i++;
}

for ($i = 1; $i <= 10; $i++) {
    echo $i;
}

```

### Функции

```php

// Определение
function get($string, $index = 0)
{
    return $string[$index];
}

// Вызов
get('lala', 3);

```
