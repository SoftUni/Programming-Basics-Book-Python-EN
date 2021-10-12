# Chapter 3.1. Simple conditions

In the present chapter, we will take a look at the **conditional constructs in the Python programming language**. By implementing these constructs, our program can produce a different output based on a given specific input. We will explain the syntax of the conditional operators (**`if`**, **`if-elif`** and **`else`**) by implementing appropriate examples and also we will take a look at the range in which a variable lives (its **scope**). Finally, we will go over different **debugging** techniques, to follow the programming steps through which our program goes during its run.

## Video

<div class="video-player">
  Watch video-tutorial about this chapter here: 
  https://www.youtube.com/watch?v=cQIl0wQLVRE.
</div>


## Number comparison

In programming, we can compare values through the use of the following **operators**:

* Operator **`<`** (less than)
* Operator **`>`** (greater than)
* Operator **`<=`** (less than or equals)
* Operator **`>=`** (greater than or equals)
* Operator **`==`** (equals)
* Operator **`!=`** (not equal; different than)

The result from a comparison is the so-called Boolean value – **`True`** or **`False`**, depending on the evaluated result being either true or false.

### Examples of number comparisons

![](/assets/chapter-3-1-images/00.Comparing-numbers-01.png)

Note that when printing **`true`** and **`false`** values in **Python**, they are capialized, **`True`** and **`False`**, respectively.

### Comparison operators

In Python we can use the following operators to compare data:

<table>
<tr>
<th>Operator</th> <th>Notation</th> <th>Applicable for</th>
</tr>
<tr>
<td>Equals</td><td align="center"> == </td><td rowspan="2"> numbers, strings, dates</td>
</tr>
<tr>
<td>Not equal</td><td align="center"> != </td>
</tr>
<tr>
<td>Greater than</td><td align="center"> > </td><td rowspan="4">numbers, dates, other comparable data types</td>
</tr>
<tr>
<td>Greater than or equal</td><td align="center"> >= </td>
</tr>
<tr>
<td>Less than</td><td align="center"> &lt; </td>
</tr>
<tr>
<td>Less than or equal</td><td align="center"> &lt;= </td>
</tr>
</table>

Here is an example:

![](assets/chapter-3-1-images/00.Comparing-numbers-02.png)

## Simple if comparisons

In programming, we often **check particular conditions** and perform various actions depending on the result of the comparison. This is done through **`if`** clauses, which have the following structure:

```python
if condition:
    # body of the conditional construct
```

### Example: Excellent Grade

We take the grade as an input in the console and check if it is excellent (**`≥ 5.50`**).

![](assets/chapter-3-1-images/01.ExcellentResult.png)

Test the example code locally. Try entering different grades, for example, **4.75**, **5.49**, **5.50** and **6.00**. For grades **less than 5.50** the program will not give any output, however for grades of **5.50 or greater**, the output will be "**Excellent!**".

#### Testing in the Judge System

You can test the solution example here:
[https://judge.softuni.org/Contests/Practice/Index/1049#0](https://judge.softuni.org/Contests/Practice/Index/1049#0).


## If-else conditional constructs

The **`if`** conditional can also have an **`else`** option to provide a specific action to be performed in case the Boolean expression (which is specified at the beginning **`if Boolean expression`**) returns a negative result (**`False`**). Written in this way, the **conditional statement** is called **`if-else`** and its behavior is as follows: if the result of the condition is **positive** (**`True`**) - a set of instructions is executed. By contrast, when the result is **negative** (**`False`**) - a different set is executed. The format of this structure is as follows:

```python
if condition:
    # Condition body to be executed if a condition is true
else:
    # else structure body to be executed if a condition is false
```

### Example: Excellent grade or not

Similarly to the example above, we input a grade and check if it is excellent, but this time we should **output a result in both cases**:

![](assets/chapter-3-1-images/02.Excellent-or-not.png)

#### Testing in Judge System

You can test your solution at the following link: [https://judge.softuni.org/Contests/Practice/Index/1049#1](https://judge.softuni.org/Contests/Practice/Index/1049#1).


## About blocks of code

By pressing **tab key** we create a block of code through which a group of commands can be executed. When we have code in **if, elif, else** (and other structures) and we want to perform a series of operations, we put them in a block after the condition.

<table><tr><td><img src="/assets/alert-icon.png" style="max-width:50px" /></td>
<td>It is a good practice <strong>to use tab (or four spaces)</strong>, since this makes the code more readable, neater and cleaner. In this way we avoid errors during code execution.</td>
</tr></table>

Here is an example of bad indentation:

![](/assets/chapter-3-1-images/00.Brackets-tip-01.png)

The above code will either give an error because it is incorrectly formatted, or its execution will display the wrong result on the console:

![](/assets/chapter-3-1-images/00.Brackets-tip-02.png)

With correct indentation:

![](/assets/chapter-3-1-images/00.Brackets-tip-03.png)

The following output will be printed on the console:

![](/assets/chapter-3-1-images/00.Brackets-tip-04.png)

### Problem: Even or Odd

Write a program that checks whether a given integer number is **even** or **odd**.

The problem can be solved with a single **`if-else`** structure and the operator **`%`**, which returns the **division remainder** of two numbers:

![](/assets/chapter-3-1-images/03.Even-or-odd-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1049#2](https://judge.softuni.org/Contests/Practice/Index/1049#2).


### Пример: по-голямото число

Write a program that reads two integers and outputs the larger.

Our first task is to  **read** the two numbers. After which through the use of a simple  **`if-else`** structure, in combination with the **greater than operator** (**`>`**), to perform the comparison. We have deliberately blurred parts of the code so that the reader can implement the learned so far.

![](/assets/chapter-3-1-images/04.Greater-number-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1049#3](https://judge.softuni.org/Contests/Practice/Index/1049#3).


## The Lifetime of a variable

Every variable has a scope in which it exists, called **variable scope**. This scope specifies where the variable can be used and accessed. In Python, **variables could be used anywhere if they are initialized at least once.**

In the example below, on the last line we try to print the variable **`my_name`**, which is defined in the **`else` structure**. We will get an **error**, because in this case the body of the  **`else`** clause, in which we initialize the variable, is not executed. However, there is no problem to print the variable **`can_drive`** because the program entered the body of the **`if`** clause and initialized the variable. As you can see the variables **`can_drive`** and **`my_name`** are colored yellow.  This is a warning from  **PyCharm**, that we may get an error. Therefore, we should be careful where we initialize the variables.

![](/assets/chapter-3-1-images/00.Variable-scope-01.png)

## Conditional chaining

Sometimes we have to do a series of checks, before deciding what actions our program will execute. In such cases we can apply the structure **`if-elif ... else` in series**. For this purpose, we employ the following structure:

```python
if condition:
    # condition body;
elif condition2:
    # condition body;
elif condition3:
    # condition body;
…
else:
    # else structure body
```

### Example: Numbers 1 through 9 in English

Print the digits one through nine in English on the console (the numbers are read from the console). We can take the digit and through a  **series of conditions** print the corresponding English word on the console:

```python
number = int(input())

if number == 1:
    print("one")
elif num == 2:
    print("two")
elif …:
    …
elif num == 9:
    print("nine")
else: 
    print("number too big")
```

The program logic of the above example **sequentially compares** the input number with the digits from 1 to 9 **with each consecutive comparison being performed only in case the previous result is not true**. Eventually, if none of the **`if`** conditionals are satisfied, the last **`else` clause** is executed.

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1049#4](https://judge.softuni.org/Contests/Practice/Index/1049#4).


## Excercies: Simple conditions

To practice the implementation of the conditional constructs **`if`** and **`if-elif`** we will take a look at a few practical problems.

### Problem: Bonus Score 

We are given an **integer** – several points. Additional **bonus points** are awarded as per the rules described below. Write a program that calculates the **bonus points** for the given number and outputs the **total points** including the bonus.

- If the number is **up to 100** inclusive, the bonus points are 5.
- If the number is **larger than 100**, the bonus points are **20%** of the number.
- If the number is  **larger than 1000**, the bonus points are **10%** of the number.
- Additional points are awarded as below (added separately from the described above):
 - For **even** numbers -> + 1 p.
 - For numbers, **ending with 5** -> + 2 p.
 
#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 20 | 6<br>26 |
| 175 | 37<br>212 |
| 2703 | 270.3<br>2973.3 |
| 15875 | 1589.5<br>17464.5 |

#### Hints and pointers

Основните и допълнителните бонус точки можем да изчислим с поредица от няколко **`if-elif-else`** проверки. Като за **основните бонус точки имаме 3 случая** (когато въведеното число е до 100, между 100 и 1000 и по-голямо от 1000), а за **допълнителните бонус точки - още 2 случая** (когато числото е четно и нечетно):

![](/assets/chapter-3-1-images/06.Bonus-score-01.png)

Ето как би могло да изглежда решението на задачата в действие:

![](/assets/chapter-3-1-images/06.Bonus-score-02.png)

Обърнете внимание, че за тази задача Judge е настроен да игнорира всичко, което не е число, така че можем да печатаме не само числата, но и уточняващ текст.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#5](https://judge.softuni.org/Contests/Practice/Index/1049#5).


### Задача: сумиране на секунди

Трима спортни състезатели финишират за някакъв **брой секунди** (между **1** и **50**). Да се напише програма, която въвежда времената на състезателите и пресмята **сумарното им време** във формат "минути:секунди". Секундите да се изведат с **водеща нула** (2 -> "02", 7 -> "07", 35 -> "35").

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 35<br>45<br>44 | 2:04 |
| 22<br>7<br>34 | 1:03 |
| 50<br>50<br>49 | 2:29 |
| 14<br>12<br>10 | 0:36 |

#### Насоки и подсказки

Първо сумираме трите числа, за да получим общия резултат в секунди. Понеже **1 минута = 60** секунди, ще трябва да изчислим броя минути и броя секунди в диапазона от 0 до 59:
- Ако резултатът е между 0 и 59, отпечатваме 0 минути + изчислените секунди.
- Ако резултатът е между 60 и 119, отпечатваме 1 минута + изчислените секунди минус 60.
- Ако резултатът е между 120 и 179, отпечатваме 2 минути + изчислените секунди минус 120.
- Ако секундите са по-малко от 10, извеждаме водеща нула преди тях.

![](/assets/chapter-3-1-images/07.Sum-seconds-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#6](https://judge.softuni.org/Contests/Practice/Index/1049#6).


### Задача: конвертор за мерни единици

Да се напише програма, която **преобразува разстояние** между следните **8 мерни единици**: **`m`, `mm`, `cm`, `mi`, `in`, `km`, `ft`, `yd`**. Използвайте съответствията от таблицата по-долу:

| Входна единица | Изходна единица |
| :-------------: | :--------------: |
| 1 meter (m) | 1000 millimeters (mm) |
| 1 meter (m) | 100 centimeters (cm) |
| 1 meter (m) | 0.000621371192 miles (mi) |
| 1 meter (m) | 39.3700787 inches (in) |
| 1 meter (m) | 0.001 kilometers (km) |
| 1 meter (m) | 3.2808399 feet (ft)  |
| 1 meter (m) | 1.0936133 yards (yd) |

Входните данни се състоят от три реда:

- Първи ред: число за преобразуване.
- Втори ред: входна мерна единица.
- Трети ред: изходна мерна единица (за резултата).

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 12 <br>km <br>ft | 39370.0788 |
| 150 <br>mi <br>in | 9503999.99393599 |
| 450 <br>yd <br>km | 0.41147999937455 |

#### Насоки и подсказки

Прочитаме си входните данни, като към прочитането на мерните единици можем да добавим функцията **`lower()`**, която ще направи всички букви малки. Както виждаме от таблицата в условието, можем да конвертираме само **между метри и някаква друга мерна единица**. Следователно трябва първо да изчислим числото за преобразуване в метри. Затова трябва да направим набор от проверки, за да определим каква е входната мерна единица, а след това и за изходната мерна единица:

![](/assets/chapter-3-1-images/08.Metric-converter-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#7](https://judge.softuni.org/Contests/Practice/Index/1049#7).


## Дебъгване - прости операции с дебъгер

До момента писахме доста код и често пъти в него имаше грешки, нали? Сега ще покажем един инструмент, с който можем да намираме грешките по-лесно.

### Какво е "дебъгване"?

**Дебъгване** е процесът на "**закачане**" към изпълнението на програмата, който ни позволява да проследим поетапно процеса на изпълнение. Можем да следим **ред по ред** какво се случва с нашата програма, какъв път следва, какви стойности имат дефинираните променливи на всяка стъпка от изпълнението на програмата и много други неща, които ни позволяват да откриваме грешки (**бъгове**):

![](/assets/chapter-3-1-images/00.Debugging-01.png)
![](/assets/chapter-3-1-images/00.Debugging-02.png)

### Дебъгване в PyCharm

Чрез натискане на [**Shift + F9**], стартираме програмата в **Debug режим**. Преминаваме към **следващия ред** на изпълнение с [**F7**]:

![](/assets/chapter-3-1-images/00.Debugging-03.png)

Чрез [**Ctrl + F8**] създаваме стопери - така наречените **breakpoints**, до които можем да стигнем директно използвайки [**Shift + F9**]  (при стартирането на програмата в **Debug режим**).

## Упражнения: прости проверки

Нека затвърдим наученото в тази глава с няколко задачи.

### Празно PyCharm решение (Project)

Създаваме празно решение в **PyCharm**, за да организираме по-добре решенията на задачите от упражненията – всяка задача ще бъде в отделен файл и всички задачи ще бъдат в общ Project.

Стартираме PyCharm. Създаваме нов **Project:** [**File**] -> [**New Project**].

![](/assets/chapter-3-1-images/00.PyCharm-01.png)

Избираме от полето в ляво **Pure Python** и задаваме директория на проекта, като на мястото на **untitled** слагаме името на нашия проект:  

![](/assets/chapter-3-1-images/00.PyCharm-02.png)

Сега имаме създаден празен проект (без файлове в него).

### Задача: проверка за отлична оценка

Първата задача от упражненията за тази тема е да се напише **конзолна програма**, която **въвежда оценка** (десетично число) и отпечатва "**Excellent!**", ако оценката е **5.50** или по-висока.

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 6 | Excellent! |
| 5 | (няма изход) |
| 5.5 | Excellent! |
| 5.49 | (няма изход) |

#### Насоки и подсказки

Създаваме нов **python** файл (**.py**) като цъкаме с десен клавиш на мишката върху създадената от нас папка и изберем [**New**] -> [**Python File**]:

 ![](/assets/chapter-3-1-images/00.PyCharm-03.png)

Ще се отвори диалогов прозорец за избор на име на файла. Тъй като задачата ни е за проверка на отлична оценка, нека именуваме файла **excellent_result**:

 ![](/assets/chapter-3-1-images/00.PyCharm-04.png)
 
Вече имаме Project с еднин файл в него. Остава да напишем кода за решаване на задачата. За целта пишем следния код:

 ![](/assets/chapter-3-1-images/01.ExcellentResult-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#0](https://judge.softuni.org/Contests/Practice/Index/1049#0).

 ![](/assets/chapter-3-1-images/01.ExcellentResult-02.png) 

 ![](/assets/chapter-3-1-images/01.ExcellentResult-03.png)


### Задача: отлична оценка или не

Следващата задача от тази тема е да се напише **конзолна програма**, която **въвежда оценка** (десетично число) и отпечатва "**Excellent!**", ако оценката е **5.50** или по-висока, или "**Not excellent.**" в противен случай.

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 6 | Excellent! |
| 5 | Not excellent. |
| 5.5 | Excellent! |
| 5.49 | Not excellent. |

#### Насоки и подсказки

Първо създаваме **нов Python файл** в нашия проект. Следва да **напишем кода** на програмата. Може да си помогнем със следния примерен код:

 ![](/assets/chapter-3-1-images/02.Excellent-or-not-01.png)

Следва да **стартираме програмата**, както обикновено с [**Shift + F10**] и да я тестваме дали работи коректно:

 ![](/assets/chapter-3-1-images/02.Excellent-or-not-02.png)
 ![](/assets/chapter-3-1-images/02.Excellent-or-not-03.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#1](https://judge.softuni.org/Contests/Practice/Index/1049#1).

![](/assets/chapter-3-1-images/02.Excellent-or-not-04.png)


### Задача: четно или нечетно

Да се напише програма, която въвежда **цяло число** и печата дали е **четно** или **нечетно**.

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 2 | even |
| 3 | odd |
| 25 | odd |
| 1024 | even |

#### Насоки и подсказки

Отново, първо добавяме **нов Python файл**. Проверката дали дадено число е четно, може да се реализира с оператора **`%`**, който ще ни върне **остатъка при целочислено деление на 2**, по следния начин: **`is_even = number % 2 == 0`**.

Остава да **стартираме** програмата с [**Ctrl+F5**] и да я тестваме:  

![](/assets/chapter-3-1-images/03.Even-or-odd-02.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#2](https://judge.softuni.org/Contests/Practice/Index/1049#2).


### Задача: намиране на по-голямото число

Да се напише програма, която въвежда **две цели числа** и отпечатва по-голямото от двете.

#### Примерен вход и изход

| Вход | Изход |
|-----|------|
|5<br>3| 5 |
|3<br>5| 5 |
|10<br>10| 10 |
|-5<br>5| 5 |

#### Насоки и подсказки

Както обикновено, първо трябва да добавим **нов Python файл**. За кода на програмата ни е необходима единична **`if-else`** конструкция. Може да си помогнете частично с кода от картинката, който е умишлено замъглен, за да помисли читателя как да го допише сам:  

![](/assets/chapter-3-1-images/04.Greater-number-01.png)

След като сме готови с имплементацията на решението, **стартираме** програмата с [**Shift + F10**] и я тестваме:

![](/assets/chapter-3-1-images/04.Greater-number-02.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#3](https://judge.softuni.org/Contests/Practice/Index/1049#3).


### Задача: изписване на число до 9 с думи

Да се напише програма, която въвежда **цяло число в диапазона** [**0 … 9**] и го **изписва с думи** на английски език. Ако числото е извън диапазона, изписва "**number too big**".

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 5 | five |
| 1 | one |
| 9 | nine |
| 10 | number too big |

#### Насоки и подсказки

Може да използваме поредица **`if-elif`** конструкции, с които да разгледаме възможните **11 случая**.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#4](https://judge.softuni.org/Contests/Practice/Index/1049#4).


### Задача: познай паролата

Да се напише програма, която **въвежда парола** (произволен текст) и проверява дали въведеното **съвпада** с фразата "**s3cr3t!P@ssw0rd**". При съответствие да се изведе "**Welcome**", а при несъответствие да се изведе "**Wrong password!**". 

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| qwerty | Wrong password! |
| s3cr3t!P@ssw0rd | Welcome |
| s3cr3t!p@ss | Wrong password! |

#### Насоки и подсказки

Може да използваме **`if-else`** конструкцията.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#8](https://judge.softuni.org/Contests/Practice/Index/1049#8).


### Задача: число от 100 до 200

Да се напише програма, която **въвежда цяло число** и проверява дали е **под 100**, **между 100 и 200** или **над 200**. Да се отпечатат съответно съобщения, като в примерите по-долу.

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 95 | Less than 100 |
| 120 | Between 100 and 200 |
| 210 | Greater than 200 |

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#9](https://judge.softuni.org/Contests/Practice/Index/1049#9).


### Задача: еднакви думи

Да се напише програма, която **въвежда две думи** и проверява дали са еднакви. Да не се прави разлика между главни и малки букви. Да се изведе "**yes**" или "**no**". 

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| Hello<br>Hello | yes |
| SoftUni<br>softuni | yes |
| Soft<br>Uni | no |
| beer<br>vodka | no |
| HeLlO<br>hELLo | yes |

#### Насоки и подсказки

Преди сравняване на думите, трябва да ги обърнем в долен регистър, за да не оказва влияние размера на буквите (главни/малки): **`word = word.lower()`**.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#10](https://judge.softuni.org/Contests/Practice/Index/1049#10).


### Задача: информация за скоростта

Да се напише програма, която **въвежда скорост** (дробно число) и отпечатва **информация за скоростта**. При скорост **до 10** (включително), отпечатайте "**slow**". При скорост **над 10** и **до 50**, отпечатайте "**average**". При скорост **над 50 и до 150**, отпечатайте "**fast**". При скорост **над 150 и до 1000**, отпечатайте "**ultra fast**". При по-висока скорост, отпечатайте "**extremely fast**".

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 8 | slow |
| 49.5 | average |
| 126 | fast |
| 160 | ultra fast |
| 3500 | extremely fast |

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#11](https://judge.softuni.org/Contests/Practice/Index/1049#11).


### Задача: лица на фигури

Да се напише програма, която **въвежда размерите на геометрична фигура** и **пресмята лицето й**. Фигурите са четири вида: квадрат (**square**), правоъгълник (**rectangle**), кръг (**circle**) и триъгълник (**triangle**).

На първия ред на входа се чете вида на фигурата (**`square`**, **`rectangle`**, **`circle`**, **`triangle`**):
* Ако фигурата е **квадрат**, на следващия ред се чете едно число – дължина на страната му.
* Ако фигурата е **правоъгълник**, на следващите два реда се четат две числа – дължините на страните му.
* Ако фигурата е **кръг**, на следващия ред се чете едно число – радиусa на кръга.
* Ако фигурата е **триъгълник**, на следващите два реда се четат две числа – дължината на страната му и дължината на височината към нея.

Резултатът да се закръгли до **3 цифри след десетичния знак**. 

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| square<br>5 | 25 |
| rectangle<br>7<br>2.5 | 17.5 |
| circle<br>6 | 113.097 |
| triangle<br>4.5<br>20 | 45 |

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#12](https://judge.softuni.org/Contests/Practice/Index/1049#12).


### Задача: време + 15 минути

Да се напише програма, която **въвежда час и минути** от 24-часово денонощие и изчислява колко ще е **часът след 15 минути**. Резултатът да се отпечата във формат **`hh:mm`**. Часовете винаги са между 0 и 23, а минутите винаги са между 0 и 59. Часовете се изписват с една или две цифри. Минутите се изписват винаги с по две цифри и с **водеща нула**, когато е необходимо.

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 1<br>46 | 2:01 |
| 0<br>01 | 0:16 |
| 23<br>59 | 0:14 |
| 11<br>08 | 11:23 |
| 12<br>49 | 13:04 |

#### Насоки и подсказки

Добавете 15 минути и направете няколко проверки. Ако минутите надвишат 59, **увеличете часовете** с 1 и **намалете минутите** с 60. По аналогичен начин разгледайте случая, когато часовете надвишат 23. При печатането на минутите, **проверете за водеща нула**.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#13](https://judge.softuni.org/Contests/Practice/Index/1049#13).


### Задача: еднакви 3 числа

Да се напише програма, в която се въвеждат **3 числа** и се отпечатва дали те са еднакви ("**yes**" / "**no**").

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 5<br>5<br>5 | yes |
| 5<br>4<br>5 | no |
| 1<br>2<br>3 | no |

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#14](https://judge.softuni.org/Contests/Practice/Index/1049#14).


### Задача: \* изписване на число от 0 до 100 с думи

Да се напише програма, която превръща число в диапазона [**0 … 100**] в текст. 

#### Примерен вход и изход

| Вход | Изход |
| --- | ---- |
| 25 | twenty five |
| 42 | forty two |
| 6  | six |

#### Насоки и подсказки

Проверяваме първо за **едноцифрени числа** и ако числото е едноцифрено, отпечатваме съответната дума за него. След това проверяваме за **двуцифрени числа**. Тях отпечатваме на две части: лява част (**десетици** = числото / 10) и дясна част (**единици** = числото % 10). Ако числото има 3 цифри, трябва да е 100 и може да се разгледа като специален случай.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1049#15](https://judge.softuni.org/Contests/Practice/Index/1049#15).
