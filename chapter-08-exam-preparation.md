# Chapter 8.1. Practical Exam Preparation - Part I

In **the present chapter**, we will examine a few **problems** with a level of **difficulty** that can be expected in **the problems** of the practical **exam** in “Programming Basics”. We will **review** and **practice** all the knowledge that was gained from this book and through the "Programming Basics" course.



## Video

<div class="video-player">
  Watch a video tutorial on this chapter here: <a target="_blank"
  https://www.youtube.com/watch?v=OYuT5_j1OVE.
</div>

## The "Programming Basics" Practical Exam

The course **"Programing Basics"** finishes with a **practical exam**. There are **6** problems included, and you will have **4 hours** to solve them. **Each** of the exam problems will **cover** one of the studied **topics** during the course. Problem topics are as follows:

- Problem with simple calculations (without conditions)
- Problem with simple condition
- Problem with more complex conditions
- Problem with a simple loop
- Problem with nested loops (drawing a figure on the console)
- Problem with nested loops and more complex logic

## The Online Evaluation System (Judge)

**All exams and homework** are automatically **tested** through the online **Judge system**: [https://judge.softuni.org](https://judge.softuni.org). For **each** of the problems, there are **visible** (zero points) tests that help you understand what is expected of the problem and fix your mistakes, as well as **competition** tests that are **hidden** and check if your solution is working properly. In the **Judge** system, you can log in with your **softuni.bg account**.

**How** does the testing in the **Judge** system work? **You upload** the source code and from the menu below you choose to compile as a **Python** program. The program is being **tested** with a series of tests, giving **points** for each **successful** test.


## Problems with Simple Calculations

**The first**  problem of the "Programming Basics" Practical Exam covers **simple calculations without checks and loops**. Here are a few examples:

### Problem: 2D Triangle Area

<table>
   <tr>
      <td width="60%">
        <b>Triangle in the plain</b>  is defined by the coordinates of its three vertices. First, <b>the vertex (x1, y1)</b> is set. Then the other two vertices are set: <b>(x2, y2)</b> and <b>(x3, y3)</b> which <b>lie on a common horizontal line</b> i.e. they have the same Y coordinates). Write a program that calculates <b>the triangle area</b> by the coordinates of its three vertices.
      </td>
      <td>
         <img src="assets/chapter-8-1-images/01.Triangle-area-01.png"/>
      </td>
   </tr>
</table>

#### Input
**6 integers** are read from the console (one per line): 
**x1, y1, x2, y2, x3, y3.**
-	All input numbers are in the range [**-1000 … 1000**].
-	It's guaranteed that **y2 = y3**.

#### Output
Print on the console **the triangle area**.

#### Sample Input and Output

|Input|Output|Visualization|Comments|
|-----|------|-------------|--------|
|5<br>-2<br>6<br>1<br>1<br>1|7.5|![](/assets/chapter-8-1-images/01.Triangle-area-01.png)|The side of the triangle **a** = 6 - 1 = **5**<br>The height of the triangle **h** = 1 - (-2) = **3**<br>The area of the triangle **S** = a \* h / 2 = 5 \* 3 / 2 = **7.5**|

|Input|Output|Visualization|Comments|
|-----|------|-------------|--------|
|4<br>1<br>-1<br>-3<br>3<br>-3|8|![](/assets/chapter-8-1-images/01.Triangle-area-02.png)|The side of the triangle **a** = 3 - (-1) = **4**<br>The height of the triangle **h** = 1 - (-3) = **4**<br>The area of the triangle **S** = a \* h / 2 = 4 \* 4 / 2 = **8**|

#### Hints and Guidelines

It is extremely important in these types of tasks, in which some coordinates are given, to pay attention to the ** order ** in which they are submitted, as well as to correctly understand which of the coordinates we will use and in what way.  In this case, the input is in order **x1, y1, x2, y2, x3, y3**. If we do not follow this sequence, the solution becomes wrong. First, we write the code that reads the input data:

![](/assets/chapter-8-1-images/01.Triangle-area-03.png)

We have to calculate **the side** and **the height** of the triangle. From the examples and the condition **`y2 = y3`** we notice that one **side** is always parallel to the horizontal axis. It means that its **length** is equal to the length of the segment between its coordinates **`x2` and `x3`**,  which is equal to the difference between the larger and the smaller coordinates. Similarly, we can calculate **the height**. It will always be equal to the difference between **`y1` and `y2`**(or **`y3`**,  as they are equal). Since we do not know if **`x2`** is greater than **`x3`**, or **`y1`** will be below or above the triangle side, we will use **the absolute values** of the difference to always get positive numbers because one segment cannot have a negative length.

![](/assets/chapter-8-1-images/01.Triangle-area-04.png)
  
We will use the formula familiar to us from school for finding the ** area of a triangle ** to calculate the area.

![](/assets/chapter-8-1-images/01.Triangle-area-05.png)

The only thing left is to print the area on the console.

![](/assets/chapter-8-1-images/01.Triangle-area-06.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1059#0](https://judge.softuni.org/Contests/Practice/Index/1059#0).


### Problem: Moving Bricks

Construction workers have to transfer a total of **x bricks**. **The workers** are **w** and work simultaneously. They transport the bricks in trolleys, each with a **capacity of m** bricks. Write a program that reads the integers **x**, **w**, and **m**, and calculates **what is the minimum number of courses** the workers need to do to transport the bricks.

#### Input

From the console **3 integers** are read (one per line):
- **The number of bricks x** is read from the first line.
- **The number of workers w** is read from the second line.
- **The capacity of the trolley m** is read from the third line. 

All input numbers are integers in the range [**1 … 1000**].

#### Output

Print on the console **the minimum number of courses** needed to transport the bricks.

#### Sample Input and Output
|Input|Output|Comments|
|-----|------|--------|
|120<br>2<br>30|2|We have **2** workers, each transporting **30** bricks per course. In total, workers are transporting **60**  bricks per course. To transport **120** bricks, exactly **2** courses are needed.|

|Input|Output|Comments|
|-----|------|--------|
|355<br>3<br>10|12|We have **3** workers, each transporting **10** bricks per course. In total, workers are transporting **30** bricks per course. To transport **355** bricks, exactly **12** courses are needed: **11** complete courses carry **330** bricks and the last **12th** course carries the last **25** bricks.|

|Input|Output|Comments|
|-----|------|--------|
|5<br>12<br>30|1|We have **5** workers, each transporting **30** bricks per course. In total, workers are transporting **150** bricks per course. To transport **5** bricks, only **1** course is enough (although incomplete, with only 5 bricks).|

#### Hints and Guidelines

The input is standard, and we only have to pay attention to the sequence in which we read the data:

![](/assets/chapter-8-1-images/02.Bricks-01.png)

We calculate how many **bricks** the workers transport in a single course:

![](/assets/chapter-8-1-images/02.Bricks-02.png)

By dividing the total number of **bricks transported for 1 course**, we will obtain the number of **courses** needed to carry them. We will use the **`math.ceil (…)`** function to round the result up. ** Remember ** to add **`import math`** at the beginning of the working file so that the **`math.ceil (…)`** function can work. When the bricks can be transferred with **an exact number of courses**, the division will return a whole number and there will be nothing to round. Accordingly, if not, the result of the division will be **the number of exact courses** but with a decimal fraction.  The decimal part will be rounded up and we will get the required **1 course** for the remaining bricks.

![](/assets/chapter-8-1-images/02.Bricks-03.png)

In the end, we print the result on the console:

![](/assets/chapter-8-1-images/02.Bricks-04.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1059#1](https://judge.softuni.org/Contests/Practice/Index/1059#1).


## Problems with Simple Condition

**The second** problem of the "Programming Basics" Practical Exam covers **conditional statements and simple calculations**. Here are a few examples:

### Problem: Point on a Segment

On a horizontal line **a horizontal segment** is placed, set with the **x** coordinates at both ends: **first** and **second**. **A point** is located **on** the same horizontal line and is set with its **x coordinate**. Write a program that checks whether the point is **inside or outside of the segment** and calculates **the distance to the nearest end** of the segment.

#### Input

From the console **3 integers** are read (one per line):
- On the first line is the number first - **one end of the segment**.
- On the second line is the number second - **the other end of the segment**.
- On the third line is the number point - **the location of the point**. 

All inputs are integers in the range [**-1000 … 1000**].

#### Output

Print the result on the console:
- On the first line, print "**in**" or "**out**" – whether the point is inside or outside the segment.
- On the second line, print the distance from the point to the nearest end of the segment.

#### Sample Input and Output

|Input|Output|Visualization|
|-----|------|-------------|
|10<br>5<br>7|in<br>2|![](/assets/chapter-8-1-images/03.Point-on-segment-01.png)|

|Input|Output|Visualization|
|-----|------|-------------|
|8<br>10<br>5|out<br>3|![](/assets/chapter-8-1-images/03.Point-on-segment-02.png)|

|Input|Output|Visualization|
|-----|------|-------------|
|1<br>-2<br>3|out<br>2|![](/assets/chapter-8-1-images/03.Point-on-segment-03.png)|

#### Hints and Guidelines

First we read the input: 

![](/assets/chapter-8-1-images/03.Point-on-segment-04.png)

Since we do not know which **point**  is on the left and which is on the right, we will create two variables to mark this. Since **the left point** is always the one with the smaller **x coordinate**, we will use the **`min(…)`** function to find it. Accordingly, **the right point** is always the one with a larger **x coordinate** and we will use the **`max(…)`** function. We will also find the distance from **the point x** to **the two points**. Since we do not know their position relative to each other, we will use the **`abs(…)`** function to get a positive result: 

![](/assets/chapter-8-1-images/03.Point-on-segment-05.png)

The shorter of the two **distances** we will find by using **`min(…)`**:

![](/assets/chapter-8-1-images/03.Point-on-segment-06.png)

What remains is to find whether **the point** is on or out of the line. The point will be **on the line** always when it **matches** one of the other two points or its x coordinate lies **between them**. Otherwise, the point is **outside the line**. After checking, we display one of the two messages ("**in**" or "**out**"), depending on which condition is satisfied:

![](/assets/chapter-8-1-images/03.Point-on-segment-07.png)

Finally, we print **the distance** found before.

![](/assets/chapter-8-1-images/03.Point-on-segment-08.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1059#2](https://judge.softuni.org/Contests/Practice/Index/1059#2).


### Problem: Point on a Figure

Write a program that checks if a point (with coordinates **x** and **y**) is **inside** or **outside** of the given figure:
 
![](/assets/chapter-8-1-images/04.Point-in-figure-01.png)

#### Input

From the console are read **two integers** (one per line): **x** и **y**.

All inputs are integers in the range **[-1000 … 1000]**.

#### Output

Print on the console "**in**" or "**out**" – whether the point is **inside** or **outside** the figure (the outline is inside).

#### Sample Input and Output

|Input|Output|Input|Output|
|----|----|----|----|
|8<br>-5|in|6<br>-3|in|

|Input|Output|Input|Output|
|----|----|----|----|
|11<br>-5|out|11<br>2|out|

#### Hints and Guidelines

To find out if **the point** is inside of the figure, we will divide **the figure** into 2 rectangles:

![](/assets/chapter-8-1-images/04.Point-in-figure-02.png)
![](/assets/chapter-8-1-images/04.Point-in-figure-03.png)

A sufficient condition is the ** point ** to be located in one of them to be in the ** figure **. 

We read the input from the console:

![](/assets/chapter-8-1-images/04.Point-in-figure-04.png)

We will initialize two variables that will mark whether **the point** is in one of the rectangles:

![](/assets/chapter-8-1-images/04.Point-in-figure-05.png)

When printing the message, we will check whether any of the variables has accepted a value of **`True`**. It's enough **only one** of them to be **`True`**  so that the point is in the figure.

![](/assets/chapter-8-1-images/04.Point-in-figure-06.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1059#3](https://judge.softuni.org/Contests/Practice/Index/1059#3).


## Problems with Complex Conditions

**The third** problem of the "Programming Basics" Practical Exam includes **several nested checks combined with simple calculations**. Here are a few examples:

### Problem: Date after 5 days

There are two numbers **d** (day) and **m** (month) that form **a date**. Write a program that prints the date that will be **after 5 days**. For example, 5 days after **28.03** is the date **2.04**. We assume that the months: April, June, September, and November have 30 days, February has 28 days, and the rest have 31 days. Months to be printed with **leading zero** when they are single-digit numbers (e.g. 01, 08).

#### Input
  
The input is read from the console and consists of two lines:
- On the first line there is an integer **d** in the interval [**1… 31**] - day. The number of the day does not exceed the number of days in the respective month (e.g. 28 for February).
- On the second line there is an integer **m** in the interval [**1… 12**] - month. Month 1 is January, month 2 is February,…, month 12 is December. The month may contain a leading zero (e.g. April may be written as 4 or 04). 

#### Output

Print a single line containing the date after 5 days in the format **day.month** on the console. The month must be a two-digit number with a leading zero, if necessary. The day must be written without a leading zero.

#### Sample Input and Output

|Input|Output|Input|Output|
|-----|------|-----|------|
|28<br>03|2.04|27<br>12|1.01|

|Input|Output|Input|Output|
|-----|------|-----|------|
|25<br>1|30.01|26<br>02|3.03|

#### Насоки и подсказки

We read the input data from the console: 

![](/assets/chapter-8-1-images/05.Date-after-5-days-01.png)

To make our checks easier, we will create a variable that will contain the **number of days** that we have in the month we set:

![](/assets/chapter-8-1-images/05.Date-after-5-days-02.png)

We increase the **day** by 5:

![](/assets/chapter-8-1-images/05.Date-after-5-days-03.png)

We check if **the day** has exceeded the number of days in **the month**. If so, we must deduct the days of the month from the obtained day to calculate which day of the next month our day corresponds to:

![](/assets/chapter-8-1-images/05.Date-after-5-days-04.png)

After we have passed to **the next month**,  this should be noted by increasing the initial one by 1. We need to check if it has become greater than 12 and if it has, to adjust it. Because we cannot skip more than **one month** when we increase by 5 days, the following check is enough:

![](/assets/chapter-8-1-images/05.Date-after-5-days-05.png)

The only thing that remains is to print the result on the console. It is important to **format the output** correctly to display the leading zero in the first 9 months. This is done by adding a **formatted string** **`%02d`** for the second element: 

![](/assets/chapter-8-1-images/05.Date-after-5-days-06.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1059#4](https://judge.softuni.org/Contests/Practice/Index/1059#4).


### Problem: Sums of Three Numbers

There are **3 integers** given. Write a program that checks if **the sum of two of the numbers is equal to the third one**. For example, if the numbers are **3**, **5**, and **2**, the sum of two of the numbers is equal to the third one: **2 + 3 = 5**.

#### Input

From the console are read **three integers**, one per line. The numbers are in the range  [**1 … 1000**].

#### Output

-	Print a single line on the console containing the solution of the problem in the format "**a + b = c**", where **a**, **b** and **c** are among the three input numbers and  **a ≤ b**.
-	If the problem has no solution, print “**No**” on the console.

#### Sample Input and Output

|Input|Output|Input|Output|
|-----|------|-----|------|
|3<br>5<br>2|2 + 3 = 5|2<br>2<br>4|2 + 2 = 4|

|Input|Output|Input|Output|
|-----|------|-----|------|
|1<br>1<br>5|No|2<br>6<br>3|No|

#### Hints and Guidelines

We take the input from the console:

![](/assets/chapter-8-1-images/06.Sums-3-numbers-01.png)

We have to check if **the sum** of a pair of numbers is equal to the third number. We have three possible cases:
* a + b = c
* a + c = b 
* b + c = a

We will write **a template**, which will later be complemented by the required code. If none of the above three conditions is met, we will make our program print "**No**":

![](/assets/chapter-8-1-images/06.Sums-3-numbers-02.png)

Now it remains to understand the order in which **the two addends** will be displayed at the output of the program. For this purpose we will make a **nested condition**, which checks which of the two numbers is the greater. In the first case, it will be as follows: 
  
![](/assets/chapter-8-1-images/06.Sums-3-numbers-03.png)

Similarly, we will supplement the other two cases. The full code of the program will look like this:

![](/assets/chapter-8-1-images/06.Sums-3-numbers-04.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1059#5](https://judge.softuni.org/Contests/Practice/Index/1059#5).


## Задачи с единичен цикъл

**Четвъртата** задача от практическия изпит по “Основи на програмирането” включва **единичен цикъл с проста логика** в него. Ето няколко примера:

### Задача: суми през 3

Дадени са **n** цели числа **a1, a2, …, an**. Да се пресметнат сумите:
-	**sum1 = a1 + a4 + a7** + … (сумират се числата, започвайки от първото със стъпка 3).
-	**sum2 = a2 + a5 + a8** + … (сумират се числата, започвайки от второто със стъпка 3).
-	**sum3 = a3 + a6 + a9** + … (сумират се числата, започвайки от третото със стъпка 3).

#### Вход

Входните данни се четат от конзолата. На първия ред стои цяло число **n (0 ≤ n ≤ 1000)**. На следващите **n** реда стоят **n** цели числа в интервала [**-1000 … 1000**]: **a1, a2, …, an**.

#### Изход

На конзолата трябва да се отпечатат 3 реда, съдържащи търсените 3 суми, във формат като в примерите.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|Вход|Изход|
|---|---|---|---|---|---|
|2<br>3<br>5<br>|sum1 = 3<br>sum2 = 5<br>sum3 = 0|4<br>7<br>-2<br>6<br>12|sum1 = 19<br>sum2 = -2<br>sum3 = 6|5<br>3<br>5<br>2<br>7<br>8|sum1 = 10<br>sum2 = 13<br>sum3 = 2| 

#### Насоки и подсказки

Ще вземем **броя на числата** от конзолата и ще декларираме **начални стойности** на трите суми:

![](/assets/chapter-8-1-images/07.Sums-Step-3-01.png)

Тъй като не знаем предварително колко числа ще обработваме, ще ги прочитаме едно по едно в **цикъл**, който ще се повтори **n на брой пъти** и ще ги обработваме в тялото на цикъла:

![](/assets/chapter-8-1-images/07.Sums-Step-3-02.png)

За да разберем в коя от **трите суми** трябва да добавим числото, ще разделим **поредния му номер на три** и ще използваме **остатъка**. Ще използваме променливата **`i`**, която следи **броя завъртания** на цикъла, за да разберем на кое поред число сме. Когато резултатът от **`i % 3`** е **нула**, това означава, че ще добавяме това число към **първата** сума, когато е **1** към **втората** и съответно, когато е **2** към **третата**:

![](/assets/chapter-8-1-images/07.Sums-Step-3-03.png)

Накрая, ще отпечатаме резултата на конзолата в изисквания от условието **формат**:

![](/assets/chapter-8-1-images/07.Sums-Step-3-04.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1059#6](https://judge.softuni.org/Contests/Practice/Index/1059#6).


### Задача: поредица от нарастващи елементи

Дадена е редица от **n** числа: **a1**, **a2**, **…**, **an**. Да се пресметне **дължината на най-дългата нарастваща поредица** от последователни елементи в редицата от числа.

#### Вход

Входните данни се четат от конзолата. На първия ред стои цяло число **n** (**0 ≤ n ≤ 1000**). На следващите **n** реда стоят **n** цели числа в интервала [**-1000 … 1000**]: **a1**, **a2**, **…**, **an**.

#### Изход

На конзолата трябва да се отпечата едно число – **дължината** на най-дългата нарастваща редица.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|Вход|Изход|Вход|Изход|
|---|---|---|---|---|---|---|---|
|3<br>5<br>2<br>4|2|4<br>2<br>8<br>7<br>6|2|4<br>1<br>2<br>4<br>4|3|4<br>5<br>6<br>7<br>8|4|

#### Насоки и подсказки

За решението на тази задача трябва да помислим малко **по-алгоритмично**. Дадена ни е **редица от числа** и трябва да проверяваме дали всяко **следващо** число е **по-голямо от предходното** и ако е така да броим колко дълга е тази подредица, в която това условие е изпълнено. След това трябва да намерим **коя подредица** е **най-дълга**. За целта, нека да си направим няколко променливи, които ще ползваме през хода на задачата: 

![](/assets/chapter-8-1-images/08.Increasing-numbers-01.png)

Променливата **`n`** е **броя числа**, които ще получим от конзолата. В **`count_current_longest`** ще запазваме **броя на елементите** в нарастващата подредица, която **броим в момента**. Напр. при редицата: 5, 6, 1, 2, 3 **`count_current_longest`** ще бъде 2, когато сме стигнали **втория елемент** от броенето (5, **6**, 1, 2, 3) и ще стане 3, когато стигнем **последния елемент** (5, 6, 1, 2, **3**), понеже нарастващата редица 1, 2, 3 има 3 елемента. Ще използваме **`count_longest`**, за да запазим **най-дългата** нарастваща редица. Останалите променливи, който ще използваме, са **`a`** - числото, на което се намираме **в момента**, и **`a_prev`** - **предишното число**, което ще сравним с **`a`**, за да разберем дали редицата **расте**.

Започваме да обхождаме числата и проверяваме дали настоящото число **`а`** е по-голямо от предходното **`a_prev`**. Ако това е изпълнено, значи подредицата **е нарастваща** и трябва да увеличим броя ѝ с **1**. Това запазваме в променливата, която следи дължината на редицата, в която се намираме в момента, а именно - **`count_current_longest`**. Ако числото **`а`** **не е по-голямо** от предходното, това означава, че започва **нова подредица** и трябва да стартираме броенето от **1**. Накрая, след всички проверки, **`a_prev`** става **числото**, което използваме **в момента**, и започваме цикъла от начало със **следващото** въведено **`а`**.

Ето и примерна реализация на описания алгоритъм:

![](/assets/chapter-8-1-images/08.Increasing-numbers-02.png)

Остава да разберем коя от всички редици е **най-дълга**. Това ще направим с проверка в цикъла дали **редицата**, в която се намираме **в момента**, е станала по-дълга от дължината на **най-дългата намерена до сега**. Целият цикъл ще изглежда така:

![](/assets/chapter-8-1-images/08.Increasing-numbers-03.png)

Накрая принтираме дължината на **най-дългата** намерена редица:

![](/assets/chapter-8-1-images/08.Increasing-numbers-04.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1059#7](https://judge.softuni.org/Contests/Practice/Index/1059#7).


## Задачи за чертане на фигурки на конзолата

**Петата** задача от практическия изпит по “Основи на програмирането” изисква **използване на един или няколко вложени цикъла за рисуване** на някаква фигурка на конзолата. Може да се изискват логически размишления, извършване на прости пресмятания и проверки. Задачата проверява способността на студентите да мислят логически и да измислят прости алгоритми за решаване на задачи, т.е. да мислят алгоритмично. Ето няколко примера за изпитни задачи:

### Задача: перфектен диамант

Да се напише програма, която прочита от конзолата цяло число **n** и чертае **перфектен диамант** с размер **n** като в примерите по-долу.

#### Вход

Входът е цяло число **n** в интервала [**1 … 1000**].

#### Изход

На конзолата трябва да се отпечата диамантът като в примерите.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|----|----|----|----|
|2|<code>&nbsp;&#42;&nbsp;</code><br><code>&#42;-&#42;</code><br><code>&nbsp;&#42;&nbsp;</code>|3|<code>&nbsp;&nbsp;&#42;&nbsp;&nbsp;</code><br><code>&nbsp;&#42;-&#42;&nbsp;</code><br><code>&#42;-&#42;-&#42;</code><br><code>&nbsp;&#42;-&#42;&nbsp;</code><br><code>&nbsp;&nbsp;&#42;&nbsp;&nbsp;</code><br>|

|Вход|Изход|Вход|Изход|
|---|---|---|---|
|4|<code>&nbsp;&nbsp;&nbsp;&#42;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&#42;-&#42;&nbsp;&nbsp;</code><br><code>&nbsp;&#42;-&#42;-&#42;&nbsp;</code><br><code>&#42;-&#42;-&#42;-&#42;</code><br><code>&nbsp;&#42;-&#42;-&#42;&nbsp;</code><br><code>&nbsp;&nbsp;&#42;-&#42;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&nbsp;&#42;&nbsp;&nbsp;&nbsp;</code><br>|5|<code>&nbsp;&nbsp;&nbsp;&nbsp;&#42;&nbsp;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&nbsp;&#42;-&#42;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&#42;-&#42;-&#42;&nbsp;&nbsp;</code><br><code>&nbsp;&#42;-&#42;-&#42;-&#42;&nbsp;</code><br><code>&#42;-&#42;-&#42;-&#42;-&#42;</code><br><code>&nbsp;&#42;-&#42;-&#42;-&#42;&nbsp;</code><br><code>&nbsp;&nbsp;&#42;-&#42;-&#42;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&nbsp;&#42;-&#42;&nbsp;&nbsp;&nbsp;</code><br><code>&nbsp;&nbsp;&nbsp;&nbsp;&#42;&nbsp;&nbsp;&nbsp;&nbsp;</code><br>|

#### Насоки и подсказки

В задачите за чертане на фигурки най-важното, което трябва да преценим е **последователността**, в която ще рисуваме. Кои елементи се **повтарят** и с какви **стъпки**. В конкретната задача, ясно може да забележим, че **горната и долната** част на диаманта са **еднакви**. Най-лесно ще я решим, като направим **един цикъл**, който чертае **горната част**, и след това още **един**, който чертае **долната** (обратно на горната).

Първо прочитаме числото **`n`** от конзолата:

![](/assets/chapter-8-1-images/09.Perfect-diamond-01.png)

Започваме да рисуваме **горната половина** на диаманта. Ясно виждаме, че **всеки ред** започва с няколко **празни места и <code>*</code>**. Ако се вгледаме по-внимателно, ще забележим, че **празните места** са винаги равни на **`n - броя на реда`** (на първия ред са n-1, на втория - n-2 и т.н.) Ще започнем с това да нарисуваме броя **празни места**, както и **първата звездичка**. Нека не забравяме да използваме **`print(…, end='')`** вместо само **`print(…)`**, за да оставаме на **същия ред**. На края на реда пишем **`print()`**, за да преминем на **нов ред**. Забележете, че започваме да броим от **1, а не от 0**. След това ще остане само да добавим няколко пъти **`-*`**, за да **довършим реда**.

Ето фрагмент от кода за начертаване на **горната част на диаманта**:

![](/assets/chapter-8-1-images/09.Perfect-diamond-02.png)

Остава да **довършим всеки ред** с нужния брой **`-*`** елементи. На всеки ред трябва да добавим **`i - 1`** такива **елемента** (на първия 1-1 -> 0, на втория -> 1 и т.н.)

Ето и пълния код за начертаване на **горната част на диаманта**:

![](/assets/chapter-8-1-images/09.Perfect-diamond-03.png)

За да изрисуваме **долната част** на диаманта, трябва да обърнем **горната** на обратно. Ще броим от **`n - 1`**, тъй като ако започнем от **`n`**, ще изрисуваме средния ред два пъти. Не забравяйте да добавите **`reversed(…)`** на **`range(…)`** на главния цикъл.

Ето го и кода за начертаване на **долната част на диаманта**:

![](/assets/chapter-8-1-images/09.Perfect-diamond-04.png)

Остава **да сглобим цялата програма** като първо четем входа, печатаме горната част на диаманта и след него и долната част на диаманта.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1059#8](https://judge.softuni.org/Contests/Practice/Index/1059#8).


### Задача: правоъгълник със звездички в центъра

Да се напише програма, която прочита от конзолата цяло число **n** и чертае **правоъгълник** с размер **n с две звездички в центъра**, като в примерите по-долу.

#### Вход

Входът е цяло число **n** в интервала [**2 … 1000**].

#### Изход

На конзолата трябва да се отпечата правоъгълникът като в примерите.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|---|---|---|---|
|2|<code>&#37;&#37;&#37;&#37;</code><br><code>&#37;&#42;&#42;&#37;</code><br><code>&#37;&#37;&#37;&#37;</code><br>|3|<code>&#37;&#37;&#37;&#37;&#37;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&#42;&#42;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&#37;&#37;&#37;&#37;&#37;</code><br>|

|Вход|Изход|Вход|Изход|
|---|---|---|---|
|4|<code>&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&#42;&#42;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;</code><br>|5|<code>&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&#42;&#42;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#37;</code><br><code>&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;&#37;</code><br>|

#### Насоки и подсказки

Прочитаме входните данни от задачата:

![](/assets/chapter-8-1-images/10.Rectangle-with-stars-01.png)

Първото нещо, което лесно забелязваме, е че **първият и последният ред** съдържат **`2 * n`** символа **`%`**. Ще започнем с това и после ще нарисуваме средата на четириъгълника:

![](/assets/chapter-8-1-images/10.Rectangle-with-stars-02.png)

От дадените примери виждаме, че **средата** на фигурата винаги има **нечетен брой** редове. Забелязваме, че когато е зададено **четно число**, броят на редовете е равен на **предишното нечетно** (2 -> 1, 4 -> 3 и т.н.). Създаваме променлива, която представлява броя редове, които ще има нашият правоъгълник, и я коригираме, ако числото **`n` е четно**. След това ще нарисуваме **правоъгълника без звездичките**. Всеки ред има за **начало и край** символа **`%`** и между тях **`2 * n - 2`** празни места (ширината е **`2 * n`** и вадим 2 за двата процента в края). Не забравяйте да преместите кода за **последния ред след цикъла**:

![](/assets/chapter-8-1-images/10.Rectangle-with-stars-03.png)

Можем да **стартираме и тестваме кода до тук**. Всичко без двете звездички в средата трябва да работи коректно.

Сега остава **в тялото** на цикъла да добавим и **звездичките**. Ще направим проверка дали сме на **средния ред**. Ако сме на средния (това ще проверим като сравним **`i`** с **`floor(num_rows / 2)`**), ще рисуваме **реда** заедно **със звездичките**, ако не - ще рисуваме **нормален ред**. **Не забравяйте** да добавите **`from math import floor`** в началото на работния файл, за да може да използваме функцията **`floor(…)`**. Редът със звездичките има **`n - 2`** **празни места** (**`n`** е половината дължина и махаме звездичката и процента), **две звезди** и отново **`n - 2` празни места**. Двата процента в началото и в края на реда ги оставяме извън проверката:

![](/assets/chapter-8-1-images/10.Rectangle-with-stars-04.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1059#9](https://judge.softuni.org/Contests/Practice/Index/1059#9).


## Задачи с вложени цикли с по-сложна логика

**Последната** (шеста) задача от практическия изпит по “Основи на програмирането” изисква използване на **няколко вложени цикъла и по-сложна логика в тях**. Задачата проверява способността на студентите да мислят алгоритмично и да решават нетривиални задачи, изискващи съставянето на цикли. Следват няколко примера за изпитни задачи.


### Задача: четворки нарастващи числа

По дадена двойка числа **a** и **b** да се генерират всички четворки **n1, n2, n3, n4,** за които **a ≤ n1 < n2 < n3 < n4 ≤ b**.

#### Вход

Входът съдържа две цели числа **a** и **b** в интервала [**0 … 1000**], по едно на ред.

#### Изход

Изходът съдържа всички търсени **четворки числа**, в нарастващ ред, по една на ред.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|---|---|---|---|
|3<br>7|3 4 5 6<br>3 4 5 7<br>3 4 6 7<br>3 5 6 7<br>4 5 6 7|15<br>20|15 16 17 18<br>15 16 17 19<br>15 16 17 20<br>15 16 18 19<br>15 16 18 20<br>15 16 19 20<br>15 17 18 19<br>15 17 18 20<br>15 17 19 20<br>15 18 19 20<br>16 17 18 19<br>16 17 18 20<br>16 17 19 20<br>16 18 19 20<br>17 18 19 20<br>|

|Вход|Изход|Вход|Изход|
|---|---|---|---|
|5<br>7|No|10<br>13|10 11 12 13|

#### Насоки и подсказки

Ще прочетем входните данни от конзолата. Създаваме и допълнителната променлива **`count`**, която ще следи дали има **съществуваща редица числа**:

![](/assets/chapter-8-1-images/11.Increasing-4-numbers-01.png)

Най-лесно ще решим задачата, ако логически я разделим **на части**. Ако се изисква да изведем всички редици от едно число между **`a`** и **`b`**, ще го направим с **един цикъл**, който изкарва всички числа от **`а`** до **`b`**. Нека помислим как ще стане това с **редици от две числа**. Отговорът е лесен - ще ползваме **вложени цикли**: 

![](/assets/chapter-8-1-images/11.Increasing-4-numbers-02.png)

Можем да тестваме недописаната програма, за да проверим дали работи коректно до този момент. Тя трябва да отпечата всички двойки числа **`i`**, **`j`**, за които **`i ≤ j`**.

Тъй като всяко **следващо число** от редицата трябва да е **по-голямо** от **предишното**, вторият цикъл ще се върти от **`i + 1`** (следващото по-голямо число). Съответно, ако **не съществува редица** от две нарастващи числа (**`a`** и **`b`** са равни), вторият цикъл  **няма да се изпълни** и няма да се разпечата нищо на конзолата.

**Аналогично**, остава да реализираме по същия начин **вложените цикли** и за **четири числа**. Ще добавим и **увеличаване на брояча** (**`count`**), който инициализирахме в началото, за да знаем дали **съществува** такава **редица**:

![](/assets/chapter-8-1-images/11.Increasing-4-numbers-03.png)

Накрая ще проверим дали **броячът** е равен на **0** и съответно ще принтираме "**No**" на конзолата, ако е така:

![](/assets/chapter-8-1-images/11.Increasing-4-numbers-04.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1059#10](https://judge.softuni.org/Contests/Practice/Index/1059#10).


### Задача: генериране на правоъгълници

По дадено число **n** и **минимална площ m** да се генерират всички правоъгълници с цели координати в интервала [**-n … n**], с площ поне **m**. Генерираните правоъгълници да се отпечатат в следния формат:

**(left, top) (right, bottom) -> area**

Правоъгълниците се задават чрез горния си ляв и долния си десен ъгъл. В сила са следните неравенства:
-	**-n ≤ left < right ≤ n**
-	**-n ≤ top < bottom ≤ n**

#### Вход

От конзолата се въвеждат две числа, по едно на ред:

-	Цяло число **n** в интервала [**1 … 100**] – задава минималната и максималната координата на връх.
-	Цяло число **m** в интервала [**0 … 50 000**] – задава минималната площ на генерираните правоъгълници.

#### Изход

-	На конзолата трябва да се отпечатат описаните правоъгълници във формат като в примерите по-долу.
-	Ако за числата **n** и **m** няма нито един правоъгълник, да се изведе "**No**".
-	Редът на извеждане на правоъгълниците е без значение.

#### Примерен вход и изход

|Вход|Изход|Вход|Изход|
|---|---|---|---|
|1<br>2|(-1, -1) (0, 1) -> 2<br>(-1, -1) (1, 0) -> 2<br>(-1, -1) (1, 1) -> 4<br>(-1, 0) (1, 1) -> 2<br>(0, -1) (1, 1) -> 2|2<br>17|No|

|Вход|Изход|
|---|---|
|3<br>36|(-3, -3) (3, 3) -> 36|

#### Насоки и подсказки

Да прочетем входните данни от конзолата. Отново ще създадем и един **брояч**, в който ще пазим броя на намерените правоъгълници:

![](/assets/chapter-8-1-images/12.Generating-rectangles-01.png)

Изключително важно е да успеем да си представим задачата, преди да започнем да я решаваме. В нашия случай се изисква да търсим правоъгълници в координатна система. Нещото, което знаем е, че **лявата точка** винаги ще има координата **`х`, по-малка** от **дясната**. Съответно **горната** винаги ще има **по-малка** координата **`у`** от **долната**. За да намерим всички правоъгълници, ще трябва да направим **цикъл**, подобен на този от предходната задача, но този път **не всеки следващ цикъл** ще започва от **следващото число**, защото някои от **координатите** може да са **равни** (например **`left`** и **`top`**):

![](/assets/chapter-8-1-images/12.Generating-rectangles-02.png)

С променливите **`left`** и **`right`** ще следим координатите по **хоризонталата**, а с **`top`** и **`bottom`** - по **вертикалата**. Важното тук е да знаем кои координати кои са, за да можем да изчислим правилно страните на правоъгълника. Сега трябва да намерим **лицето на правоъгълника** и да направим проверка дали то е **по-голямо** или **равно** на **`m`**. Едната **страна** ще е **разликата между `left` и `right`**, а **другата -  между `top` и `bottom`**. Тъй като координатите евентуално може да са разменени, ще ползваме **абсолютни стойности**. Отново добавяме и **брояча** в цикъла, като броим **само четириъгълниците**, които изписваме. Важно е да забележим, че поредността на изписване е **`left`**, **`top`**, **`right`**, **`bottom`**, тъй като така е зададено в условието:

![](/assets/chapter-8-1-images/12.Generating-rectangles-03.png)

Накрая принтираме "**No**", ако не съществуват такива правоъгълници:

![](/assets/chapter-8-1-images/12.Generating-rectangles-04.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1059#11](https://judge.softuni.org/Contests/Practice/Index/1059#11).
