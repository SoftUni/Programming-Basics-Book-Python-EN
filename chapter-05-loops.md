# Chapter 5.1. Loops (Repetitions)

In this chapter we will get familiar with how to **repeat blocks of commands**, known in programming as "**loops**". We will write a number of loops using the **`for`** operator in its classic form. Finally, we will solve some practical problems, which require repeating series of actions, using loops.


## Video

<div class="video-player">
  Watch video-tutorial about this chapter here: 
  https://www.youtube.com/watch?v=pvTMTGsooMk.
</div>


## Repeating blocks of code (for loop)

In programming it is often required **to execute a block with commands multiple times**. For this reason we are using **loops**. We can see an example for **`for` loop**, which goes through the numbers from 1 to 10 and prints them:

![](/assets/chapter-5-1-images/00.For-loop-01.png)

The loop starts with the **operator `for`** and passes through all values of particular variable in given range, for example all numbers from 1 to 10 included (without 11) and for each value it performs series of commands.

Upon declaring the loop, you can specify a **start value** and **end value**, while the end value is not included in the range. **The body of the loop** is a block with at least one commands. THe figure below shows the structure of a **`for` loop**:

![](/assets/chapter-5-1-images/00.For-loop-02.png)

In most cases a **`for` loop** is run between **`1`** and **`n`** (for example from 1 to 10). The purpose of the loop is to go sequentially through the numbers 1, 2, 3, …, n  and for each of them to perfomrm a particular action. In the example above, the variable **`i`** accepts values from 1 to 10 and  the current value is printes in the body of the loop. The loop is repeated 10 times and each of these repetitions is called "**iteration**".

### Problem: the numbers from 1 to 100

Write a program that **prints the numbers from 1 to 100**. The program does not accept input and prints the numbers from 1 to 100 sequentially, each on a separate line.

#### Hints and guidelines

We can solve the problem using a **`for` loop** , via which we will pass through the numbers from 1 to 100 using the **`i`** variable, and print the numbers in the body of the loop:

![](/assets/chapter-5-1-images/01.Numbers-1-to-100-01.png)

**Start** the program with [**Ctrl+Shift+F10**] or with right click - **Run** and **test it**:

![](/assets/chapter-5-1-images/01.Numbers-1-to-100-02.png)

#### Test in the Judge system

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#0](https://judge.softuni.org/Contests/Practice/Index/1053#0).

You should get **100 points** (fully accurate solution).

### Problem: numbers to 1000, ending in 7

Write a program that finds all numbers in range [**1 … 1000**], that end in 7. 

####  Hints and guidelines

We can solve the problem by combining a **`for` loop** for passing through the numbers between 1 and 1000 and a condition to **check** if each of the numbers end in 7. Of course, there are other solutions, but let's solve the problem using **loop + condition**:

![](/assets/chapter-5-1-images/02.Numbers-ending-in-7-01.png)

#### Test in the Judge system

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#1](https://judge.softuni.org/Contests/Practice/Index/1053#1).


### Problem: all Latin letters

Write a program that prints the letters from the Latin alphabet: **a, b, c, …, z**.

#### Hints and guidelines

It is good to know that the **`for` loops** don't work only with numbers. We can solve the task by running a **`for` loop**, that goes sequentially through all letters in the Latin alphabet:

![](/assets/chapter-5-1-images/03.Latin-letters-01.png)

#### Test in the Judge system

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#2](https://judge.softuni.org/Contests/Practice/Index/1053#2).


### Problem: sum of numbers

Write a program that **reads `n` integers and finds their sum**.

* The first line of the input holds the number of integers **`n`**.
* Each of the following **`n`** holds an integer.
* Sum up the numbers and print the result.

#### Sample Input and Output

| Input | Output |
| --- | --- |
| 2<br>10<br>20 | 30 |
| 3<br>-10<br>-20<br>-30 | -60 |
| 4<br>45<br>-20<br>7<br>11<br> | 43 |
| 1<br>999 | 999 | 
| 0 | 0 |

#### Hints and guidelines

We can solve the problem with summing up numbers in the following way:
 - We read the input number **`n`**.
 - We initially start with a sum **`sum = 0`**.
 - We run a loop from 0 to **`n`**. On each step of the loop, we read the number **`num`** and add it to the **`sum`**.
 - Finally, we print the calculated amount **`sum`**.
 
Here is the source code for the solution:

![](/assets/chapter-5-1-images/04.Sum-numbers-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#3](https://judge.softuni.org/Contests/Practice/Index/1053#3).


### Problem: Max number

Write a program that enters **n integers** (**n** > 0) and finds **the max** among them. The first line of the input, reads the number of integers. After that the next lines read the integers, each on separate line. Examples:

#### Sample Input and Output

| Input | Output |
| --- | --- |
| 2<br>100<br>99 | 100 | 
| 3<br>-10<br>20<br>-30 | 20 |
| 4<br>45<br>-20<br>7<br>99<br> | 99 | 
| 1<br>999 | 999 |
| 2<br>-1<br>-2 | -1 |

#### Hints and guidelines

We will first enter one number **`n`** (the number of integers that are about to be entered). We assign the current maximum **`max`**an initial neutral value, for example **-10000000000000**. Using a **`for` loop**, that is iterated **n-1 times**, we read one integer **`num`**.  If the read number **`num`** is higher than the current maximum **`max`**, we assign the value of the **`num`** to the **`max`** value. Finally, in **`max`**  we must have stored the highest number. We print the number on the console.:

![](/assets/chapter-5-1-images/05.Max-number-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#4](https://judge.softuni.org/Contests/Practice/Index/1053#4).


### Problem: Min number

Write a program that enters **n integers** (**n** > 0) and finds **the min** among them. The first line of the input, reads the number of integers and after that the next lines read the integers, each on separate line.

#### Sample Input and Output

| Input | Output | 
| --- | --- |
| 2<br>100<br>99 | 99 |
| 3<br>-10<br>20<br>-30 | -30 |
| 4<br>45<br>-20<br>7<br>99<br> | -20 |

#### Hints and Guidelines

The problem is completely identical to the previous one, except this time we will start with another neutral starting value:

![](/assets/chapter-5-1-images/06.Min-number-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#5](https://judge.softuni.org/Contests/Practice/Index/1053#5).


### Example: Left and right sum

Write a program that reads an input **2 \* n integers** and checks if ** the sum of the first n numbers** (left sum) is equal to **the sum of the second n numbers** (right sum). In case the sums are equal, print **"Yes" + sum**, otherwise print **"No" + the difference**. The difference is calculated as a positive number (by absolute value). The format of the output must be identical to the one in the examples below.

#### Sample Input and Output

| Input | Output | Input | Output |
| --- | --- | --- | --- | 
| 2<br>10<br>90<br>60<br>40 | Yes, sum = 100 | 2<br>90<br>9<br>50<br>50 | No, diff = 1 |

#### Hints and Guidelines

We will first input the number **n**, after that the first **n** numbers (**left** half) and we sum them up. We will then proceed with inputting more **n** numbers (**right** half) and sum them up. We calculate **the difference ** between the sums by absolute value: **`math.fabs(rightSum - leftSum)`**. If the difference is **0**, print **"Yes" + sum**, otherwise print **"No" + the difference **.

![](/assets/chapter-5-1-images/07.Left-and-right-sum-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#6](https://judge.softuni.org/Contests/Practice/Index/1053#6).


### Problem: even / odd sum

Write a program that inputs **n integers** and checks whether **the sum of the numbers on even positions** is equal to **the sum of the numbers on odd positions**. In case the sums are equal, print **"Yes" + sum**, otherwise print **"No" + the difference **. The difference is calculated by absolute value. The format of the output must be identical to the one in the examples below.

#### Sample Input and Output

| Input | Output |
| --- | --- |
| 4<br>10<br>50<br>60<br>20 | Yes<br>Sum = 70 |
| 4<br>3<br>5<br>1<br>-2 | No<br>Diff = 1 |
| 3<br>5<br>8<br>1 | No<br>Diff = 2 |

#### Hints and Guidelines

Input the numbers one by one and calculate the two **sums** (of the numbers on **even** positions and the numbers on **odd** positions). Identically to the previous problem, we calculate the absolute value of the difference and print the result (**"Yes" + sum** in case of difference of 0 or **"No" + the difference ** in any other case):

![](/assets/chapter-5-1-images/08.Odd-even-sum-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#7](https://judge.softuni.org/Contests/Practice/Index/1053#7).


### Problem: sum of vowels

Write a program that inputs **text** (string), calculates and prints **the sum of the values of vowels** according to the table below:

| a | e | i | o | u | 
| :---: | :---: | :---: | :---: | :---: |
| 1 | 2 | 3 | 4 | 5 |

#### Sample Input and Output

| Input | Output | Input | Output | 
| --- | --- | --- | --- |
| hello | 6<br>(e+o = 2+4 = 6) | bamboo | 9<br>(a+o+o = 1+4+4 = 9) |
| hi | 3<br>(i = 3) | beer | 4<br>(e+e = 2+2 = 4) |

#### Hints and guidelines

We read the input text **`line`**, null the sum and run a loop, which goes through each symbol from the text. We check each letter **`c`** and verify if it is a vowel, and accordingly, add its value to the sum:

![](/assets/chapter-5-1-images/09.Vowels-sum-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1053#8](https://judge.softuni.org/Contests/Practice/Index/1053#8).


## What did we learn in this chapter?

We can repeata block of code with **`for` loop**:

![](/assets/chapter-5-1-images/00.For-loop-01.png)

We can read a sequence of **`n`** numbers from the console:

![](/assets/chapter-5-1-images/00.For-loop-03.png)

## Exercises: Repetitions (loops)

Now that we got acquainted with the loops, it's time **to consolidate our knowledge in practice**, and as you know, this is done with a lot of code writing. Let's solve several problems for exercise.

### Creating new project in PyCharm

Create new project in PyCharm (from [**File**] -> [**New Project**]), in order to organise better the exercise tasks. The purpose of this **project** is to contain **one Python file for each task** from the exercises:
  
![](/assets/chapter-5-1-images/00.New-project-PyCharm-01.png)

### Problem: елемент, равен на сумата на останалите

Да се напише програма, която въвежда **n цели числа** и проверява дали сред тях съществува число, което е равно на сумата на всички останали. Ако има такъв елемент, се отпечатва **"Yes" + неговата стойност**, в противен случай - **"No" + разликата между най-големия елемент и сумата на останалите** (по абсолютна стойност). 

#### Примерен вход и изход

| Вход | Изход | Коментар |
| --- | --- | :---: |
| 7<br>3<br>4<br>1<br>1<br>2<br>12<br>1 | Yes<br>Sum = 12 | 3 + 4 + 1 + 2 + 1 + 1 = 12 |
| 4<br>6<br>1<br>2<br>3 | Yes<br>Sum = 6 | 1 + 2 + 3 = 6 |
| 3<br>1<br>1<br>10 | No<br>Diff = 8 | &#124;10 - (1 + 1)&#124; = 8 |
| 3<br>5<br>5<br>1 | No<br>Diff = 1 | &#124;5 - (5 + 1)&#124; = 1 |
| 3<br>1<br>1<br>1 | No<br>Diff = 1 | - |

#### Насоки и подсказки

Трябва да изчислим **сумата** на всички елементи, да намерим **най-големия** от тях и да проверим търсеното условие.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1053#9](https://judge.softuni.org/Contests/Practice/Index/1053#9).


### Задача: четни / нечетни позиции

Напишете програма, която чете **n числа** и пресмята **сумата**, **минимума** и **максимума** на числата на **четни** и **нечетни** позиции (броим от 1). Когато няма минимален / максимален елемент, отпечатайте **"No"**. 

#### Примерен вход и изход

| Вход | Изход | Вход | Изход |
| --- | --- | --- | --- |
| 6<br>2<br>3<br>5<br>4<br>2<br>1 | OddSum=9,<br>OddMin=2,<br>OddMax=5,<br>EvenSum=8,<br>EvenMin=1,<br>EvenMax=4 | 2<br>1.5<br>-2.5 | OddSum=1.5,<br>OddMin=1.5,<br>OddMax=1.5,<br>EvenSum=-2.5,<br>EvenMin=-2.5,<br>EvenMax=-2.5 |
| 1<br>1 | OddSum=1,<br>OddMin=1,<br>OddMax=1,<br>EvenSum=0,<br>EvenMin=No,<br>EvenMax=No | 0 | OddSum=0,<br>OddMin=No,<br>OddMax=No,<br>EvenSum=0,<br>EvenMin=No,<br>EvenMax=No |
| 5<br>3<br>-2<br>8<br>11<br>-3 | OddSum=8,<br>OddMin=-3,<br>OddMax=8,<br>EvenSum=9,<br>EvenMin=-2,<br>EvenMax=11 | 4<br>1.5<br>1.75<br>1.5<br>1.75 | OddSum=3,<br>OddMin=1.5,<br>OddMax=1.5,<br>EvenSum=3.5,<br>EvenMin=1.75,<br>EvenMax=1.75 |
| 1<br>-5 | OddSum=-5,<br>OddMin=-5,<br>OddMax=-5,<br>EvenSum=0,<br>EvenMin=No,<br>EvenMax=No | 3<br>-1<br>-2<br>-3 | OddSum=-4,<br>OddMin=-3,<br>OddMax=-1,<br>EvenSum=-2,<br>EvenMin=-2,<br>EvenMax=-2 |

#### Насоки и подсказки

Задачата обединява няколко предходни задачи: намиране на **минимум**, **максимум** и **сума**, както и обработка на елементите от **четни и нечетни позиции**. Припомнете си ги.

В тази задача е по-добре да се работи с **дробни числа** (не цели). Сумата, минимумът и максимумът също са дробни числа. Трябва да използваме **неутрална начална стойност** при намиране на минимум / максимум, например **1000000000.0** и **-1000000000.0**. Ако получим накрая неутралната стойност, печатаме **"No"**.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1053#10](https://judge.softuni.org/Contests/Practice/Index/1053#10).


### Задача: еднакви двойки

Дадени са **2 \* n числа**. Първото и второто формират **двойка**, третото и четвъртото също и т.н. Всяка двойка има **стойност** – сумата от съставящите я числа. Напишете програма, която проверява **дали всички двойки имат еднаква стойност**. В случай, че е еднаква отпечатайте **"Yes, value=…" + стойността**, в противен случай отпечатайте **максималната разлика** между две последователни двойки в следния формат - **"No, maxdiff=…" + максималната разлика**. Входът се състои от число **n**, следвано от **2*n цели числа**, всички по едно на ред.

#### Примерен вход и изход

| Вход | Изход | Коментар |
| --- | --- | :---: | 
| 3<br>1<br>2<br>0<br>3<br>4<br>-1| Yes, value=3 | стойности = {3, 3, 3}<br>еднакви стойности | 
| 2<br>1<br>2<br>2<br>2 | No, maxdiff=1 | стойности = {3, 4}<br>разлики = {1}<br>макс. разлика = 1 |
| 4<br>1<br>1<br>3<br>1<br>2<br>2<br>0<br>0 | No, maxdiff=4 | стойности = {2, 4, 4, 0}<br>разлики = {2, 0, 4}<br>макс. разлика = 4 |
| 1<br>5<br>5 | Yes, value=10 | стойности = {10}<br>една стойност<br>еднакви стойности |
| 2<br>-1<br>0<br>0<br>-1 | Yes, value=-1 | стойности = {-1, -1}<br>еднакви стойности | 
| 2<br>-1<br>2<br>0<br>-1 | No, maxdiff=2 | стойности = {1, -1}<br>разлики = {2}<br>макс. разлика = 2 |

#### Насоки и подсказки

Прочитаме входните числа **по двойки**. За всяка двойка пресмятаме **сумата** ѝ. Докато четем входните двойки, за всяка двойка, без първата, трябва да пресметнем **разликата с предходната**. За целта е необходимо да пазим в отделна променлива сумата на предходната двойка. Накрая намираме **най-голямата разлика** между две двойки. Ако е **0**, печатаме **"Yes"** + стойността, в противен случай - **"No"** + разликата.

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1053#11](https://judge.softuni.org/Contests/Practice/Index/1053#11).


## Упражнения: графични и уеб приложения

В настоящата глава се запознахме с **циклите** като конструкция в програмирането, която ни позволява да повтаряме многократно дадено действие или група от действия. Сега нека си поиграем с тях. За целта ще начертаем няколко фигурки, които се състоят от голям брой повтарящи се графични елементи, но този път не на конзолата, а в графична среда, използвайки "**графика с костенурка**". Ще е интересно. И никак не е сложно. Опитайте!

### Задача: чертане с костенурка – графично GUI приложение

Целта на следващото упражнение е да си поиграем с една **библиотека за рисуване**, известна като **"графика с костенурка" (turtle graphics)**. Ще изградим графично приложение, в което ще **рисуваме различни фигури**, придвижвайки нашата **"костенурка"** по екрана чрез операции от типа "отиди напред 100 позиции", "завърти се надясно на 30 градуса", "отиди напред още 50 позиции". Приложението ще изглежда приблизително така:

![](/assets/chapter-5-1-images/13.Turtle-graphics-01.png)

Нека първо се запознаем с **концепцията за рисуване "Turtle Graphics"**. Може да разгледаме следните източници:

* Дефиниция на понятието "turtle graphics": [https://wiki.c2.com/?TurtleGraphics](https://wiki.c2.com/?TurtleGraphics)
* Статия за "turtle graphics" в Wikipedia – [https://en.wikipedia.org/wiki/Turtle_graphics](https://en.wikipedia.org/wiki/Turtle_graphics)
* Интерактивен онлайн инструмент за чертане с костенурка – [https://blockly-games.appspot.com/turtle](https://blockly-games.appspot.com/turtle)

Започваме, като създаваме нов **проект с PyCharm**:

![](/assets/chapter-5-1-images/13.Turtle-graphics-02.png)

В новосъздадения проект добавяме нов **Python File**. За чертането ще използваме външната библиотека **`turtle`**. Тя дефинира клас **`Turtle`**, който представлява **костенурка за рисуване**. За да я използваме, добавяме следния код, най-отгоре в началото на Python файла:
  
![](/assets/chapter-5-1-images/13.Turtle-graphics-03.png)

След това, за чертането, добавяме следния код:

![](/assets/chapter-5-1-images/13.Turtle-graphics-04.png)

Горния код мести и върти костенурката, която в началото е в центъра на екрана (в средата на формата), и чертае равностранен триъгълник. Може да го редактирате и да си поиграете с него. **Стартираме** приложението:

![](/assets/chapter-5-1-images/13.Turtle-graphics-05.png)

Сега може да променим и усложним горния код, за да получим по-сложна фигура: 

![](/assets/chapter-5-1-images/13.Turtle-graphics-06.png)

Отново **стартираме** приложението, за да видим резултата:

![](/assets/chapter-5-1-images/13.Turtle-graphics-7.png)

Вече нашата костенурката чертае по-сложни фигури чрез приятно анимирано движение.

### Задача: * чертане на шестоъгълник с костенурката

Добавeте нов Python файл, с примерно име **hexagon**, който ще чертае правилен шестоъгълник:

![](/assets/chapter-5-1-images/13.Turtle-graphics-8.png)

**Подсказка:**

В цикъл повторете 6 пъти следното:
* Ротация на 60 градуса.
* Движение напред 100.

### Задача: * чертане на звезда с костенурката

Добавете нов Python файл **star.py**, който чертае звезда с 5 върха (**петолъчка**), като на фигурата по-долу:

![](/assets/chapter-5-1-images/13.Turtle-graphics-9.png)

**Подсказка:** Сменете цвета: **`my_turtle.color("green")`**. 

В цикъл повторете 5 пъти следното:
* Движение напред 200.
* Ротация на 144 градуса.

### Задача * чертане на спирала с костенурката

Добавете нов Python файл **spiral.py**, който чертае спирала с 20 върха като на фигурата по-долу:

![](/assets/chapter-5-1-images/13.Turtle-graphics-10.png)

**Подсказка:** Чертайте в цикъл, като движите напред и завъртате. С всяка стъпка увеличавайте постепенно дължината на движението напред и завъртайте на 60 градуса.

### Задача: * чертане на слънце с костенурката

Добавете нов Python файл **sun.py**, който чертае слънце с 36 върха като на фигурата по-долу:

![](/assets/chapter-5-1-images/13.Turtle-graphics-11.png)

### Задача: * чертане на спирален триъгълник с костенурката

Добавете нов Python файл **triangle.py**, който чертае три триъгълника с по 22 върха като на фигурата по-долу:

![](/assets/chapter-5-1-images/13.Turtle-graphics-12.png)

**Подсказка:** Чертайте в цикъл като движите напред и завъртате. С всяка стъпка увеличавайте с 10 дължината на движението напред и завъртайте на 120 градуса. Повторете 3 пъти за трите триъгълника.

Ако имате проблеми с примерния проект по-горе, питайте във **форума на СофтУни**: https://softuni.bg/forum.
