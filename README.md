## Комментарии в коде

Всё, что написано в программе после символа `#` на той же строчке называется комментариями и игнорируется python при исполнении программы

## Команда Print

`print` - команда для вывода на экран.
Print всегда используется со скобками: `print()`, чтобы показать, что это команда и мы её вызываем.

### Текст

Чтобы вывести какой-нибудь текст, нужно заключить его в кавычки
```python
print("Hello World")
print('Saint Petersburg!!!')
```
Можно использовать и двойные, и одинарные кавычки. Но обязательно одинаковые в начале и в конце: `print("Error')` не сработает

Можно выводить несколько элементов через запятую, они будут разделяться пробелом:
```python
print("fri", "end") # выведет "fri end"
```

Команда `print` по умолчанию после вывода делает перевод строки.
Следующий вызов `print` будет выводить уже на новой строке.

```python
print("Hello")
print("my", "friend")  # "my friend" выводится на следующей строке после "Hello"
```

### Числа

Числа можно передавать в команду `print` и без кавычек: `print(239)`.

Тогда python понимает, что это не просто строка, а число. С числами можно выполнять математические действия. Например:
```python
print(2 + 2) # выведется 4
print(72 - 12) # выведется 60
```

#### Арифметические действия

```python
print(10 + 4)  # сложение  -> 14
print(10 - 4)  # вычитание -> 6
print(10 * 4)  # умножение -> 40  (символ *, а не . и не х)
print(10 / 4)  # деление   -> 2.5 (символ /, а не \ и не :)

print(1 + 2 + 3 * 4)    # 15 - python знает порядок арифметических операций!
print(1 + (2 + 3) * 4)  # 21 - можно использовать скобки для изменения порядка
```

`print("2 + 2")` выведет не результат сложения, а просто строку `2 + 2`.
Всё, что написано в кавычках, python никак не обрабатывает.
Он не знает, что это числа, а считает, что это просто текст.

##### Деление

```python
print(11 / 4)  # 2.75 - деление с дробями
print(11 // 4) # 2    - частное целочисленного деления
print(11 % 4)  # 3    - остаток от деления (целочисленного)
```

### Действия с текстом

Текст (строки) тоже можно складывать. При сложении двух строк они просто склеиваются друг с другом.

```python
print("Mos" + "cow") # выведет "Moscow"
```

Но если сложить текст и число, будет ошибка: `print("2" + 2)` -> `TypeError: can only concatenate str (not "int") to str`

Зато текст можно умножать на число. Числом мы указываем, сколько раз повторить строку. (Число должно быть целое.)

```python
print("help!" * 4) # выведет "help!help!help!help!"
```

## Переменные

Переменная - ячейка, выделенная в памяти компьютера и названная каким-нибудь именем. Для того, чтобы завести переменную, нужно написать имя переменной, затем `=`, и затем значение, которое записываем в переменную.

```python
x = 239
```

Чтобы достать из переменной записанное значение и использовать его, просто указываем имя переменной (без кавычек)

```python
print(x) # выведет 239
```

В названии переменной можно использовать маленькие и большие английские буквы, цифры и нижнее подчёркивание (`_`). Название не может начинаться с цифры. Не стоит использовать в качестве названий переменных названия команд python, например `print`, `if`, `import` и другие. Примеры правильных названий: `a`, `person3`, `songs_list`, `minAge`. Примеры неправильных названий: `1a`, `qq-q`, `my var`.

### Оператор присваивания

После того как в переменную записали значение, можно поменять его (поэтому она и называется "переменная" :)) Для этого нужно просто ещё раз написать `=` и новое значение.

```python
x = 7
print(x) # 7
x = 20
x = 48
print(x) # 48
```


Можно справа от знака `=` писать выражения для вычисления. В них так же можно использовать значения других переменных, или даже текущее значение той же переменной.

```python
a = 6 + 4 # в a запишется 10
b = a * 5 # в b запишется 50
b = b - 1 # в b запишется 49
```

Знак `=` называется оператором присваивания. Он работает так: сначала смотрит на правую часть, считает значение выражения, записанного там, затем записывает это в переменную в левой части. Обратите внимание, что в левой части должна быть именно просто переменная, а не какое-то выражение. `a + b = 3 * 8` - неправильно.

## Типы данных

Все значения в python, в том числе значения в переменных, имеют свой тип данных. Тип данных - описание того, в каком виде эти данные записаны. Мы уже видели, что можно выводить данные через `print` как числа и как текст. Это и есть типы данных. Более конкретно:

`int` (сокращение от `integer`) - целые числа. Например, `17`, `0`, `-148`, `154008`.  
`float` - добрые числа. Например, `2.5`, `-17.863`, `14.0`.  
`str` (сокращение от `string`) - строки (текст). Например, `Hello, world`, `I am 23`. Строки в python всегда нужно писать в кавычках. Числа, которые написаны без кавычек, python воспринимает как числа, а текст без кавычек - как название какой-то команды или переменной. Всё, что написано в кавычках python считает просто текстом и может работать с этим только как со строкой.

### Преобразование типов

Если есть данные одного типа, то их можно перевести в другой. Для этого нужно использовать команду, которая совпадает с названием типа данных, в который нужно перевести: `int()` переводит в целое число, `float()` - в доброе число, а `str()` - в строку. Это тоже команды, как и `print`, поэтому их пишем со скобками. в скобках указываем, что именно приводим к этому типу: `int("123")` - получится число `123`, как если бы мы написали его без кавычек.

```python
s = "246"       # s - это строка
n = int(s)      # n - это число 246
print(s + "4")  # складываем строку со строкой, они склеиваются, получается 2464
print(s + 4)    # ошибка! Нельзя складывать строку и число
print(n + 4)    # складываем число и число, получится 250
```

## Ввод данных

До этого момента мы писали программы, которые при каждом запуске работают одинаково и выводят одинаковый результат. Но это не очень интересно. Более полезны программы, которые в процессе работы получают данные от пользователя, обрабатывают их, и выдают разный результат в зависимости от входных данных.  
Например, можно написать программу, которая запускается и говорит: я могу сложить два числа. Введите, какие числа мне сложить. После этого пользователь вводит два числа, и затем программа выводит их сумму. Если пользователь введёт 5 и 3, программа выведет 8. Если пользователь введёт 16 и 4, та же программа выведет 20.  
*Конечно, можно было бы каждый раз менять код программы, и, если надо сложить 5 и 3, написать программу `print(5+3)`, а если надо сложить 16 и 4, написать программу `print(16+4)`. Но менять код - дело сложное, и пользователи не умеют этого делать. Код пишет программист, а пользователю нужно дать способ вводить данные снаружи, не меняя код.*

Для того, чтобы вводить данные, в python используют команду `input()`. Так как это тоже команда, как и `print()`, `int()` и `str()`, то после неё мы ставим скобки, хотя в скобках обычно не будем ничего писать. Через `input()` мы получаем данные, и затем их можно, например, записать в переменную.

```python
s = input() # ввод строки
```

`input` вводит всё, что написано на одной строке. Там могут быть цифры, буквы, разные символы, пробелы. Поэтому результат ввода всегда сохраняется в формате строки (текста). Чтобы преобразовать введённые данные к числу и складывать, вычитать, умножать с другими числами нужно использовать функцию преобразования типов. Например:

```python
s = input() # ввод строки
n = int(s)  # преобразование строки в число
```

Можно записать это в одной строке программы, сразу передавая результат `input` в `int`, не  используя промежуточную переменную.

```python
n = int(input()) # ввод числа
```

## Условный оператор

`if` - условный оператор (иногда также называемый "оператор ветвления") в python.

Синтаксис:
```python
if <условие>:
    <действия, если условие выполнено>
else:
    <действия, если условие выполнено>
```

Краткая версия:
```python
if <условие>:
    <действия, если условие выполнено>
```

В качестве условий можно использовать, например, операторы сравнения: `>`, `<`, `>=`, `<=`, `==` (проверка равенства), `!=` (не равно). Знак `=` уже используется для обозначения записи в переменную, поэтому здесь, для проверки равенства, используется двойное равно.

Действия могут быть любыми командами, операциями. Можно также внутри `if` использовать ещё один или несколько `if`.

В python важны отступы: всё что написано после оператора `if` с отступом большим, чем сам `if` находится "внутри" него и выполняется в зависимости от условия. Всё, что пойдёт с таким же, или меньшим отступом, чем `if` выполнится после него независимо от условия.

Примеры:
```python
if x > 10:
    print("Число x больше 10")
else:
    print("Число x равно 10, или меньше")
```
```python
if x % 2 == 1:   # проверяем, что остаток от деления числа x на 2 равен 1, то есть, что x - нечётное
    x = x - 3    # выполняется, только если x было нечётным
    x = x / 2    # выполняется, только если x к началу if было нечётным
print(x)         # выполняется в любом случае
```

Несколько условий можно соединять в одно с помощью логических операторов `and` (и) и `or` (или).
Например, если мы хотим проверить, что значение переменной $x$ больше $10$ и меньше $30$, можно написать
```python
if x > 10 and x < 30:
```
Также, проверим $x$ чётное или делится на $3$ (то есть остаток от деления на $3$ равен $0$):
```python
if x % 2 == 0 or x % 3 == 0:
```

Можно использовать много `and` и `or` в одном условии. По умолчанию у `and` приоритет больше, чем у `or`, однако можно поменять порядок действий с помощью скобок.
```python
if (x % 10 == 7 or x % 3 == 0) and x % 7 == 0:
```

Если мы хотим провести две проверки одну за другой, можно написать вложенные `if`, например:
```python
if x > 10:
    print("Число больше 10")
else:
    if x >= 5:
        print("Число от 5 до 10")
    else:
        print("Число меньше 5")
```

Однако иногда удобно использовать оператор `elif` -- он заменяет комбинацию else + if. Например, в данном случае можно переписать так:
```python
if x > 10:
    print("Число больше 10")
elif x >= 5:
    print("Число от 5 до 10")
else:
    print("Число меньше 5")
```

После `elif` пишется условие, также как и после `if`. Можно использовать `elif` много раз в одном блоке `if`. Условие в `elif` проверяется только если условие в `if` перед ним, а также во всех других `elif` раньше него в этом же блоке `if` оказались неверными. В конце блока `if`, после всех `elif` может быть, а может не быть `else` -- то что выполняется, если никакие условия оказались не верны.
