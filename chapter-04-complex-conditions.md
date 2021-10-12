# Chapter 4.1. More Complex Conditions

In the **current** chapter, we are going to examine **nested conditional statements** in the **Python** language, by which our program can execute **conditions**, that contain other **nested conditional statements**. We call them **"nested"**, because **we put `if` condition** into **another `if` condition**. We are going to examine the **more complex logical conditions** through proper examples.


## Video
<div class="video-player">
  Watch this chapter's video lesson here:
  https://www.youtube.com/watch?v=aeeje4nIzas.
</div>


## Nested Conditions

Pretty often the program logic requires the use of **`if`** or **`if-else`** statements, which are contained one inside another. They are called **nested** **`if`** or **`if-else`** statements. As implied by the title **"nested"**, these are **`if`** or **`if-else`** statements that are placed inside other **`if`** or **`else`** statements.

```python
if condition1:
    if condition2:
        # тяло
    else:
        # тяло
```

Nesting of*more than three conditional statements inside each other is not considered a good practice and has to be avoided, mostly through optimization of the structure/the algorithm of the code and/or by using another type of conditional statement, which we are going to examine below in this chapter.

### Example: Personal Titles

Depending on **age** (decimal number and **gender** (**m** / **f**), print a personal title:
* “**Mr.**” – a man (gender “**m**”) – 16 or more years old.
* “**Master**” – a boy (gender “**m**”) under 16 years.
* “**Ms.**” – a woman (gender “**f**”) – 16 or more years old.
* “**Miss**” – a girl (gender “**f**”) under 16 years.

#### Sample Input and Output

|Input|Output|Input|Output|
|----|----|----|------|
|12<br>f|Miss|17<br>m|Mr.|

|Input|Output|Input|Output|
|----|----|----|------|
|25<br>f|Ms.|13.5<br>m|Master|

#### Решение

We should notice that the **output** of the program **depends on a few things**. **First**, we have to check what is the entered **gender** and **then** check the **age**. Respectively, we are going to use **a few** **`if-else`** blocks. These blocks will be **nested**, meaning from **the result** of the first, we are going to **define** which one of the **others** to execute.

![](/assets/chapter-4-1-images/01.Personal-titles-01.jpg)

After **reading the input data from the console**, the following **program logic** should be executed:

![](/assets/chapter-4-1-images/01.Personal-titles-02.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#0](https://judge.softuni.org/Contests/Practice/Index/1051#0).


### Example: Small Shop

A Bulgarian entrepreneur opens **small shops** in **a few cities** with different **prices** for the following **products**:

|product / city|  Sofia  | Plovdiv |  Varna  |
|:------------:|:-------:|:-------:|:-------:|
|coffee<br>water<br>beer<br>sweets<br>peanuts|0.50<br>0.80<br>1.20<br>1.45<br>1.60<br>|0.40<br>0.70<br>1.15<br>1.30<br>1.50<br>|0.45<br>0.70<br>1.10<br>1.35<br>1.55|

Calculate the price by the given **city** (string), **product** (string) and **quantity** (float).

#### Sample Input and Output

|        Input        | Output |          Input         |Output|
|--------------------|-------|-----------------------|-----|
|coffee<br>Varna<br>2|0.90   |peanuts<br>Plovdiv<br>1|1.50 |

|        Input        | Output |          Input         |Output|
|--------------------|-------|-----------------------|-----|
|beer<br>Sofia<br>6  |7.20   |water<br>Plovdiv<br>3  |2.10 |

#### Solution

We **convert** all of the letters into **lower register** using the function **`.lower()`**, to compare products and cities **no matter** what the letters are – small or capital ones.

![](/assets/chapter-4-1-images/02.Small-shop-01.png)

#### Testing in the Judge System 

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#1](https://judge.softuni.org/Contests/Practice/Index/1051#1).


## More Complex Conditions

Let's take a look at how we can create more complex logical conditions. We can use the logical "**AND**" (**`and`**), logical "**OR**" (**`or`**), logical **negation** (**`not`**) and **brackets** (**`()`**).

## Logical "AND"

As we saw, in some tasks we have to make **many checks at once**. But what happens when to execute some code **more** conditions have to be executed and we **don't want to** make a **negation** (**`else`**) for each one of them? The option with nested **`if` blocks** is valid, but the code would look very **unordered** and for sure – **hard** to read and maintain.

The logical "**AND**" (operator **`and`**) means a few conditions have to be **fulfilled simultaneously**. The following table of truthfulness is applicable:

|a|b|a **`and`** b|
|-----|-----|-----|
|True<br>True<br>False<br>False|True<br>False<br>True<br>False|True<br>False<br>False<br>False|

### How does the `and` Operator work?

The **`and`** operator accepts **a couple of Boolean** (conditional) statements, which have a **`True`** or **`False`** value, and returns **one** bool statement as a **result**. Using it **instead** of a couple of nested **`if`** blocks, makes the code **more readable**, **ordered** and **easy** to maintain. But how does it **work**, when we put a **few** conditions one after another? As we saw above, the logical **"AND"** returns **`True`**, **only** when it accepts as **arguments statements** with the value **`True`**. Respectively, when we have a **sequence** of arguments, the logical "AND" **checks** either until one of the arguments is **over**, or until it **meets** an argument with value **`False`**. 

**Example**:

```python
a = True
b = True
c = False
d = True

result = a and b and c and d
# False (as d is not being checked)
```

The program will run in the **following** way: **It starts** the check form **`a`**, **reads** it and accepts that it has a **`True`** value, after which it **checks** **`b`**. After it has **accepted** that **`a`** and **`b`** return **`True`**, **it checks the next** argument. It gets to **`c`** and sees that the variable has a **`False`** value. After the program accepts that argument **`c`** has a **`False`** value, it calculates the expression **before `c`**, **independent** of what the value of **`d`** is. That is why the evaluation of **`d`** is being **skipped** and the whole expression is calculated as **`False`**.


### Example: Point in a Rectangle

Checks whether **point {x, y}** is placed **inside the rectangle {x1, y1} – {x2, y2}**. The input data is read from the console and consists of 6 lines: the decimal numbers **x1**, **y1**, **x2**, **y2**, **x** and **y** (as it is guaranteed that **x1 < x2** and **y1 < y2**).

#### Sample Input and Output

|Input |Output |Visualization|
|-----|------|:------:|
|2<br>-3<br>12<br>3<br>8<br>-1|Inside|![shop](/assets/chapter-4-1-images/03.Point-in-rectangle-01.png)|

#### Solution

A point is internal for a given polygon if the following four conditions are applied **at the same time**:

* The point is placed to the right from the left side of the rectangle.
* The point is placed to the left from the right side of the rectangle.
* The point is placed downwards from the upper side of the rectangle.
* The point is placed upwards from the down side of the rectangle.

![](/assets/chapter-4-1-images/03.Point-in-rectangle-03.png)

#### Testing in the Judge System

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#2](https://judge.softuni.org/Contests/Practice/Index/1051#2).


## Logical "OR"

The logical **"OR"** (operator **`or`**) means that **at least one** among a few conditions is fulfilled. Similar to the operator **`and`**, the logical **"OR"** accepts a few arguments of **bool** (conditional) type and returns **`True`** or **`False`**. We can easily guess that we **obtain** a value **`True`** whenever at least **one** of the arguments has a **`True`** value. This is shown at the truth table below:

In school, the teacher said: "Ivan or Peter should clean the board". For completing this condition (the board to be clean), it's possible only Ivan to clean it, only Peter to clean it or both of them to do it.

|a|b|a **`or`** b|
|:-----:|:-----:|:-----:|
|True<br>True<br>False<br>False|True<br>False<br>True<br>False|True<br>True<br>True<br>False|


### How does the `or` operator work?

We have already learned what the logical **"OR" represents**. But how is it being achieved? Just like with the logical **"AND"**, the program **checks** from left to right **the arguments** that are given. To obtain **`True`** from the expression, **just one** argument must have a **`True`** value. Respectively, the checking **continues** until an **argument** with **such** value is met or until the arguments **are over**.

Here is one **example** of the **`or`** operator in action:

```python
a = False
b = True
c = False
d = True

result = a or b or c or d
# True (as c and d are not being checked)
```

The program **checks `a`**, accepts that it has a value **`False`** and continues. Reaching **`b`**, it understands that it has a **`True`** value and the whole **expression** is calculated as **`True`**, **without** having to check **`c`** or **`d`**, because their values **wouldn't change** the result of the expression.

### Example: Fruit or Vegetable

Let's check whether a given **product** is **a fruit** or **a vegetable**. The "**fruits**" are **banana**, **apple**, **kiwi**, **cherry**, **lemon** and **grapes**. The "**vegetables**" are **tomato**, **cucumber**, **pepper** and **carrot**. Everything else is "**unknown**".

#### Sample Input and Output

|Input|Output|
|----|----|
|banana<br>tomato<br>java|fruit<br>vegetable<br>unknown|

#### Solution

We have to use a few conditional statements with logical "**OR**" (**`or`**):

![](/assets/chapter-4-1-images/04.Fruit-or-vegetable-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#3](https://judge.softuni.org/Contests/Practice/Index/1051#3).


## Logical Negation

**Logical negation** (operator **`not`**) means that a given condition is **not fulfilled**.

|a|**`not`** a|
|:----:|:----:|
|True|False|

The operator **`not`** accepts as an **argument** a bool variable and **returns** its value.
(the truth becomes a lie and the lie becomes a truth).

### Example: Invalid Number

A given **number is valid** if it is in the range [**100 … 200**] or it is **0**. Validate an **invalid** number.

#### Sample Input and Output

|Input|Output|
|----|----|
|75|invalid|
|150| (no output)|
|220|invalid|

#### Solution

![](/assets/chapter-4-1-images/05.Invalid-number-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#4](https://judge.softuni.org/Contests/Practice/Index/1051#4).


## The Parenthesis **`()`** Operator

Like the rest of the operators in programming, the operators **`and`** and **`or`** have a priority, as in the case **`and`** is with higher priority than **`or`**. The operator **`()`** serves for **changing the priority of operators** and is being calculated first, just like in mathematics. Using parentheses also gives the code better readability and is considered a good practice.


## По-сложни логически условия

Понякога условията може да са доста сложни, така че да изискват дълъг булев израз или поредица от проверки. Да разгледаме няколко такива примера.

### Пример: точка върху страна на правоъгълник

Да се напише програма, която проверява дали **точка {x, y}** се намира **върху някоя от страните на правоъгълник {x1, y1} - {x2, y2}**. Входните данни се четат от конзолата и се състоят от 6 реда: десетичните числа **x1**, **y1**, **x2**, **y2**, **x** и **y** (като се гарантира, че **x1 < x2** и **y1 < y2**). Да се отпечата "**Border**" (точката лежи на някоя от страните) или "**Inside / Outside**" (в противен случай).

![](/assets/chapter-4-1-images/06.Point-on-rectangle-border-01.png)

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|2<br>-3<br>12<br>3<br>12<br>-1|Border|2<br>-3<br>12<br>3<br>8<br>-1|Inside / Outside|

#### Решение

Точка лежи върху някоя от страните на правоъгълник, ако:

* **x** съвпада с **x1** или **x2** и същевременно **y** е между **y1** и **y2** или
* **y** съвпада с **y1** или **y2** и същевременно **x** е между **x1** и **x2**.

![](/assets/chapter-4-1-images/06.Point-on-rectangle-border-02.png)

Предходната проверка може да се опрости по този начин:

![](/assets/chapter-4-1-images/06.Point-on-rectangle-border-03.png)

Вторият начин с допълнителните булеви променливи е по-дълъг, но е много по-разбираем от първия, нали? Препоръчваме ви когато пишете булеви условия, да ги правите **лесни за четене и разбиране**, а не кратки. Ако се налага, ползвайте допълнителни променливи със смислени имена. Имената на булевите променливи трябва да подсказват каква стойност се съхранява в тях.

Остава да се допише кода, за да отпечатва "**Inside / Outside**", ако точката не е върху някоя от страните на правоъгълника.

#### Тестване в Judge системата

След като допишете решението, може да го тествате тук: [https://judge.softuni.org/Contests/Practice/Index/1051#5](https://judge.softuni.org/Contests/Practice/Index/1051#5).


### Пример: магазин за плодове

Магазин за плодове в **работни дни** продава на следните **цени**:

|Плод|Цена|
|:-----:|:-----:|
|banana<br>apple<br>orange<br>grapefruit<br>kiwi<br>pineapple<br>grapes|2.50<br>1.20<br>0.85<br>1.45<br>2.70<br>5.50<br>3.85|

В почивни дни цените са **по-високи**:

|Плод|Цена|
|:-----:|:-----:|
|banana<br>apple<br>orange<br>grapefruit<br>kiwi<br>pineapple<br>grapes|2.70<br>1.25<br>0.90<br>1.60<br>3.00<br>5.60<br>4.20|

Напишете програма, която чете от конзолата **плод** (banana / apple / …), **ден от седмицата** (Monday / Tuesday / …) и **количество (десетично число)** и **пресмята цената** според цените от таблиците по-горе. Резултатът да се отпечата **закръглен с 2 цифри след десетичния знак**. При **невалиден ден** от седмицата или **невалидно име** на плод да се отпечата **“error”**.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|----|----|----|----|
|orange<br>Sunday<br>3|2.70|kiwi<br>Monday<br>2.5|6.75|

|Вход|Изход|Вход|Изход|
|----|----|----|----|
|grapes<br>Saturday<br>0.5|2.10|tomato<br>Monday<br>0.5|error|

#### Решение

![](/assets/chapter-4-1-images/07.Fruit-shop-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#6](https://judge.softuni.org/Contests/Practice/Index/1051#6).


### Пример: търговски комисионни

Фирма дава следните **комисионни** на търговците си според **града**, в който работят и **обема на продажбите s**:

|Град|0 <= s <= 500|500 < s <= 1000|1000 < s <= 10000|s > 10000|
|:----:|:----:|:----:|:----:|:----:|
|Sofia<br>Varna<br>Plovdiv|5%<br>4.5%<br>5.5%|7%<br>7.5%<br>8%|8%<br>10%<br>12%|12%<br>13%<br>14.5%|

Напишете програма, която чете име на **град** (стринг) и обем на **продажбите** (десетично число) и изчислява размера на  комисионната. Резултатът да се изведе закръглен с **2 десетични цифри след десетичния знак**. При **невалиден град или обем на продажбите** (отрицателно число) да се отпечата "**error**".

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|-----|-----|
|Sofia<br>1500|120.00|Plovdiv<br>499.99|27.50|Kaspichan<br>-50|error|

#### Решение

При прочитането на входа можем да обърнем града в малки букви (с функцията **`.lower()`**). Първоначално задаваме комисионната да е **`-1`**. Тя ще бъде променена, ако градът и ценовият диапазон бъдат намерени в таблицата с комисионните. За да изчислим комисионната според града и обема на продажбите, се нуждаем от няколко вложени **`if` проверки**, както е в примерния код по-долу:

![](/assets/chapter-4-1-images/08.Trade-comissions-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#7](https://judge.softuni.org/Contests/Practice/Index/1051#7).

### Пример: ден от седмицата

Нека напишем програма, която принтира **деня от седмицата** (на английски) според **въведеното число** (1 … 7) или "**Error**", ако е подаден невалиден ден.

#### Примерен вход и изход

|Вход|Изход|
|-----|-----|
|1<br>7<br>-1|Monday<br>Sunday<br>Error|

#### Решение

![](/assets/chapter-4-1-images/09.Day-of-week-01.png)

<table><tr><td><img src="/assets/alert-icon.png" style="max-width:50px" /></td>
<td><b>Добра практика</b> е на <b>първо</b> място да поставяме онези условия, които обработват <b>най-често случилите се ситуации</b>, а <b>конструкциите</b>, обработващи <b>по-рядко възникващи ситуации</b>, да оставим в <b>края на конструкцията</b>. Друга <b>добра практика</b> е да <b>подреждаме случайте</b> в <b>нарастващ ред</b>, без значение дали са целочислени или символни.</td>
</tr></table>

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#8](https://judge.softuni.org/Contests/Practice/Index/1051#8).


### Пример: вид животно

Напишете програма, която принтира вида на животно според името му: 

* dog -> **mammal**
* crocodile, tortoise, snake -> **reptile**
* others -> **unknown**

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|Вход|Изход|
|------|------|------|------|------|-----|
|tortoise|reptile|dog|mammal|elephant|unknown|

#### Решение

Можем да решим задачата чрез няколко **`if-elif`** проверки по следния начин:

![](/assets/chapter-4-1-images/10.Animal-type-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#9](https://judge.softuni.org/Contests/Practice/Index/1051#9).


## Какво научихме от тази глава?

Да си припомним новите конструкции и програмни техники, с които се запознахме в тази глава:

### Вложени проверки

```python
if condition1:
    if condition2:
        # тяло 
    else:
        # тяло
```

### По-сложни проверки с and, or, not и ()

```python
if (x == left or x == right) and (y >= top or y <= bottom):
    print(...) 
```

## Упражнения: по-сложни проверки

Нека сега да упражним работата с по-сложни проверки. Да решим няколко практически задачи.

### Задача: кино

В една кинозала столовете са наредени в **правоъгълна** форма в **r** реда и **c** колони. Има три вида прожекции с билети на **различни** цени:

* **Premiere** – премиерна прожекция, на цена **12.00** лева.
* **Normal** – стандартна прожекция, на цена **7.50** лева.
* **Discount** – прожекция за деца, ученици и студенти на намалена цена от **5.00** лева.

Напишете програма, която въвежда **тип прожекция** (стринг), брой **редове** и брой **колони** в залата (цели числа) и изчислява **общите приходи** от билети при **пълна зала**. Резултатът да се отпечата във формат като в примерите по-долу - с 2 цифри след десетичния знак.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|----|-----|----|-----|
|Premiere<br>10<br>12|1440.00 leva|Normal<br>21<br>13|2047.50 leva|

#### Насоки и подсказки 

При прочитането на входа можем да обърнем типа на прожекцията в малки букви (с функцията **`.lower()`**). Създаваме и променлива, която ще ни съхранява изчислените приходи. В друга променлива пресмятаме пълния капацитет на залата. Използваме **`if-elif`** условна конструкция, за да изчислим прихода в зависимост от вида на прожекцията и отпечатваме резултата на конзолата в зададения формат (потърсете нужната **Python** функционалност в интернет). 

Примерен код на описаната идея (части от кода са замъглени с цел да се стимулира самостоятелно мислене и решение):

![](/assets/chapter-4-1-images/11.Cinema-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#10](https://judge.softuni.org/Contests/Practice/Index/1051#10).


### Задача: волейбол

Влади е студент, живее в София и си ходи от време на време до родния град. Той е много запален по волейбола, но е зает през работните дни и играе **волейбол** само през **уикендите** и в **празничните дни**. Влади играе **в София** всяка **събота**, когато **не е на работа** и **не си пътува до родния град**, както и в **2/3 от празничните дни**. Той пътува до **родния си град h пъти** в годината, където играе волейбол със старите си приятели в **неделя**. Влади **не е на работа 3/4 от уикендите**, в които е в София. Отделно, през **високосните години** Влади играе с **15% повече** волейбол от нормалното. Приемаме, че годината има точно **48 уикенда**, подходящи за волейбол. Напишете програма, която изчислява **колко пъти Влади е играл волейбол** през годината. **Закръглете резултата** надолу до най-близкото цяло число (напр. 2.15 -> 2; 9.95 -> 9).

Входните данни се четат от конзолата:

* Първият ред съдържа думата “**leap**” (високосна година) или “**normal**” (нормална година с 365 дни).
* Вторият ред съдържа цялото число **p** – брой празници в годината (които не са събота или неделя).
* Третият ред съдържа цялото число **h** – брой уикенди, в които Влади си пътува до родния град.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|leap<br>5<br>2|45|normal<br>3<br>2|38|

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|normal<br>11<br>6|44|leap<br>0<br>1|41|

#### Насоки и подсказки

Стандартно прочитаме входните данни от конзолата като за избягване на грешки при въвеждане обръщаме текста в малки букви с функцията **`.lower()`**. Последователно пресмятаме **уикендите прекарани в София**, **времето за игра в София** и **общото време за игра**. Накрая проверяваме дали годината е **високосна**, правим допълнителни изчисления при необходимост и извеждаме резултата на конзолата **закръглен надолу** до най-близкото **цяло число** (потърсете **Python** функция с такава функционалност в интернет).

Примерен код на описаната идея (части от кода са замъглени с цел да се стимулира самостоятелно мислене и решение):

![](/assets/chapter-4-1-images/12.Volleyball-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#11](https://judge.softuni.org/Contests/Practice/Index/1051#11).


### Задача: * точка във фигурата

Фигура се състои от **6 блокчета с размер h \* h**, разположени като на фигурата. Долният ляв ъгъл на сградата е на позиция {0, 0}. Горният десен ъгъл на фигурата е на позиция {**2\*h**, **4\*h**}. На фигурата координатите са дадени при **h = 2**:

<p align="center"><img src="assets/chapter-4-1-images/13.Point-in-the-figure-01.png" /></p>

Да се напише програма, която въвежда цяло число **h** и координатите на дадена **точка {x, y}** (цели числа) и отпечатва дали точката е вътре във фигурата (**inside**), вън от фигурата (**outside**) или на някоя от стените на фигурата (**border**).

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|2<br>3<br>10|outside|2<br>3<br>1|inside|

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|2<br>2<br>2|border|2<br>6<br>0|border|

|Вход|Изход|Вход|Изход|
|----|-----|-----|-----|
|2<br>0<br>6|outside|15<br>13<br>55|outside|

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|15<br>29<br>37|inside|15<br>37<br>18|outside|

|Вход|Изход|Вход|Изход|
|-----|-----|-----|-----|
|15<br>-4<br>7|outside|15<br>30<br>0|border|

#### Насоки и подсказки

Примерна логика за решаване на задачата (не е единствената правилна):

* Може да разделим фигурата на **два правоъгълника** с обща стена:

<p align="center"><img src="assets/chapter-4-1-images/13.Point-in-the-figure-03.png" /></p>

* Една точка е **външна (outside)** за фигурата, когато е едновременно **извън** двата правоъгълника.
* Една точка е **вътрешна (inside)** за фигурата, ако е вътре в някой от правоъгълниците (изключвайки стените им) или лежи върху общата им стена.
* В **противен случай** точката лежи на стената на правоъгълника (**border**).

Примерен код (части от кода са замъглени с цел да се стимулира самостоятелно мислене и решение):

![](/assets/chapter-4-1-images/13.Point-in-the-figure-02.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1051#12](https://judge.softuni.org/Contests/Practice/Index/1051#12).
