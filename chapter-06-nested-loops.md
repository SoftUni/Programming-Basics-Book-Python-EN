# Chapter 6.1. Nested Loops

In the current chapter, we will be looking at **nested loops** and how to use `for` loops to **draw** various **figures on the console**, that contain symbols and signs, ordered in rows and columns on the console. We will use **single** and **nested loops** (loops that stay in other loops), **calculations** and **checks**, in order to print on the console simple and not so simple figures by specified sizes.


## Video 

<div class="video-player">
  Watch the video lesson of this chapter here: 
  https://www.youtube.com/watch?v=kkxl1bitNAg.
</div>


### Example: Rectangle Made of 10 x 10 Asterisks

Print on the console a rectangle made out of **10 x 10** asterisks.

|Input|Output|
|---|---|
|(None)|<code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code><br><code>\*\*\*\*\*\*\*\*\*\*</code>|

#### Hints and Guidelines

![](/assets/chapter-6-1-images/01.Rectangle-of-10-x-10-stars-01.png)

How does the example work? We initialize **a loop with a variable `i`**. The default value of the variable is  **`i = 0`**. With each iteration of the cycle, the variable increases by **1** until it is **less than 10**. This way the code in the body of the loop is executed **10 times** - from **0<sup>-th</sup>** to **9<sup>-th</sup>** included. In the body of the loop, we print a new line on the console **`'*' * 10`**, which creates a string of 10 asterisks.


#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#0](https://judge.softuni.org/Contests/Practice/Index/1055#0).


###Example: Rectangle Made of N x N Asterisks

Write a program which receives a positive number **n** and prints on the console **a rectangle of N x N asterisks**. 

|Input|Output|Input|Output|Input|Output|
|---|---|---|---|---|---|
|2|<code>\*\*</code><br><code>\*\*</code>|3|<code>\*\*\*</code><br><code>\*\*\*</code><br><code>\*\*\*</code>|4|<code>\*\*\*\*</code><br><code>\*\*\*\*</code><br><code>\*\*\*\*</code><br><code>\*\*\*\*</code>|

#### Hints and Guidelines

The task is similar to the previous one: 

![](/assets/chapter-6-1-images/02.Rectangle-of-N-x-N-stars-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#1](https://judge.softuni.org/Contests/Practice/Index/1055#1).


## Nested loops

A **nested loop** is a construction where **the body of one loop** (the outer one) **stays inside another loop** (the inner one). In each iteration of the outer loop, **the whole** inner loop is executed. This happens in the following way:

 - When nested loops start executing, **the outer loop starts** first: **initialization** of its control variable is performed and after checking for end of the loop, the code in its body is executed.
  - After that, **the inner loop is executed**. The control variable's start position is initialized, a check for end of the loop is made and the code in its body is executed.
 - When the set value for **end of the loop** is reached, the program goes back one step up and continues executing the previous outer loop. The control variable of the outer loop changes with one step, a check is made to see if the condition for end of the loop is met and **a new execution of the nested \(inner\) loop is started**.
 - This is repeated until the variable of the outer loop meets the condition to **end the loop**.

Here is an **example** that illustrates nested loops. The aim is again to print a rectangle made of **N x N asterisk**, in which for each row a loop iterates from **1** to **N**, and for each column a nested loop is executed from **1** to **N**:

![](/assets/chapter-6-1-images/00.Nested-loops-01.png)

In **Python**, when the standard initial value of the variable in the loop (**`i = 0`**) does not work for us, we can change it with the above syntax. I.e. when we want the loop to start from **1** and rotate to **`n`** inclusive, we write: **`for i in range (1, n + 1)`**. The first value in parentheses indicates the beginning of the loop, and the second - the end of the loop, but not including, i.e. the loop ends before it is reached. 

Let's look at the example above. After the initialization of the **first (outer) loop**, its **body**, which contains **the second (nested) loop**, starts to run. It itself prints one line **`n`** of asterisks. After the **internal** loop **completes** its execution in the first iteration of the external one, then **the external one will continue**, i.e. will print a blank line on the console. **Then** the **first** loop ** will be **updated** and the whole **second** (nested) loop will be executed again. The inner loop will be executed as many times as the body of the outer loop is executed, in this case **`n`** times. 

### Example: Square Made of Asterisks

Print on the console a square made of **N x N** asterisks:

|Input|Output|Input|Output|Input|Output|
|---|---|---|---|---|---|
|2|<code>\* \*</code><br><code>\* \*</code>|3|<code>\* \* \*</code><br><code>\* \* \*</code><br><code>\* \* \*</code>|4|<code>\* \* \* \*</code><br><code>\* \* \* \*</code><br><code>\* \* \* \*</code><br><code>\* \* \* \*</code>|

#### Hints and Guidelines

The problem is similar to the last one. The difference here is that we need to figure out how to add a whitespace after the asterisks so that there aren't any excess white spaces at the beginning and the end:

![](/assets/chapter-6-1-images/03.Square-01.png)

#### Тестване в Judge системата

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#2](https://judge.softuni.org/Contests/Practice/Index/1055#2).

### Example: Triangle Made of Dollars

Write a program which receives an integer **n** and prints **a triangle made of dollars**.

|Input|Output|Input|Output|Input|Output
|---|---|---|---|---|---|
|3|<code>&dollar;</code><br><code>&dollar; &dollar;</code><br><code>&dollar; &dollar; &dollar;</code>|4|<code>&dollar;</code><br><code>&dollar; &dollar;</code><br><code>&dollar; &dollar; &dollar;</code><br><code>&dollar; &dollar; &dollar; &dollar;</code>|5|<code>&dollar;</code><br><code>&dollar; &dollar;</code><br><code>&dollar; &dollar; &dollar;</code><br><code>&dollar; &dollar; &dollar; &dollar;</code><br><code>&dollar; &dollar; &dollar; &dollar; &dollar;</code>|

#### Hints and Guidelines

The problem is **similar** to those for drawing **a rectangle** and **square**. Once again, we will use **nested loops**, but there is **a  catch** here. The difference is that **the number of columns** that we need to print depends on **the row**, on which we are and not on the input number **`n`**. From the example input and output data, we see that **the count of dollars depends** on which **row** we are on at the moment of the printing, i.e. 1 dollar means the first row, 3 dollars mean the third row, and so on. Let's see the following example in detail. We see that **the variable** of **the nested** loop is connected with the variable of **the outer** one. This way our program prints the desired triangle:

![](/assets/chapter-6-1-images/04.Triangle-of-dollars-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#3](https://judge.softuni.org/Contests/Practice/Index/1055#3).


### Example: Square Frame

Write a program which receives a positive integer **n** and draws on the console **a square frame** with a size of **N x N**.

|Input|Output|Input|Output|
|---|---|---|---|
|3|<code>+ - +</code><br><code>&#124; - &#124;</code><br><code>+ - +</code>|4|<code>+ - - +</code><br><code>&#124; - - &#124;</code><br><code>&#124; - - &#124;</code><br><code>+ - - +</code>|

|Input|Output|Input|Output|
|---|---|---|---|
|5|<code>+ - - - +</code><br><code>&#124; - - - &#124;</code><br><code>&#124; - - - &#124;</code><br><code>&#124; - - - &#124;</code><br><code>+ - - - +</code>|6|<code>+ - - - - +</code><br><code>&#124; - - - - &#124;</code><br><code>&#124; - - - - &#124;</code><br><code>&#124; - - - - &#124;</code><br><code>&#124; - - - - &#124;</code><br><code>+ - - - - +</code>|

#### Hints and Guidelines

We can solve the problem in the following way:
* We read from the console the number **`n`**.
* We print **the upper part**: first a **`+`** sign, then **n-2** times **`-`** and in the end a **`+`** sign.
* We print **the middle part**: we print **n-2** rows, as we first print a **`|`** sign, then **n-2** times **`-`** and in the end again a **`|`** sign. We can do this with nested loops.
* We print **the lower part**: first a **`+`** sign, then **n-2** times **`-`** and in the end a **`+`** sign.

Here is an example implementation of the above idea with nested loops:

![](/assets/chapter-6-1-images/05.Square-frame-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#4](https://judge.softuni.org/Contests/Practice/Index/1055#4).


### Problem: Rhombus Made of Asterisks

Write a program which receives a positive integer **n** and prints **a rhombus made of asterisks** with size **N**.

|Input|Output|Input|Output|
|---|---|---|---|
|1|<code>\*</code>|2|<code>&nbsp;\*&nbsp;</code><br><code>\*&nbsp;\*</code><br><code>&nbsp;\*&nbsp;</code><br>|


|Input|Output|Input|Output|
|---|---|---|---|
|3|<code>&nbsp;&nbsp;\*&nbsp;&nbsp;</code><br><code>&nbsp;\*&nbsp;\*&nbsp;</code><br><code>\*&nbsp;\*&nbsp;\*</code><br><code>&nbsp;\*&nbsp;\*&nbsp;</code><br><code>&nbsp;&nbsp;\*&nbsp;&nbsp;</code>|4|<code>&nbsp;&nbsp;&nbsp;\*&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;\*&nbsp;\*&nbsp;&nbsp;</code><br><code>&nbsp;\*&nbsp;\*&nbsp;\*&nbsp;</code><br><code>\*&nbsp;\*&nbsp;\*&nbsp;\*</code><br><code>&nbsp;\*&nbsp;\*&nbsp;\*&nbsp;</code><br><code>&nbsp;&nbsp;\*&nbsp;\*&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&nbsp;\*&nbsp;&nbsp;&nbsp;</code>|

#### Hints and Guidelines

To solve this problem, we need to mentally **divide** **the rhombus** into **two parts** – the **upper** one, which **also** includes the middle row, and the **lower** one. For **the printing** of each part, we will use **two** separate loops, as we leave the reader to decide the dependency between **`n`** and the variables of the loops. For the first loop we can use the following guidelines:

* We print **`n-row`** whitespaces.
* We print **`*`**.
* We print **`row-1`** times **`*`**.

**The second** (lower) part will be printed **similarly**, which again we leave to the reader to do..

![](/assets/chapter-6-1-images/06.Rhombus-of-stars-01.png)

In Python, the standard step of the <strong><code>for</code></strong> loop is positive and is equal to 1. If we want to change it, we must use a third parameter in the arguments of the loop: <code><b>for i in range (0, 100, 2)</b></code>. The third parameter in this case shows that the variable will increase from 0 to 99 inclusive, with step 2.</td>
</tr></table>

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#5](https://judge.softuni.org/Contests/Practice/Index/1055#5).

### Problem: Christmas Tree

Write a program which receives a number **n** (1 ≤ n ≤ 100) and prints a Christmas tree with a height of **N + 1**.

|Input|Output|Input|Output|
|---|---|---|---|
|1|<code>&nbsp;&nbsp;&#124;&nbsp;&nbsp;</code><br><code>\*&nbsp;&#124;&nbsp;\*</code>|2|<code>&nbsp;&nbsp;&nbsp;&#124;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;\*&nbsp;&#124;&nbsp;\*&nbsp;</code><br><code>\*\*&nbsp;&#124;&nbsp;\*\*</code>|

|Input|Output|Input|Output|
|---|---|---|---|
|3|<code>&nbsp;&nbsp;&nbsp;&nbsp;&#124;&nbsp;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;\*&nbsp;&#124;&nbsp;\*&nbsp;&nbsp;</code><br><code>&nbsp;\*\*&nbsp;&#124;&nbsp;\*\*&nbsp;</code><br><code>\*\*\*&nbsp;&#124;&nbsp;\*\*\*</code>|4|<code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#124;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&nbsp;\*&nbsp;&#124;&nbsp;\*&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;\*\*&nbsp;&#124;&nbsp;\*\*&nbsp;&nbsp;</code><br><code>&nbsp;\*\*\*&nbsp;&#124;&nbsp;\*\*\*&nbsp;</code><br><code>\*\*\*\*&nbsp;&#124;&nbsp;\*\*\*\*</code>|

#### Hints and Guidelines

From the examples, we see that **the Christmas tree** can be **divided** into **three** logical parts. **The first** part is **the asterisks and the whitespaces before and after them**, **the middle** part is **` | `**, and **the last** part is again **asterisks**, but this time there are **whitespaces** only **before** them. The printing can be done with only **one loop** and the operation **string multiplication** , which we will use once for the asterisks and once for the whitespaces:

![](/assets/chapter-6-1-images/07.Christmas-tree-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#6](https://judge.softuni.org/Contests/Practice/Index/1055#6).


## Drawing more complex figures

Let's look at how to **draw figures** using **nested loops** with more complex logic, for which we need to think more before coding.

### Problem: Sunglasses

Write a program which receives an integer **n** (3 ≤ n ≤ 100) and prints sunglasses with a size of **5\*N x N** as found in the examples:

|Input|Output|Input|Output|
|---|---|---|---|
|3|<code>\*\*\*\*\*\*&nbsp;&nbsp;&nbsp;\*\*\*\*\*\*</code><br><code>\*////\*&#124;&#124;&#124;\*////\*</code><br><code>\*\*\*\*\*\*&nbsp;&nbsp;&nbsp;\*\*\*\*\*\*</code>|4|<code>\*\*\*\*\*\*\*\*&nbsp;&nbsp;&nbsp;&nbsp;\*\*\*\*\*\*\*\*</code><br><code>\*//////\*&#124;&#124;&#124;&#124;\*//////\*</code><br><code>\*//////\*&nbsp;&nbsp;&nbsp;&nbsp;\*//////\*</code><br><code>\*\*\*\*\*\*\*\*&nbsp;&nbsp;&nbsp;&nbsp;\*\*\*\*\*\*\*\*</code><br>|

|Input|Output|
|---|---|
|5|<code>\*\*\*\*\*\*\*\*\*\*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\*\*\*\*\*\*\*\*\*\*</code><br><code>\*////////\*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\*////////\*</code><br><code>\*////////\*&#124;&#124;&#124;&#124;&#124;\*////////\*</code><br><code>\*////////\*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\*////////\*</code><br><code>\*\*\*\*\*\*\*\*\*\*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\*\*\*\*\*\*\*\*\*\*</code><br>|

#### Hints and Guidelines

From the examples, we can see that the sunglasses can be divided into **three parts** – upper, middle, and lower. Below is part of the code with which the problem can be solved. When drawing the upper and lower rows we need to print **`2 * n`** asterisks, **`n`** whitespaces, and **`2 * n`** asterisks:

![](/assets/chapter-6-1-images/08.Sunglasses-01.png)


When drawing **the middle** part, we need to **check** if the row is **`(n-1) / 2 - 1`**, because in the examples we can see that in **this row** we need to print **vertical slashes** instead of whitespaces:

![](/assets/chapter-6-1-images/08.Sunglasses-02.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1055#7](https://judge.softuni.org/Contests/Practice/Index/1055#7).

### Problem: House

Write a program which receives a number **n** (2 ≤ **n** ≤ 100) and prints **a house** with size **N x N**, just as in the examples:

|Input|Output|Input|Output|Input|Output|
|---|---|---|---|---|---|
|2|<code>**</code><br><code>&#124;&#124;</code><br>|3|<code>-\*-</code><br><code>\*\*\*</code><br><code>&#124;\*&#124;</code>|4|<code>-\*\*-</code><br><code>\*\*\*\*</code><br><code>&#124;\*\*&#124;</code><br><code>&#124;\*\*&#124;</code>

|Input|Output|Input|Output|
|---|---|---|---|
|5|<code>--\*--</code><br><code>-\*\*\*-</code><br><code>\*\*\*\*\*</code><br><code>&#124;\*\*\*&#124;</code><br><code>&#124;\*\*\*&#124;</code>|8|<code>---\*\*---</code><br><code>--\*\*\*\*--</code><br><code>-\*\*\*\*\*\*-</code><br><code>\*\*\*\*\*\*\*\*</code><br><code>&#124;\*\*\*\*\*\*&#124;</code><br><code>&#124;\*\*\*\*\*\*&#124;</code><br><code>&#124;\*\*\*\*\*\*&#124;</code><br><code>&#124;\*\*\*\*\*\*&#124;</code><br>|


#### Hints and Guidelines

We understand from the description of the problem that the house has size **`n` x `n`**. What we see from the example input and output is that:

* The house is divided into two parts: **roof and base**.

![](/assets/chapter-6-1-images/09.House-01.png)

* Когато **`n`** е четно число, върхът на къщичката е тъп.
* Когато **`n`** е нечетно число, **покривът** е с остър връх и с един ред по-голям от **основата**.

##### Покрив
* Съставен е от **звезди** и **тирета**.
* В най-високата си част има една или две звезди, спрямо това дали **n** e четно или нечетно, както и тирета.
* В най-ниската си част има много звезди и малко или никакви тирета.
* С всеки един ред по-надолу **звездите** се увеличават с 2, а **тиретата** намаляват също с 2.

##### Основа
* Дълга е **`n`** на брой реда.
* Съставена е от **звезди** и **вертикални черти**.
* Редовете са съставени от 2 **вертикални черти** - по една в началото и в края на реда, както и **звезди** между чертите с дължина на низа **`n - 2`**.  

Прочитаме входното число **`n`** от конзолата и записваме стойността му в променлива:  

![](/assets/chapter-6-1-images/09.House-02.png)

<table><tr><td><img src="/assets/alert-icon.png" style="max-width:50px" /></td>
<td><b>Много е важно да проверяваме дали са валидни входните данни!</b> В тези задачи не е проблем директно да обръщаме прочетеният вход от конзолата в тип <b><code>int</code></b>, защото изрично е казано, че ще получаваме валидни целочислени числа. Ако обаче правим по-сериозни приложения, е добра практика да проверяваме данните. Какво ще стане, ако вместо число потребителят въведе например буквата "А"?</td>
</tr></table>

За да начертаем **покрива**, записваме колко ще е началният брой **звезди** в променлива **`stars`**:
* Ако **`n`** е **нечетно** число, ще е 1 брой.
* Ако **`n`** е **четно**, ще са 2 броя.

![](/assets/chapter-6-1-images/09.House-03.png)

Изчисляваме дължината на **покрива**. Тя е равна на половината от **`n`**. Резултата записваме в променливата **`roof_length`**:

![](/assets/chapter-6-1-images/09.House-04.png)

**Забележка:** За да използваме **`math.ceil()`**, която закръгля към по-голямото цяло число, без значение от дробната част, е необходимо да въведем библиотеката **`math`**. Това става с командата **`import math`**. Препоръчително е да напишем **`import math`** (както и всички други import-и) още в началото на файла.

Важно е да съобразим, че когато **`n`** е нечетно число, дължината на покрива е по-голяма с един ред от тази на **основата**. 

В езика **Python**, когато два целочислени типа се делят и има остатък, то резултатът ще е число с остатък. Ако искаме да извършим чисто целочислено деление без остатък, е необходимо да използваме оператора **`//`**.

Пример:

```python
result1 = 3 / 2    # резултат 1.5
result2 = 3 // 2   # резултат 1
```

Ако искаме да закръглим резултата нагоре, трябва да използваме метода **`math.cail(…)`**:
**`result = math.ceil(3 / 2)`**.

След като сме изчислили дължината на покрива, завъртаме цикъл от 0 до **`roof_length`**. На всяко повторение ще:
* Изчисляваме броя **тирета**, които трябва да изрисуваме. Броят ще е равен на **`(n - stars) / 2`**. Записваме го в променлива **`padding`**.

![](/assets/chapter-6-1-images/09.House-05.png)

* Отпечатваме на конзолата: "**тирета**" (**`padding`** на брой пъти) + "**звезди**" (**`stars`** пъти) + "**тирета**" (**`padding`** пъти). 

![](/assets/chapter-6-1-images/09.House-06.png)

* Преди да завърши въртенето на цикъла увеличаваме **`stars`** (броя на **звездите**) с 2.

![](/assets/chapter-6-1-images/09.House-07.png)

След като сме приключили с покрива, е време за **основата**. Тя е по-лесна за печатане:
* Започваме с цикъл от 0 до **`n`** (изключено).
* Отпечатваме на конзолата: **`|`** + **`*`** (**`n - 2`** на брой пъти) + **`|`**.

![](/assets/chapter-6-1-images/09.House-08.png)

Ако всичко сме написали както трябва, задачата ни е решена.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1055#8](https://judge.softuni.org/Contests/Practice/Index/1055#8).

### Пример: диамант

Да се напише програма, която приема цяло число **n** (1 ≤ **n** ≤ 100) и печата диамант с размер **N**, като в следните примери:

|Вход|Изход|Вход|Изход|Вход|Изход|
|---|---|---|---|---|---|
|1|<code>\*</code><br>|2|<code>\*\*</code>|3|<code>-\*-</code><br><code>\*-\*</code><br><code>-\*-</code>|

|Вход|Изход|Вход|Изход|Вход|Изход|
|---|---|---|---|---|---|
|4|<code>-\*\*-</code><br><code>\*--\*</code><br><code>-\*\*-</code>|5|<code>--\*--</code><br><code>-\*-\*-</code><br><code>\*---\*</code><br><code>-\*-\*-</code><br><code>--\*--</code><br>|6|<code>--\*\*--</code><br><code>-\*--\*-</code><br><code>\*----\*</code><br><code>-\*--\*-</code><br><code>--\*\*--</code><br>|

|Вход|Изход|Вход|Изход|Вход|Изход|
|---|---|---|---|---|---|
|7|<code>---\*---</code><br><code>--\*-\*--</code><br><code>-\*---\*-</code><br><code>\*-----\*</code><br><code>-\*---\*-</code><br><code>--\*-\*--</code><br><code>---\*---</code><br>|8|<code>---\*\*---</code><br><code>--\*--\*--</code><br><code>-\*----\*-</code><br><code>\*------\*</code><br><code>-\*----\*-</code><br><code>--\*--\*--</code><br><code>---\*\*---</code><br>|9|<code>----\*----</code><br><code>---\*-\*---</code><br><code>--\*---\*--</code><br><code>-\*-----\*-</code><br><code>\*-------\*</code><br><code>-\*-----\*-</code><br><code>--\*---\*--</code><br><code>---\*-\*---</code><br><code>----\*----</code>|

#### Насоки и подсказки

Това, което знаем от условието на задачата, е че диамантът е с размер **`n` x `n`**. От примерните вход и изход можем да си направим извода, че всички редове съдържат точно по **`n`** символа и всички редове, с изключение на горните върхове, имат по **2 звезди**. Можем мислено да разделим диаманта на 2 части:
* **Горна** част. Тя започва от горния връх до средата.
* **Долна** част. Тя започва от реда след средата до най-долния връх включително.

##### Горна част

* Ако **`n`** е **нечетно**, то тя започва с **1 звезда**.
* Ако **`n`** е **четно**, то тя започва с **2 звезди**.
* С всеки ред надолу звездите се отдалечават една от друга.
* Пространството между, преди и след **звездите** е запълнено с **тирета**.

##### Долна част

* С всеки ред надолу звездите се приближават една към друга. Това означава, че пространството (**тиретата**) между тях намалява, а пространството (**тиретата**) отляво и отдясно се увеличава.
* В най-долната си част е с 1 или 2 **звезди**, спрямо това дали **`n`** е четно или не.

##### Горна и долна част на диаманта

* На всеки ред звездите са заобиколени от външни **тирета**, с изключение на средния ред.
* На всеки ред има пространство между двете **звезди**, с изключение на първия и последния ред (понякога **звездата е 1**).

Прочитаме стойността на **`n`** от конзолата, като я конвертираме до тип **`int`**:

![](/assets/chapter-6-1-images/10.Diamond-01.png)

Започваме да печатаме на конзолата горната част на диаманта. Първото нещо, което трябва да направим, е да изчислим началната стойност на външната бройка **тирета `left_right`** (тиретата от външната част на **звездите**). Тя е равна на **`(n - 1) / 2`**, закръглено надолу:

![](/assets/chapter-6-1-images/10.Diamond-02.png)

След като сме изчислили **`left_right`**, започваме да чертаем **горната част** на диаманта. Може да започнем, като завъртим **цикъл** от **`0`** до **`(n + 1) // 2 `** (т.е. закръглено надолу).  

При всяко завъртане на цикъла трябва да се изпълнят следните стъпки:

* Печатане на левите **тирета** на конзолата (с дължина **`left_right`**) и веднага след тях първата **звезда**.

![](/assets/chapter-6-1-images/10.Diamond-03.png)

* Изчисляване на разстоянието между двете **звезди**. Може да го направим като извадим от **`n`** дължината на външните **тирета**, както и числото 2 (бройката на **звездите**, т.е. очертанията на диаманта). Резултата от тази разлика записваме в променлива **`mid`**.

![](/assets/chapter-6-1-images/10.Diamond-04.png)

* Ако стойността на **`mid`** е по-малка от 0, то тогава знаем, че на този ред трябва да има 1 звезда. Ако е по-голяма или равно на 0, то тогава трябва да начертаем **тирета** с дължина **`mid`** и една **звезда** след тях.
* Печатаме на конзолата десните външни **тирета** с дължина също **`left_right`**. 

![](/assets/chapter-6-1-images/10.Diamond-05.png)

* В края на цикъла намаляваме стойността на **`left_right`** с 1 (**звездите** се отдалечават).

Готови сме с горната част.

Чертането на долната част е доста подобно на това на горната част. Разликата е, че вместо да намаляме стойността на **`left_right`** с 1 към края на цикъла, ще я увеличаваме с 1 в началото на цикъла. Също така **цикълът ще се върти от 0 до `(n - 1) // 2`**:

![](/assets/chapter-6-1-images/10.Diamond-06.png)

<table><tr><td><img src="/assets/alert-icon.png" style="max-width:50px" /></td>
<td><b>Повторението на код се смята за лоша практика</b>, защото кодът става доста труден за поддръжка. Нека си представим, че имаме парче код (напр. логиката за чертането на ред от диаманта) на още няколко места и решаваме да направим промяна. За целта би било необходимо да минем през всичките места и да направим промените. А сега нека си представим, че трябва да използвате код не 1, 2 или 3 пъти, а десетки пъти. Начин за справяне с този проблем е като се използват <b>функции</b>. Можете да потърсите допълнителна информация за тях в Интернет или да прегледате <a href="/chapter-10-methods.md">Глава 10. Функции</a>.</td>
</tr></table>

Ако сме написали всичко коректно, задачата ни е решена.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1055#9](https://judge.softuni.org/Contests/Practice/Index/1055#9).


## Какво научихме от тази глава?

Запознахме се с един от начините за създаване на низове:

```python
print_me = '*' * 5
```

Научихме се да чертаем фигури с вложени **`for`** цикли:

```python
for row in range(5):
    print('*', end='')

    for col in range(4):
        print(' *', end='')

    print()
```

## Упражнения: Чертане на фигурки в уеб среда

Сега, след като свикнахме с **вложените цикли** и как да ги използваме, за да чертаем фигурки на конзолата, можем да се захванем с нещо още по-интересно: да видим как циклите могат да се използват за **чертане в уеб среда**. Ще направим уеб приложение, което визуализира числов рейтинг (число от 0 до 100) със звездички. Такава визуализация се среща често в сайтове за електронна търговия, ревюта на продукти, оценки на събития, рейтинг на приложения и други.

Не се притеснявайте, ако не разберете целия код, как точно е направен и как точно работи проектът. Нормално е, сега се учим да пишем код, не сме стигнали до технологиите за уеб разработка. Ако имате трудности да си напишете проекта, следвайки описаните стъпки, питайте в СофтУни форума: https://softuni.bg/forum.

### Задача: рейтинги – визуализация в уеб среда

Да се разработи уеб приложение за визуализация на рейтинг (число от 0 до 100). Чертаят се от 1 до 10 звездички (с половинки). Звездичките да се генерират с **`for`** цикъл. 

![](assets/chapter-6-1-images/11.Ratings-01.png)

#### Насоки и подсказки

Започваме като създаваме нов проект в **PyCharm** от [**File**] -> [**New Project**] (или от началния прозорец):

![](assets/chapter-6-1-images/11.Ratings-02.png)

Даваме смислено име на проекта, например "Ratings". Избираме тип на текущия **Python интерпретатор**. Нека да е този по подразбиране:

![](assets/chapter-6-1-images/11.Ratings-03.png)

Ще използваме отново библиотеката Flask, която служи за създаване на уеб приложения. Преди да започнем да пишем код, трябва да инсталираме Flask. Нека си припомним как ставаше това. Отиваме в настройките на PyCharm [**File**] -> [**Settings**] -> [**Project: Ratings**] -> [**Project Interpreter**]. Там, натискаме бутона **`+`**:

![](assets/chapter-6-1-images/11.Ratings-04.png)

Търсим **Flask** в прозореца, който излиза и натискаме бутона [**Install Package**]:

![](assets/chapter-6-1-images/11.Ratings-05.png)

Сега добавяме **структурата** на проекта (файловете със заданието за този проект могат да бъдат свалени от [тук](https://github.com/SoftUni/Programming-Basics-Book-Python-BG/tree/chapter-06-nested-loops/assets/chapter-6-1-assets)). Копираме ги от Windows Explorer и ги поставяме в папката на проекта **Ratings** с Copy/Paste:

![](assets/chapter-6-1-images/11.Ratings-06.png)

За да заработи всичко, трябва да допишем кода. Първо отиваме във файла **index.html** (от папка templates) и търсим **TODO** секциите. На тяхно място въвеждаме следния код:

![](assets/chapter-6-1-images/11.Ratings-07.png)

Горният код създава уеб форма **`<form>`** с едно поле **`"rating"`** за въвеждане на число в интервала [**0 … 100**] и бутон [**Rate**] за изпращане на данните от формата към сървъра. След което, рисува с три отделни **for** цикъла съответния брой звездички - запълнени, полупразни и празни.

Действието, което ще обработи данните, се казва **`/DrawRatings`**, което означава функция **`draw_ratings()`** във файла **`app.py`**:

![](assets/chapter-6-1-images/11.Ratings-08.png)

Кодът от функцията **`draw_ratings()`** взима въведеното число **`rating`** от формата и го подава на функцията **`calc_rating(…)`**. Функцията **`calc_rating(…)`** извършва пресмятания и изчислява броя **пълни звездички**, броя **празни звездички** и броя **половинки звездички**, след което зарежда отново страницата, но вече с подадени нови стойности на променливите за звездичките. Имплементираме я по следния начин:

![](assets/chapter-6-1-images/11.Ratings-09.png)

Стартираме проекта с [**Ctrl+Shift+F10**] (или с [**Десен бутон**] -> [**Run 'app'**]) и изчакваме да се зареди:

![](assets/chapter-6-1-images/11.Ratings-10.png)

Отиваме на посочения адрес и се наслаждаваме на готовия проект:

![](assets/chapter-6-1-images/11.Ratings-11.png)

Ако имате проблеми с примерния проект по-горе, може да задавате въпроси във **форума на СофтУни**: [https://softuni.bg/forum](https://softuni.bg/forum).
