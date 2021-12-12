# Chapter 4.1. More Complex Conditions

In the **current** chapter, we are going to examine **nested conditional statements** in the **Python** language, by which our program can execute **conditions**, that contain other **nested conditional statements**. We call them **"nested"** because **we put `if` condition** into **another `if` condition**. We are going to examine the **more complex logical conditions** through proper examples.

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
        # body
    else:
        # body
```

Nesting of **more than three conditional** statements inside each other is not considered a good practice and has to be avoided, mostly through optimization of the structure/the algorithm of the code and/or by using another type of conditional statement, which we are going to examine below in this chapter.

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

#### Solution

We should notice that the **output** of the program **depends on a few things**. **First**, we have to check what is the entered **gender** and **then** check the **age**. Respectively, we are going to use **a few** **`if-else`** blocks. These blocks will be **nested**, meaning from **the result** of the first, we are going to **define** which one of the **others** to execute.

![](/assets/chapter-4-1-images/01.Personal-titles-01.jpg)

After **reading the input data from the console**, the following **program logic** should be executed:

![](/assets/chapter-4-1-images/01.Personal-titles-02.PNG)

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

![](/assets/chapter-4-1-images/02.Small-shop-01.PNG)

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
|2<br>-3<br>12<br>3<br>8<br>-1|Inside|![shop](/assets/chapter-4-1-images/03.Point-in-rectangle-01.PNG)|

#### Solution

A point is internal for a given polygon if the following four conditions are applied **at the same time**:

* The point is placed to the right from the left side of the rectangle.
* The point is placed to the left from the right side of the rectangle.
* The point is placed downwards from the upper side of the rectangle.
* The point is placed upwards from the down side of the rectangle.

![](/assets/chapter-4-1-images/03.Point-in-rectangle-03.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#2](https://judge.softuni.org/Contests/Practice/Index/1051#2).

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

![](/assets/chapter-4-1-images/04.Fruit-or-vegetable-01.PNG)

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

![](/assets/chapter-4-1-images/05.Invalid-number-01.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#4](https://judge.softuni.org/Contests/Practice/Index/1051#4).

## The Parenthesis **`()`** Operator

Like the rest of the operators in programming, the operators **`and`** and **`or`** have a priority, as in the case **`and`** is with higher priority than **`or`**. The operator **`()`** serves for **changing the priority of operators** and is being calculated first, just like in mathematics. Using parentheses also gives the code better readability and is considered a good practice.

## More Complex Conditions - Examples

Sometimes the conditions may be **very complex**, so they can require a long bool expression or a sequence of conditions. Let's take a look at a few examples.

### Example: Point on a Rectangle Border

Write a program that checks whether a **point {x, y}** is placed **onto any of the sides of a rectangle {x1, y1} – {x2, y2}**. The input data is read from the console and consists of 6 lines: the decimal numbers **x1**, **y1**, **x2**, **y2**, **x** and **y** (as it is guaranteed that **x1 < x2** and **y1 < y2**). Print "**Border**" (if the point lies on any of the sides) or "**Inside / Outside**" (in the opposite case).

![](/assets/chapter-4-1-images/06.Point-on-rectangle-border-01.PNG)

#### Sample Input and Output

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|2<br>-3<br>12<br>3<br>12<br>-1|Border|2<br>-3<br>12<br>3<br>8<br>-1|Inside / Outside|

#### Solution

The point lies on any of the sides of the rectangle if:

* **x** coincides with **x1** or **x2** and at the same time **y** is between **y1** and **y2** or
* **y** coincides with **y1** or **y2** and at the same time **x** is between **x1** and **x2**.

![](/assets/chapter-4-1-images/06.Point-on-rectangle-border-02.PNG)

The previous conditional statement can be simplified by this way:

![](/assets/chapter-4-1-images/06.Point-on-rectangle-border-03.PNG)

The second way with an additional boolean variable is longer but it's also more readable than the first, right? We advise you when writing boolean conditions to make them **easier for reading than understanding** and not short. If you are forced to, use additional variables with similar names. Names of the boolean variables should be with reasonable names. They should hint at what value will be stored in them.

All that's left is to write the code, that prints "**Inside / Outside**" if the point is not on one of the sides of the rectangle.

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#5](https://judge.softuni.org/Contests/Practice/Index/1051#5).

### Example: Fruit Shop

A fruit shop during **weekdays** sells at the following **prices**:

|Fruit|Price|
|:-----:|:-----:|
|banana<br>apple<br>orange<br>grapefruit<br>kiwi<br>pineapple<br>grapes|2.50<br>1.20<br>0.85<br>1.45<br>2.70<br>5.50<br>3.85|

During the **weekend days** the prices are **higher**:

|Fruit|Price|
|:-----:|:-----:|
|banana<br>apple<br>orange<br>grapefruit<br>kiwi<br>pineapple<br>grapes|2.70<br>1.25<br>0.90<br>1.60<br>3.00<br>5.60<br>4.20|

Write a program that **reads** from the console a **fruit** (banana / apple / …), **a day of the week** (Monday / Tuesday / …) and **a quantity (a decimal number)** and **calculates the price** according to the prices from the tables above. The result has to be printed **rounded up to 2 digits after the decimal point**. Print **“error”** if it is an **invalid day** of the week or an **invalid name** of a fruit.

#### Sample Input and Output

|Input|Output|Input|Output|
|----|----|----|----|
|orange<br>Sunday<br>3|2.70|kiwi<br>Monday<br>2.5|6.75|

|Input|Output|Input|Output|
|----|----|----|----|
|grapes<br>Saturday<br>0.5|2.10|tomato<br>Monday<br>0.5|error|

#### Solution

![](/assets/chapter-4-1-images/07.Fruit-shop-01.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#6](https://judge.softuni.org/Contests/Practice/Index/1051#6).

### Example: Trade Fees

A company is giving the following **commissions** to its traders according to the **city**, in which they are working and the **volume of sales s**:

|City|0 <= s <= 500|500 < s <= 1000|1000 < s <= 10000|s > 10000|
|:----:|:----:|:----:|:----:|:----:|
|Sofia<br>Varna<br>Plovdiv|5%<br>4.5%<br>5.5%|7%<br>7.5%<br>8%|8%<br>10%<br>12%|12%<br>13%<br>14.5%|

Write a **program** that reads the name of a **city** (string) and the volume of **sales** (float) and calculates the rate of the commission fee. The result has to be shown rounded **up to 2 digits after the decimal point**. When there is an **invalid city or volume of sales** (a negative number), print "**error**".

#### Sample Input and Output

|Input|Output|Input|Output|Input|Output|
|-----|-----|-----|-----|-----|-----|
|Sofia<br>1500|120.00|Plovdiv<br>499.99|27.50|Kaspichan<br>-50|error|

#### Solution

When reading the input, we could convert the city into small letters (with the function **`.lower()`**). Initially, we set the commission fee to **`-1`**. It will be changed if the city and the price range are found in the table of commissions.
To calculate the commission according to the city and volume of sales, we need a few nested **`if` statements**, as in the sample code below:

![](/assets/chapter-4-1-images/08.Trade-comissions-01.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#7](https://judge.softuni.org/Contests/Practice/Index/1051#7).

### Example: Day of the Week

Let's write a program that prints **the day of the week** depending on the **given number** (1 … 7) or "**Error!**" if invalid input is given.

#### Sample Input and Output

|Input|Output|
|-----|-----|
|1<br>7<br>-1|Monday<br>Sunday<br>Error|

#### Solution

![](/assets/chapter-4-1-images/09.Day-of-week-01.PNG)

<table><tr><td><img src="/assets/alert-icon.PNG" style="max-width:50px" /></td>
<td><b>It is a good practice</b> to put at the <b>first</b> place those <b><code>case</code> statements</b> that process <b>the most common situations</b> and leave the <b><code>case</code> constructions</b> processing <b>the rarer situations</b> at <b>the end, before the <code>default</code> construction</b>. Another <b>good practice</b> is to <b>arrange the <code>case</code> labels</b> in <b>ascending order</b>, regardless of whether they are integral or symbolic.</td>
</tr></table>

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#8](https://judge.softuni.org/Contests/Practice/Index/1051#8).

### Example: Animal Type

Write a program that prints the type of the animal depending on its name: 

* dog -> **mammal**
* crocodile, tortoise, snake -> **reptile**
* others -> **unknown**

#### Sample Input and Output

|Input|Output|Input|Output|Input|Output|
|------|------|------|------|------|-----|
|tortoise|reptile|dog|mammal|elephant|unknown|

#### Solution

We can solve the example with a few **`if-elif`** conditional statements by doing so:

![](/assets/chapter-4-1-images/10.Animal-type-01.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#9](https://judge.softuni.org/Contests/Practice/Index/1051#9).

## What have we learned from this chapter?

Let's review the new constructions and program techniques we have met in this chapter:

### Nested Conditions

```python
if condition1:
    if condition2:
        # body 
    else:
        # body
```

### Complex Conditions with and, or, not and ()

```python
if (x == left or x == right) and (y >= top or y <= bottom):
    print(...) 
```

## Exercises: More Complex Conditions 

Let's practice using more complex conditions. We will solve a few practical exercises.

### Problem: Cinema

In a cinema hall, the chairs are ordered in a **rectangle** shape in **r** rows and **c** columns. There are three types of screenings with tickets of **different** prices:

* **Premiere** – a premiere screening, with a price of **12.00** BGN.
* **Normal** – a standard screening, with a price of **7.50** BGN.
* **Discount** – a screening for children and students at a reduced price – **5.00** BGN.

Write a program that enters a **type of screening** (string), a number for **rows** and a number for **columns** in the hall (integer numbers) and calculates **the total income** from tickets from a **full hall**. The result has to be printed in the same format as in the examples below – rounded up to 2 digits after the decimal point.

#### Sample Input and Output

|Input|Output|Input|Output|
|----|-----|----|-----|
|Premiere<br>10<br>12|1440.00 leva|Normal<br>21<br>13|2047.50 leva|

#### Hints and Guidelines

While reading the input, we could convert the screening type into small letters (with the function **`.lower()`**). We create and initialize a variable that will store the calculated income. In another variable, we calculate the full capacity of the hall. We use an **`if-elif`** conditional statement to calculate the income according to the type of the projection and print the result on the console in the given format (look for the needed **Python** functionality on the internet). 

Sample code (parts of the code are blurred with the purpose to stimulate your thinking and solving skills):

![](/assets/chapter-4-1-images/11.Cinema-01.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#10](https://judge.softuni.org/Contests/Practice/Index/1051#10).

### Problem: Volleyball

Vladimir is a student, lives in Sofia and goes to his hometown from time to time. He is very keen on volleyball, but is busy during weekdays and plays **volleyball** only during **weekends** and on **holidays**. Vladimir plays **in Sofia** every **Saturday** when **he is not working**, and **he is not traveling to his hometown** and also during **2/3 of the holidays**. He travels to his **hometown h times** a year, where he plays volleyball with his old friends on **Sunday**. Vladimir **is not working 3/4 of the weekends**, during which he is in Sofia. Furthermore, during **leap years** Vladimir plays **15% more** volleyball than usual. We accept that the year has exactly **48 weekends**, suitable for volleyball. 
Write a program that calculates **how many times Vladimir has played volleyball** throughout the year. **Round the result** down to the nearest whole number (e.g. 2.15 -> 2; 9.95 -> 9).

The input data is read from the console:

 * The first line contains the word “**leap**” (leap year) or “**normal**” (a normal year with 365 days).
 * The second line contains the integer **p** – the count of holidays in the year (which are not Saturday or Sunday).
 * The third line contains the integer **h** – the count of weekends, in which Vladimir travels to his hometown.

#### Sample Input and Output

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|leap<br>5<br>2|45|normal<br>3<br>2|38|

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|normal<br>11<br>6|44|leap<br>0<br>1|41|

#### Hints and Guidelines

As usual, we read the input data from the console and, to avoid making mistakes, we convert the text into small letters with the function **`.lower()`**. Consequently, we calculate **the weekends spent in Sofia**, **the time for playing in Sofia** and **the common playtime**. At last, we check whether the year is a **leap**, we make additional calculations when necessary and we print the result on the console **rounded down** to the nearest **integer** (look for a **Python** class with such functionality).

A sample code (parts of the code are blurred on purpose to stimulate independent thinking and solving skills):

![](/assets/chapter-4-1-images/12.Volleyball-01.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#11](https://judge.softuni.org/Contests/Practice/Index/1051#11).

### Problem: * Point in the Figure

The figure consists of **6 blocks with size h \* h**, placed as in the figure below. The lower left angle of the building is on position {0, 0}. The upper right angle of the figure is on position {**2\*h**, **4\*h**}. The coordinates given in the figure are for **h = 2**:

<p align="center"><img src="assets/chapter-4-1-images/13.Point-in-the-figure-01.PNG" /></p>

Write a program that enters an integer **h** and the coordinates of a given **point {x, y}** (integers) and prints whether the point is inside the figure (**inside**), outside of the figure (**outside**) or on any of the borders of the figure (**border**).

#### Sample Input and Output

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|2<br>3<br>10|outside|2<br>3<br>1|inside|

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|2<br>2<br>2|border|2<br>6<br>0|border|

|Input|Output|Input|Output|
|----|-----|-----|-----|
|2<br>0<br>6|outside|15<br>13<br>55|outside|

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|15<br>29<br>37|inside|15<br>37<br>18|outside|

|Input|Output|Input|Output|
|-----|-----|-----|-----|
|15<br>-4<br>7|outside|15<br>30<br>0|border|

#### Hints and Guidelines

A possible logic for solving the task (not the only correct one):

* We might split the figure into **two rectangles** with a common side:

<p align="center"><img src="assets/chapter-4-1-images/13.Point-in-the-figure-03.PNG" /></p>

* A point is **outer (outside)** for the figure when it is **outside** both of the rectangles.
* A point is **inner (inside)** for the figure if it is inside one of the rectangles (excluding their borders) or lies on their common side.
* In **every other case**, the point lies on the border of the rectangle (**border**).

Sample code (parts of the code are blurred to stimulate logical thinking and solving skills):

![](/assets/chapter-4-1-images/13.Point-in-the-figure-02.PNG)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1051#12](https://judge.softuni.org/Contests/Practice/Index/1051#12).
