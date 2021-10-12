# Chapter 5.2 Iterations (loops) - exam problems

In the previous chapter we learned how to run a command block **more than once**. That's why we implemented **`for` loop** and covered some of its main applications. Our task in the current chapter is to hone our knowledge by solving a couple of more complex problems with loops, which appear in exams.  For some of them we’ll show detailed solved examples, while for others there’ll be tips only. Before we begin, we’ll recall the **`for` loop** construction:

![](/assets/chapter-5-2-images/00.For-construction-01.png)

**`for` loops** consist of:
 * **Initialization block**, where the variable-counter (**`i`**) is declared, and with the help of the **`range(…)`** function built into Python, we define what its starting and ending value will be.
 * **Updating the counter** – we implement it as a third parameter in the **`range(…)`** function, and it shows with how many steps the variable-counter should be updated.
 * **Loop body** - it has a random block full of source code.

## Exam problems

Let’s solve a couple of problems with loops in SoftUni’s exams.

## Problem: histogram
	
We’re given **n-count integers** in range [**1 … 1000**]. A percent of them, **p1**, are under 200, __p2__ percent are between 200 and 399, **p3** percent are between 400 and 599, **p4** percent are between 600 and 799, and the remaining **p5** percent begin at 800. Write a program that calculates and prints the percentages **p1**, **p2**, **p3**, **p4** and **p5**.

**Example**: we have n = **20** integers: 53, 7, 56, 180, 450, 920, 12, 7, 150, 250, 680, 2, 600, 200, 800, 799, 199, 46, 128, 65. We get the following distribution and visualization:
                          
| **Group**   | **Numbers**                                     |**Number count**| **Percentage**                  |
|-------------|-------------------------------------------------|:---------------|---------------------------------|
| < 200       | 53, 7, 56, 180, 12, 7, 150, 2, 199, 46, 128, 65 | 12             | p1 = 12 / 20 * 100 = 60.00%     |
| 200 … 399   | 250, 200                                        | 2              | p2 = 2 / 20 * 100 = 10.00%      |
| 400 … 599   | 450                                             | 1              | p3 = 1 / 20 * 100 = 5.00%       |
| 600 … 799   | 680, 600, 799                                   | 3              | p4 = 3 / 20 * 100 = 15.00%      |
| ≥ 800       | 920, 800                                        | 2              | p5 = 2 / 20 * 100 = 10.00%      |


### Input

On the first line of the input is an integer **n** ( 1 <= **n** <= 1000), which stands for the number of lines with numbers, which will be given to us. On the next **n lines** there is **one integer** in range [**1 … 1000**] – the numbers that the histogram will be based on.

### Output

In the console, print a histogram of **5 lines**, each of them containing a number between 0% and 100%, formatted with two-digit precision after the decimal point(for example, 25.00%, 66.67%, 57.14%).

### Example input & output

<table>
<thead>
<tr>
<th align="left"><strong>Input</strong></th>
<th align="left"><strong>Output</strong></th>
<th align="left"><strong>Input</strong></th>
<th align="left"><strong>Output</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>3</strong><br>1<br>2<br>999</td>
<td valign="top">66.67%<br>0.00%<br>0.00%<br>0.00%<br>33.33%</td>
<td valign="top"><strong>4</strong><br>53<br>7<br>56<br>999</td>
<td valign="top">75.00%<br>0.00%<br>0.00%<br>0.00%<br>25.00%</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th align="left"><strong>Input</strong></th>
<th align="left"><strong>Output</strong></th>
<th align="left"><strong>Input</strong></th>
<th align="left"><strong>Output</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>7</strong><br>800<br>801<br>250<br>199<br>399<br>599<br>799</td>
<td valign="top">14.29%<br>28.57%<br>14.29%<br>14.29%<br>28.57%</td>
<td valign="top"><strong>9</strong><br>367<br>99<br>200<br>799<br>999<br>333<br>555<br>111<br>9</td>
<td valign="top">33.33%<br>33.33%<br>11.11%<br>11.11%<br>11.11%</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th align="left"><strong>Input</strong></th>
<th align="left"><strong>Output</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>14</strong><br>53<br>7<br>56<br>180<br>450<br>920<br>12<br>7<br>150<br>250<br>680<br>2<br>600<br>200</td>
<td valign="top">57.14%<br>14.29%<br>7.14%<br>14.29%<br>7.14%</td>
</tr>
</tbody>
</table>

### Tips and advice

The program that solves this problem can be divided theoretically into three parts:

  * **Reading the input data** – in the current task, this means reading the integer **n**, followed by a **count of n integers**, each on a new line.
  * **Processing the input data** – in this case, this means dividing the numbers in groups and calculating the division percentage by those groups.
  * **Outputting the final result** – printing the histogram in the console, in the given format.

#### Reading the input data
  
Before we transition to the real reading of the input, we have to **declare our variables**, in which the data will be stored:

![](/assets/chapter-5-2-images/01.Histogram-01.png)

We declare variables **`p1_percentage`**, **`p2_percentage`**, etc., in which we’ll store the percentages, as well as **`cnt_p1`**, **`cnt_p2`**, etc., in which we’ll keep the count of numbers for the respective group.

After we’ve declared the needed variables, we can move on to reading the number **`n`** from the console:

![](/assets/chapter-5-2-images/01.Histogram-02.png)

#### Processing the input data
  
In order to read and assign each number to its respective group, we’ll use a **`for`-loop** from **0** to **`n`** (the count of the numbers). Each iteration of the cycle will read and assign **only one number** (**`current_number`**) to it’s respective group. So that we can decide if a selected number belongs to a group, **we check its range**. If it passes, we increase the count of this group’s numbers(**`cnt_p1`**, **`cnt_p2`**, etc.) by 1:

![](/assets/chapter-5-2-images/01.Histogram-03.png)

After we’ve found out how many numbers there are in each group, we can move on to calculating the percentages, which is also the main part of the problem. We’ll use the following formula:

<p align="center"><strong>(Group percentage) = (Group number count) * 100 / (Count of all numbers)</strong></p>

It doesn’t matter whether we’ll divide by **100** (an **`integer`** type), or **100.0**(a **`float`** type), since the **division** will take place and the result will be saved to the variable. Example: **5 / 2 = 2.5**, and **5 / 2.0 = 2.5**. In **`Python 3`**, there’s no difference whether we’ll be dividing by an integer or a real number - if the result is a real number itself, then it will be saved in the variable as a floating-point number. But in **`Python 2.7`** we have to convert the numbers to a **`float`** type, in order to get the correct result – a real number. Having that in mind, the first variable’s formula will look like this:

![](/assets/chapter-5-2-images/01.Histogram-04.png)

To better understand what’s happening, let’s look at the following example:

|Input|Output|
|--------|---------|
|**3**<br>1<br>2<br>999|66.67%<br>0.00%<br>0.00%<br>0.00%<br>33.33%|

In this case, **`n = 3`**. 
The cycle consists of:
   -   	**`i = 0`** - we read the number 1, which is lower than 200 and belongs to the first group, thus increasing the counter of the number (**`cnt_p1`**) by 1.
   -   	**`i = 1`** – we read the number 2, which, again, belongs to the first group and we increase the group’s counter(**`cnt_p1`**) by 1.
   -   	**`i = 2`** – we read the number 999, which belongs to the last group(**`p5`**), because it’s bigger than 800, and we increase it’s group counter (**`cnt_p5`**) by 1.
   
After reading the numbers, we have two of them in the first group, and we have only one in the last group. There are **no numbers** in the other groups. After we apply the aforementioned formula, we calculate the percentage of each group. It doesn’t matter whether we multiply by **100** or **100.0** – we’ll get the same result: the **first** group has 66.67%, and the **last** group – 33.33%. We have to mention that this is valid only for **`Python 3`**.

#### Printing the final result
  
The last step is to print the calculated results. In the problem’s description it’s said that the percentages have to be with **2-digit precision after the decimal point**. To achieve this, we have to write **`.2f`** after the placeholder.

![](/assets/chapter-5-2-images/01.Histogram-05.png)

### Testing in the Judge system

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1054#0](https://judge.softuni.org/Contests/Practice/Index/1054#0).


## Problem: Smart Lily

Lily is **N years old**. Each **birthday** she receives a gift. For her **odd** birthdays (1, 3, 5, …, n) she receives **toys**, and for each **even** birthday (2, 4, 6, …, n) she receives **money**. For her **second birthday** she receives **10.00 USD**, and **the sum increases by 10 USD with each following even birthday** (2 -> 10, 4 -> 20, 6 -> 30, etc.). Lily has secretly been saving the money for years. **Her brother**, in the years when she **receives money**, **takes 1.00 USD**. Lily **sold the toys** received with the years, **each for P USD** and added the sum to the saved money. With them she wants **to buy a washing machine for X USD**. Write a program that calculates **how much money she has saved** and whether **it's enough to buy a washing machine**.

### Input

**3 numbers** are read from the console, each on a new line:

   - **Lily's age** – **integer** in range [**1 … 77**].
   - **The price of the washing machine** – a number in range [**1.00 … 10 000.00**].
   - **The price of a single toy** – **integer** in range [**0 … 40**].

### Изходни данни

Да се отпечата на конзолата един ред:

  * Ако парите на Лили са достатъчни:
    * "**Yes! {N}**" – където **N** е остатъка пари след покупката
  * Ако парите не са достатъчни:
    * "**No! {M}**" – където **M** е сумата, която не достига
  * Числата **N** и **M** трябва да са **форматирани до втория знак след десетичната точка**.

### Output

Print a single line in the console:

  * If Lily's money are enough:
    * "**Yes! {N}**" – where **N** are the remaining money after the purchase
  * If they're not:
    * "**No! {M}**" – where **M** are the missing money
  * The numbers **N** and **M** should be **formatted with 2-digit precision after the decimal point**.

### Example input & output

<table>
<thead>
<tr>
<th align="left"><strong>Input</strong></th>
<th align="left"><strong>Output</strong></th>
<th align="left"><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">10<br>170.00<br>6</td>
<td valign="top">Yes! 5.00</td>
<td valign="top"><p><strong>On the first birthday</strong> she receives <strong>a toy</strong>; <strong>Second</strong> -> <strong>10 USD</strong>; 3rd -> toy; <strong>4th</strong>  -> 10 + 10 = <strong>20 USD</strong>; 5th -> toy; <strong>6th</strong> -> 20 + 10 = <strong>30 USD</strong>; 7th -> toy; <strong>8th</strong> -> 30 + 10 = <strong>40 USD</strong>; 9th -> toy; <strong>10th</strong> -> 40 + 10 = <strong>50 USD</strong><br>
<strong>She has saved</strong> -> 10 + 20 + 30 + 40 + 50 = <strong>150 USD</strong>. She has sold <strong>5 toys by 6 USD = 30 USD</strong>.<br>
<strong>Her brother took 1 USD for 5 years = 5 USD</strong>. <strong>Remaining money</strong> -> 150 + 30 – 5 = <strong>175 USD</strong>.
<strong>175 &gt;= 170</strong> (washing machine's price) <strong>She has succeeded</strong> buying it and there <strong>remain</strong> 175-170 = <strong>5 USD</strong>.
</p></td>
</tr>
<tr>
<td valign="top">21<br>1570.98<br>3</td>
<td valign="top">No! 997.98</td>
<td valign="top"><p><strong>She has saved 550 USD</strong>. <strong>She's sold</strong> <strong>11 toys</strong> by <strong>3 USD each</strong> = <strong>33 USD</strong>. Her brother <strong>has taken 1 USD for 10 years</strong> = <strong>10 USD</strong>. <strong>There remain</strong> 550 + 33 – 10 = <strong>573 USD.</strong> <br>
<strong>573 &lt; 1570.98</strong> – <strong>She's failed</strong> buying a washing machine. <strong>She needs</strong> 1570.98–573 = <strong>997.98 USD more.</strong></p></td>
</tr>
</tbody>
</table>    

### Tips and advice

Solving this problem, like the previous one, again can be divided in three parts – **reading** the input data, **processing** it and **outputting** a result.

As we already know, in most of the scripting languages, in Python as well, we don't bother defining the types of the variables that we declare. The interpretator decides on its own what it'll be. For Lily's (**`age`**) and a single toy's price, (**`present_price`**), in the problem's description it's said that they'll be **integers**. That's why we'll use **the built-in function `int()`** to convert the read value from string to integer. When the **`input()`** function is used, the input's value in the console is always (**`string`**), that's why if a conversion to another type is needed, we can use **the built-in functions of Python** for this task. For the washing machine's price, (**`price_of_washing_machine`**), we know that it's a **fractional number and we choose the `float` type**. In the code below **we declare** and **initialize** (assign a value) to the variables:

![](/assets/chapter-5-2-images/02.Smart-lilly-01.png)

За да решим задачата, ще се нуждаем от няколко помощни променливи – за **броя на играчките** (**`number_of_toys`**), за **спестените пари** (**`saved_money`**) и за **парите, получени на всеки рожден ден** (**`money_for_birthday`**). Като присвояваме на **`money_for_birthday`** първоначална стойност 10, тъй като по условие е дадено, че първата сума, която Лили получава, е 10 лв:

![](/assets/chapter-5-2-images/02.Smart-lilly-02.png)
 
С **`for` цикъл** преминаваме през всеки рожден ден на Лили. Когато водещата променлива е **четно число**, това означава, че Лили е **получила пари** и съответно прибавяме тези пари към общите ѝ спестявания. Едновременно с това **изваждаме по 1 лев** - парите, които брат ѝ взема. След това **увеличаваме** стойността на променливата **`money_for_birthday`**, т.е. увеличаваме с 10 сумата, която тя ще получи на следващия си рожден ден. Обратно, когато водещата променлива е **нечетно число**, увеличаваме броя на **играчките**. Проверката за четност осъществяваме чрез **деление с остатък** (**`%`**) **на 2** – когато остатъкът е 0, числото е четно, а при остатък 1 - нечетно:
 
![](/assets/chapter-5-2-images/02.Smart-lilly-03.png)
 
Към спестяванията на Лили прибавяме и парите от продадените играчки:

![](/assets/chapter-5-2-images/02.Smart-lilly-04.png)

Накрая остава да отпечатаме получените резултати, като се съобразим с форматирането, указано в условието, т.е. сумата трябва да е **закръглена до две цифри след десетичния знак**:

![](/assets/chapter-5-2-images/02.Smart-lilly-05.png)

В някои програмни езици съществува конструкция, като **условния оператор (`?:`)** (наричан още тернарен оператор), тъй като записът е по-кратък. В Python синтаксисът му е следният: **`операнд1 if операнд2 else операнд3`**. Вторият операнд е нашето условие и трябва да е от **булев тип** (т.е. да връща **`true/false`**). Ако **`операнд2`** върне стойност **`true`**, то ще се изпълни **`операнд1`**, а ако върне **`false`** – **`операнд3`**. В нашия случай проверяваме дали **събраните пари** от Лили стигат за една пералня. Ако те са повече или равни на цената на пералнята, то проверката **`saved_money >= price_of_washing_machine`** ще върне **`true`** и ще се отпечата "**Yes! …**", а ако е по-малко – резултатът ще е **`false`** и ще се отпечата "**No! …**". Разбира се, вместо условния оператор, можем да използваме и обикновени **`if`** проверки.

Повече за условния оператор: [https://book.pythontips.com/en/latest/ternary_operators.html](https://book.pythontips.com/en/latest/ternary_operators.html).

### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1054#1](https://judge.softuni.org/Contests/Practice/Index/1054#1).


## Задача: завръщане в миналото

Иванчо е на **18 години** и получава наследство, което се състои от **X сума пари** и **машина на времето**. Той решава **да се върне до 1800 година**, но не знае **дали парите** ще **са достатъчни**, за да живее без да работи. Напишете **програма, която пресмята** дали Иванчо **ще има достатъчно пари**, за да не се налага да работи **до дадена година включително**. Като приемем, че **за всяка четна** (1800, 1802 и т.н.) година ще **харчи 12 000 долара**. За **всяка нечетна** (1801, 1803  и т.н.) ще харчи **12 000 + 50 * [годините, които е навършил през дадената година]**.

### Входни данни

Входът се чете от конзолата и **съдържа точно 2 реда**:

  * **Наследените пари** – реално число в интервала [**1.00 … 1 000 000.00**].
  * **Годината, до която трябва да живее (включително)** – цяло число в интервала [**1801 … 1900**].

### Изходни данни

Да се **отпечата** на конзолата **1 ред**. **Сумата** трябва да е **форматирана** до **два знака след десетичния знак**:
  * Ако **парите са достатъчно**:
    * "**Yes! He will live a carefree life and will have {N} dollars left.**" – където **N** са парите, които ще му останат.
  *	Ако **парите НЕ са достатъчно**:
    * "**He will need {М} dollars to survive.**" – където **M** е сумата, която **НЕ достига**.

### Примерен вход и изход

<table>
<thead>
<tr>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
<th align="left"><strong>Обяснения</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">50000<br>1802</td>
<td valign="top">Yes! He will live a carefree life and<br> will have 13050.00 dollars left.</td>
<td valign="top"><p>1800 &rarr; <strong>четна</strong><br> 
 	&nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; <strong>Харчи 12000</strong> долара <br>
  &nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; Остават 50000 – 12000 = <strong>38000</strong><br>
1801 &rarr; <strong>нечетна</strong> <br>
	&nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; <strong>Харчи</strong> 12000 + <strong>19*50</strong> = 12950 долара<br>
	&nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; <strong>Остават</strong> 38000 – 12950 = <strong>25050</strong><br>
1802 &rarr; <strong>четна</strong> <br>
	&nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; <strong>Харчи</strong> 12000 долара<br>
	&nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; <strong>Остават</strong> 25050 – 12000 = <strong>13050</strong></p></td>
</tr>
<tr>
<td valign="top">100000.15<br>1808</td>
<td valign="top">He will need 12399.85 dollars<br> to survive.</td>
<td valign="top"><p>1800 &rarr; <strong>четна</strong><br> 
  &nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; Остават 100000.15 – 12000 = <strong>88000.15</strong><br>
1801 &rarr; <strong>нечетна</strong> <br>
	&nbsp;	&nbsp;	&nbsp;	&nbsp;  &rarr; <strong>Остават</strong> 88000.15 – 12950 = <strong>75050.15</strong><br>
<strong>…</strong><br>
1808 &rarr; <strong>четна</strong> &rarr; -399.85 - 12000 = -12399.85<br>
<strong>12399.85 не достигат</strong>
</p></td>
</tr>
</tbody>
</table>    

### Насоки и подсказки

Методът за решаване на тази задача не е по-различен от тези на предходните, затова започваме **деклариране и инициализиране** на нужните променливи. В условието е казано, че годините на Иванчо са 18, ето защо при декларацията на променливата **`years`** ѝ задаваме начална стойност **18**. Другите променливи прочитаме от конзолата: 

![](/assets/chapter-5-2-images/03.Back-to-the-past-01.png)

С помощта на **`for` цикъл** ще обходим всички години. **Започваме от 1800** – годината, в която Иванчо се връща, и стигаме **до годината, до която той трябва да живее**. В цикъла проверяваме дали текущата година е **четна** или **нечетна**. Проверката за четност осъществяваме чрез **деление с остатък** (**`%`**) на 2. Ако годината е **четна**, изваждаме от наследството (**`heritage`**) **12000**, a ако е **нечетна**, изваждаме от наследството (**`heritage`**) **12000 + 50 * (годините на Иванчо)**:

![](/assets/chapter-5-2-images/03.Back-to-the-past-02.png)

Накрая остава да отпечатаме резултатите, като за целта правим **проверка дали наследството** (**`heritage`**) му е било достатъчно да живее без да работи или не. Ако наследството (**`heritage`**) е **положително число**, отпечатваме: "**`Yes! He will live a carefree life and will have {N} dollars left.`**", а ако е **отрицателно число**: "**`He will need {М} dollars to survive.`**". Не забравяме да форматираме сумата до два знака след десетичната точка.

**Hint**: Обмислете използването на функцията **`abs(…)`** при отпечатване на изхода, когато наследството е недостатъчно.

### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1054#2](https://judge.softuni.org/Contests/Practice/Index/1054#2).


## Задача: болница

За даден период от време, всеки ден в болницата пристигат пациенти за преглед. Тя разполага **първоначално** със **7 лекари**. Всеки лекар може да преглежда **само по един пациент на ден**, но понякога има недостиг на лекари, затова **останалите пациенти се изпращат в други болници**. **Всеки трети ден** болницата прави изчисления и **ако броят на непрегледаните пациенти е по-голям от броя на прегледаните, се назначава още един лекар**. Като назначаването става преди да започне приемът на пациенти за деня.

Напишете програма, която изчислява **за дадения период броя на прегледаните и непрегледаните пациенти**.

### Входни данни

Входът се чете от **конзолата** и съдържа:
  * На първия ред – **периода**, за който трябва да направите изчисления. **Цяло число** в интервала [**1 … 1000**].
  * На следващите редове (равни на броя на дните) – **броя пациенти**, които пристигат за преглед за **текущия ден**. Цяло число в интервала [**0 … 10 000**].

### Изходни данни

Да се **отпечатат** на конзолата **2 реда**:

* На **първия ред**: "**Treated patients: {брой прегледани пациенти}.**"
* На **втория ред**: "**Untreated patients: {брой непрегледани пациенти}.**"

### Примерен вход и изход

<table>
<thead>
<tr>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
<th align="left"><strong>Обяснения</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">4<br>7<br>27<br>9<br>1</td>
<td valign="top">Treated patients: 23.<br>Untreated patients: 21.</td>
<td valign="top"><p><strong>1 ден</strong>: 7 прегледани и 0 непрегледани пациента за деня<br>
<strong>2 ден</strong>: 7 прегледани и 20 непрегледани пациента за деня<br>
<strong>3 ден</strong>: До момента прегледаните пациенти са общо 14,<br> а непрегледаните – 20 –> Назначава се нов лекар <br>–>
8 прегледани и 1 непрегледан пациент за деня<br>
<strong>4 ден</strong>: 1 прегледан и 0 непрегледани пациента за деня<br>
<strong>Общо: 23 прегледани и 21 непрегледани пациенти.</strong></p></td>
</tr>
</tbody>
</table>    

<table>
<thead>
<tr>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">6<br>25<br>25<br>25<br>25<br>25<br>2</td>
<td valign="top">Treated patients: 40.<br>Untreated patients: 87.</td>
</tr>
<tr>
<td valign="top">3<br>7<br>7<br>7</td>
<td valign="top">Treated patients: 21.<br>Untreated patients: 0.</td>
</tr>
</tbody>
</table>    

### Насоки и подсказки

Отново започваме, като **декларираме и инициализираме** нужните променливи. Периодът, за който трябва да направим изчисленията, прочитаме от конзолата и запазваме в променливата **`period`**. Ще се нуждаем и от няколко помощни променливи: броя на излекуваните пациенти (**`treated_patients`**), броя на неизлекуваните пациенти (**`untreated_patients`**) и броя на докторите (**`count_of_doctors`**), който първоначално е 7: 

![](/assets/chapter-5-2-images/04.Hospital-01.png)

С помощта на **`for` цикъл** обхождаме всички дни в дадения период (**`period`**). За всеки ден прочитаме от конзолата броя на пациентите (**`current_patients`**). Увеличаването на докторите по условие може да стане **всеки трети ден**, **НО** само ако броят на непрегледаните пациенти е **по-голям** от броя на прегледаните. За тази цел проверяваме дали денят е трети – чрез аритметичния оператор за деление с остатък (**`%`**): **`day % 3 == 0`**.

Например:
 * Ако денят е **трети**, остатъкът от делението на **3** ще бъде **0** (**`3 % 3 = 0`**) и проверката **`day % 3 == 0`** ще върне **`true`**.
 * Ако денят е **втори**, остатъкът от делението на **3** ще бъде **2** (**`2 % 3 = 2`**) и проверката ще върне **`false`**.
 * Ако денят е **четвърти**, остатъкът от делението ще бъде **1** (**`4 % 3 = 1`**) и проверката отново ще върне **`false`**.

Ако проверката **`day % 3 == 0`** върне **`true`**, ще се провери дали и броят на неизлекуваните пациенти е по-голям от този на излекуваните: **`untreated_patients > treated_patients`**. Ако резултатът отново е **`true`**, тогава ще се увеличи броят на лекарите (**`count_of_doctors`**).

След това проверяваме броя на пациентите за деня (**`current_patients`**) дали е по-голям от броя на докторите (**`count_of_doctors`**). Ако броят на пациентите е **по-голям**:
 - Увеличаваме стойността на променливата **`treated_patients`** с броя на докторите (**`count_of_doctors`**).
 - Увеличаваме стойността на променливата **`untreated_patients`** с броя на останалите пациенти, който изчисляваме, като от всички пациенти извадим броя на докторите (**`current_patients - count_of_doctors`**).
 
Ако броят на пациентите **не е по-голям**, увеличаваме само променливата **`treated_patients`** с броя на пациентите за деня (**`current_patients`**):

![](/assets/chapter-5-2-images/04.Hospital-02.png)

Накрая трябва само да отпечатаме броя на излекуваните и броя на неизлекуваните пациенти.

### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1054#3](https://judge.softuni.org/Contests/Practice/Index/1054#3).


## Задача: деление без остатък

Дадени са **n цели числа** в интервала [**1 … 1000**]. От тях някакъв **процент p1 се делят без остатък на 2**, **процент p2** се **делят без остатък на 3**, **процент p3** се **делят без остатък на 4**. Да се напише програма, която изчислява и отпечатва процентите p1, p2 и p3.
**Пример:** имаме **n = 10** числа: 680, 2, 600, 200, 800, 799, 199, 46, 128, 65. Получаваме следното разпределение и визуализация:
<table>
<thead>
<tr>
<th align="left"><strong>Деление без остатък на:</strong></th>
<th align="left"><strong>Числа</strong></th>
<th align="left"><strong>Брой</strong></th>
<th align="left"><strong>Процент</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">2</td>
<td valign="top">680, 2, 600, 200, 800, 46, 128</td>
<td valign="top">7</td>
<td valign="top">p1 = (7 / 10) * 100 = <strong>70.00%</strong></td>
</tr>
<tr>
<td valign="top">3</td>
<td valign="top">600</td>
<td valign="top">1</td>
<td valign="top">p2 = (1 / 10) * 100 = <strong>10.00%</strong></td>
</tr>
<tr>
<td valign="top">4</td>
<td valign="top">680, 600, 200, 800, 128</td>
<td valign="top">5</td>
<td valign="top">p3 = (5 / 10) * 100 = <strong>50.00%</strong></td>
</tr>
</tbody>
</table>   

### Входни данни

На първия ред от входа стои цялото число **n** (1 ≤ **n** ≤ 1000) – брой числа. На следващите **n реда** стои **по едно цяло число** в интервала [**1 … 1000**] – числата, които да бъдат проверени на колко се делят.

### Изходни данни

Да се отпечатат на конзолата **3 реда**, всеки от които съдържа процент между 0% и 100%, с точност две цифри след десетичния знак, например 25.00%, 66.67%, 57.14%.
 * На **първия ред** – процентът на числата, които **се делят на 2**.
 * На **втория ред** – процентът на числата, които **се делят на 3**.
 * На **третия ред** – процентът на числата, които **се делят на 4**.

### Примерен вход и изход

<table>
<thead>
<tr>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>10</strong><br>680<br>2<br>600<br>200<br>800<br>799<br>199<br>46<br>128<br>65</td>
<td valign="top">70.00%<br>10.00%<br>50.00%</td>
<td valign="top"><strong>3</strong><br>3<br>6<br>9</td>
<td valign="top">33.33%<br>100.00%<br>0.00%</td>
<td valign="top"><strong>1</strong><br>12</td>
<td valign="top">100.00%<br>100.00%<br>100.00%</td>
</tr>
</tbody>
</table>   

### Насоки и подсказки

За тази и следващата задача ще трябва сами да напишете програмния код, следвайки дадените напътствия.

Програмата, която решава текущия проблем, е аналогична на тази от задача **Хистограма**, която разгледахме по-горе. Затова можем да започнем с декларацията на нужните ни променливи. Примерни имена на променливи може да са: **`n`** – брой на числата (който трябва да прочетем от конзолата) и **`divisible_by_2`**, **`divisible_by_3`**, **`divisible_by_4`** – помощни променливи, пазещи броя на числата от съответната група.

За да прочетем и разпределим всяко число в съответната му група, ще трябва да завъртим **`for` цикъл** от **`0`** до **`n`** (броя на числата). Всяка итерация на цикъла трябва да прочита и разпределя **едно единствено число**. Различното тук е, че **едно число може да попадне в няколко групи едновременно**, затова трябва да направим **три отделни `if` проверки за всяко число** – съответно дали се дели на 2, 3 и 4 и да увеличим стойността на променливата, която пази броя на числата в съответната група. 

**Внимание**: **`if-elif`** конструкция в този случай няма да ни свърши работа, защото след като намери съвпадение се прекъсва по-нататъшното проверяване на условията.

Накрая трябва да отпечатате получените резултати, като спазвате посочения формат в условието.

### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1054#4](https://judge.softuni.org/Contests/Practice/Index/1054#4).


## Задача: логистика

Отговаряте за логистиката на различни товари. **В зависимост от теглото** на всеки товар е нужно **различно превозно средство** и струва **различна цена на тон**:

 * До **3 тона** – **микробус** (200 лева на тон).
 * От **над 3 и до 11 тона** – **камион** (175 лева на тон).
 * **Над 11 тона – влак** (120 лева на тон).

Вашата задача е да изчислите **средната цена на тон превозен товар**, както и **колко процента от товара** се превозват с **всяко превозно средство**.

### Входни данни

От конзолата се четат **поредица от числа**, всяко на отделен ред:
 * **Първи ред**: **брой на товарите** за превоз – **цяло число** в интервала [**1 … 1000**].
 * На всеки следващ ред се подава **тонажът на поредния товар** – **цяло число** в интервала [**1 … 1000**].

### Изходни данни

Да се отпечатат на конзолата **4 реда**, както следва:
 * **Ред #1** – **средната цена на тон превозен товар** (закръглена до втория знак след десетичната точка).
 * **Ред #2** – **процентът** товар, превозван с **микробус** (между 0.00% и 100.00%, закръглен до втория знак след десетичната точка).
 * **Ред #3** – **процентът** товар, превозвани с **камион** (между 0.00% и 100.00%).
 * **Ред #4** – **процентът** товар, превозвани с **влак** (между 0.00% и 100.00%).
 
### Примерен вход и изход

<table>
<thead>
<tr>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
<th align="left"><strong>Обяснения</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">4<br>1<br>5<br>16<br>3</td>
<td valign="top">143.80<br>16.00%<br>20.00%<br>64.00%</td>
<td valign="top">
С <b>микробус</b> се превозват два от товарите <b>1</b> + <b>3</b>, общо <b>4</b> тона.<br>
С <b>камион</b> се превозва един от товарите: <b>5</b> тона.<br>
С <b>влак</b> се превозва един от товарите: <b>16</b> тона.<br>
<b>Сумата</b> от всички товари е: 1 + 5 + 16 + 3 = <b>25</b> тона.<br>
Процент товар <b>с микробус</b>: 4/25*100 = <b>16.00%</b><br>
Процент товар <b>с камион</b>: 5/25*100 = <b>20.00%</b><br>
Процент товар <b>с влак</b>: 16/25*100 = <b>64.00%</b><br>
<b>Средна цена</b> на тон превозен товар: (4 * 200 + 5 * 175 + 16 * 120) / 25 = <b>143.80</b>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
<th align="left"><strong>Вход</strong></th>
<th align="left"><strong>Изход</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top">5<br>2<br>10<br>20<br>1<br>7</td>
<td valign="top">149.38<br>7.50%<br>42.50%<br>50.00%</td>
<td valign="top">4<br>53<br>7<br>56<br>999</td>
<td valign="top">120.35<br>0.00%<br>0.63%<br>99.37%</td>
</tr>
</tbody>
</table>

### Насоки и подсказки

Първо **ще прочетем теглото на всеки товар** и ще **сумираме** колко тона се превозват съответно с **микробус**, **камион** и **влак** и ще изчислим и **общите тонове** превозени товари. Ще пресметнем **цените за всеки вид транспорт** според превозените тонове и **общата цена**. Накрая ще  пресметнем и отпечатаме **общата средна цена на тон** и **каква част от товара е превозена с всеки вид транспорт процентно**.

Декларираме си нужните променливи, например: **`count_of_loads`** – броя на товарите за превоз (прочитаме ги от конзолата), **`sum_of_tons`** – сумата от тонажа на всички товари, **`microbus_tons`**, **`truck_tons`**, **`train_tons`** – променливи, пазещи сумата от тонажа на товарите, превозвани съответно с микробус, камион и влак.

Ще ни трябва **`for` цикъл** от **`0`** до **`count_of_loads - 1`**, за да обходим всички товари. За всеки товар **прочитаме теглото му** (в тонове) от конзолата и го запазваме в променлива, например **`tons`**. Прибавяме към сумата от тонажа на всички товари (**`sum_of_tons`**) теглото на текущия товар (**`tons`**). След като сме прочели теглото на текущия товар, **трябва да определим кое превозно средство ще се ползва за него** (микробус, камион или влак). За целта ще ни трябват **`if-elif`** проверки:

 * Ако стойността на променливата **`tons`** е **по-малка от 3**, увеличаваме стойността на променливата **`microbus_tons`** със стойността на **`tons`**:
 
   ```python
   microbus_tons += tons;
   ```
   
 * Иначе, ако стойността **`tons`** е **до 11**, увеличаваме **`truck_tons`** с **`tons`**.
 * Ако **`tons`** e **повече от 11**, увеличаваме **`train_tons`** с **`tons`**.

Преди да отпечатаме изхода трябва да **изчислим процента на тоновете, превозвани с всяко превозно средство** и **средната цена на тон**. За средната цена на тон ще си декларираме още една помощна променлива **`total_price`**, в която ще **сумираме общата цена на всички превозвани товари** (с микробус, камион и влак). Средната цена ще получим, разделяйки **`total_price`** на **`sum_of_tons`**. Остава **сами да изчислите** процента на тоновете, превозвани с всяко превозно средство, и да отпечатате резултатите, спазвайки формата в условието.

### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1054#5](https://judge.softuni.org/Contests/Practice/Index/1054#5).
