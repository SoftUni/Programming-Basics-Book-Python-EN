# Chapter 7.1. Complex loops

Since we have learned what **`for` loops** are and their function in code, now is the time to take a look at **other loop types**, as well as some **more complex loop constructs**. These will expand our knowledge and help us solve more challenging problems. In particular, we will discuss how to use the following programming constructs:

  * loops **with step aka stride**
  * **`while`** loops
  * **`while`** + **`break`** loops
  * **infinite** цикли

In the current chapter, we will also take a look at the **`break`** operator and ** how** to use it to **interrupt** a loop. We will also learn how to process **errors during execution** of the program, using **`try-except`** statement.


## Video

<div class="video-player">
  Watch a video lesson on this chapter here:
  https://www.youtube.com/watch?v=IPJigJNDuKQ.
</div>


## Loops with stride

In the ["Loops (Repetitions)"](/chapter-05-loops.md) chapter we learned how the **`for`**  loop works and we already know when and to what purpose to use it. In the present chapter we will **take a look** at a particular and a very important **part of this structure** - its **step** or as it is also known **stride**.

### Loop with a Step – Explanation

The **stride** is **part** of the **'range'** function, that specifies the **amount** used to **increment** or **decrement** the value of the **main** variable. The step is declared as last argument in the **`range`** function.

By default, range in Python uses a step **value of `1`** and is not added to the **`range`** function. If we want our step to be **different from 1**, when writing the **`range`** function, we add another number as last parameter, which is our step. With a step of **`10`**, the loop would appear as below: 

![](/assets/chapter-7-1-images/00.Step-explanation-01.png)

Here is a series of sample problems, the solution of which will help us better understand the use of a **step** in a **`for`** loop.

### Example: Numbers from 1 to N with a step of 3

Write a program that prints the numbers **from 1 to n** with a **stride of 3**. For example, **if n = 100**, then the output would be: **1, 4, 7, 10, …, 94, 97, 100**.

We can solve the problem using the following sequence of actions (algorithm):

  * We read **`n`** from the console.
  * We run a **`for` loop** from **1** to **`n`** (including **`n`**) with a stride of **3**.
  * In the **body of the loop** we print the value of the current step.
  
![](/assets/chapter-7-1-images/01.Numbers-1-to-n-01.png)

#### Testing in the Judge System

You can test your solution at the following link: [https://judge.softuni.org/Contests/Practice/Index/1057#0](https://judge.softuni.org/Contests/Practice/Index/1057#0).


### Example: Numbers from N to 1 in reverse

Write a program that prints the numbers **from n to 1 in reverse** (step -1). For example, **if n = 100**, then the output will be: **100, 99, 98, …, 3, 2, 1**.

We can solve the problem in the following manner:

  * We read **`n`** from the console.
  * We create a **`for` loop**, from **`n`** to 0.
  * We define the stride size: **-1**.
  * In the **body of the loop** we print the value of the current step.

![](/assets/chapter-7-1-images/02.Numbers-n-to-1-01.png)

#### Testing in the Judge System

You can test your solution at the following link: [https://judge.softuni.org/Contests/Practice/Index/1057#1](https://judge.softuni.org/Contests/Practice/Index/1057#1).


### Example: Numbers from 1 to 2^n with a for loop

In the following example, we will use the standard size 1 stride.

Write a program that prints the numbers **from 1 to 2^n** (two to the power of n). For example, **if n = 10**, then the output would be **1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024**.

![](/assets/chapter-7-1-images/03.Numbers-1-to-2^n-01.png)

#### Testing in the Judge System

You can test your solution at the following link: [https://judge.softuni.org/Contests/Practice/Index/1057#2](https://judge.softuni.org/Contests/Practice/Index/1057#2).


### Example: Even Powers of 2

Print the **even** powers of **2** until **2^n**: **2^0, 2^2, 2^4, 2^8, …, 2^n**. For example, if **n = 10**, then the output would be **1, 4, 16, 64, 256, 1024**.

Here is how we can solve the problem:

  * We declare a variable **`num`** that will hold the current number and we assign it the initial **value of  1**.
  * For the **step** of the loop we set a value of **2**.
  * In the **body of the loop**: we print the value of the current number and **increase the current number `num` 4 times** (as per the problem description).

![](/assets/chapter-7-1-images/04.Even^2-01.png)

#### Testing in the Judge System

You can test your solution at the following link: [https://judge.softuni.org/Contests/Practice/Index/1057#3](https://judge.softuni.org/Contests/Practice/Index/1057#3).


## While loop

The next type of loops that we will familiarize, which are called **`while` loops**. The special thing about them is that they repeat a command block, **while a condition is met**. Their structure is a bit different than that of the **`for`** loops, however, they boast a simpler syntax.


### While Loop – Explanation

In programming, the **`while` loop** is used when we want to **repeat** the execution of a specific logic block until **a specific condition is met**. Any expression that returns either **`true`** или **`false`** (a Boolean) can be used as a "**condition**". When the **condition** becomes **invalid**, the **`while`** loop **is interrupted** and the program **proceeds** to execute the code after the loop. The **`while` loop** structure looks like this:

![](/assets/chapter-7-1-images/00.While-loop-01.png)

Here is a series of sample problems, the solutions of which will help us better understand the use of the **`while`** loop.


### Example: Sequence of Numbers 2k+1

Write a program that prints **all numbers ≤ n** in the series: **1, 3, 7, 15, 31, …**, assuming that each number is generated according to the following formula next_number = **previous_number \* 2 + 1**.

Here is how we can solve the problem:

* We declare a variable **`num`** that will hold the current number and we assign it the initial **value of 1**.
* For loop condition, we use **the current number <= n**.
* In the **body of the loop**: we print the value of the current number and increase the current number by using the formula above.

Here is a sample implementation of this idea:

![](/assets/chapter-7-1-images/05.Numbers-2k+1-01.png)
 
#### Testing in the Judge System

You can test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#4](https://judge.softuni.org/Contests/Practice/Index/1057#4).


### Example: Number in Range [1 … 100]

Enter an integer in the range [**1 … 100**]. If the entered number is **invalid**, enter **again**. In this case, an invalid number would be any number that is **outside** the given range.

To solve the problem, we can use the following algorithm:

* We declare a variable **`num`**, to which we assign the integer part of the first argument, received from the console.
* For a loop condition, we put a **`True`** expression, if the number **is not** in the range specified in the problem description.
* In the **body of the loop**: we print the message "**Invalid number!**" on the console, afterwards we assign a new value to **`num`** (the next line from the console input).
* Once we have validated the entered number,we print its value outside the body of the loop.

Here is a sample implementation of the algorithm using a **`while` loop**:

![](/assets/chapter-7-1-images/06.Numbers-in-range-1..100-01.png)

#### Testing in the Judge System

You can test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#5](https://judge.softuni.org/Contests/Practice/Index/1057#5).


## Greatest Common Divisor (GCD)

Before proceeding to the next problem, we should become familiar with the definition of **the greatest common divisor** (**GCD**).

**Definition of GCD**: the greatest common divisor of two **natural** numbers **a** and **b** is the largest number that **divides both** **a** and **b** without reminder. For example:


|a|b|GCD| 
|:---:|:---:|:---:| 
|24|16|8|
|67|18|1|
|12|24|12|
|15|9|3|
|10|10|10|
|100|88|4|

## The Euclidean Algorithm

In the next problem we will use one of the first published algorithms for finding the GCD - **Euclid's algorithm**:

**Until** we have a remainder of 0:

* We divide the greater number by the smaller one.
* We take the remainder of the division.

Euclid's algorithm **pseudo-code**:

```python
while b ≠ 0
  oldB = b
  b = a % b
  a = oldB
print а
```

### Example: Greatest Common Divisor (GCD)

Enter the **integers** **a** and **b** and find **GCD(a, b)**.

We will solve the problem by implementing **Euclid's algorithm**:

* We declare variables **`a`** and **`b`**, to which we assign the **integer** values, passed by the console input.
* For loop condition, we use a **`True`** expression, if the number **`b`** **is different** than **0**.
* In the **body of the loop** we follow the instructions from the pseudo-code:
   * We create a temporary variable to which we assign the **current** value of **`b`**.
   * We assign a new value to **`b`**, which is the remainder of the division of **`a`** and **`b`**.
   * On variable **`a`** we assign the **previous** value of the variable **`b`**.
* Once the loop is complete and we have found the GCD, we print it on the screen.

![](/assets/chapter-7-1-images/07.GCD-01.png)

#### Testing in the Judge System

You can test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#6](https://judge.softuni.org/Contests/Practice/Index/1057#6).


## While True + break цикъл

The next type of loop construction that we will be familiar with while studying programming is the `while True` + `break` loop (for short `while` + `break` loop). Its idea **is to repeat a block of code** over and over again until **explicit termination of the loop**, usually after a `if` statement in the body of the loop. Here's what this loop looks like in Python code:

![](/assets/chapter-7-1-images/00.Do-while-01.png)

The above example is called “**inverted `while` loop**”, because the condition for exiting the loop is at the end, not at the beginning. In essence, the above construction is an “infinite loop” with a check, of a given condition, for an exit inside the body of the cycle.

In programming, the `break` operator unconditionally terminates a loop and proceeds to the first instruction after it. In the example above, a condition is checked at the end of the cycle, and if it is not true, the cycle is terminated.

The construct for the `while` + `break` loop in many other programming languages is implemented with the `do-while` construct, but there is no direct equivalent of `do-while` in Python. In order to do the same in Python, we can use an infinite loop (`while True`) and when an exit condition is reached, the loop is interrupted (with `break`).

The `while` + `break` construct provides more flexibility than `while` loops, because it allows to break the loop at **any place** in the body of the loop(for example at the beginning, in the middle or at the end), it even allows to have exit of the loop in several different places (with several `break` operators).

The structure of `while` + `break` loop is very similar to the classic `while` loop, but there is a significant difference: `while` is executed 0 or more times (according to the entry condition of the loop), whilst `while` + `break` will execute its body **at least once**. Why is this? In the `while True` + `break` loop structure, the **condition** is always checked **in the body of the loop**, whilst with the classic `while` loop the condition, which we check to exit the loop is always at the begginning, before its body.

Once we are familiar with the concept of a `while` + `break` loop with an exit condition, which is not required to be at the beginning, now we should proceed with the usual set of practical problems, with which we can master the new knowledge.

### Example: Calculating Factorial

For natural **n** number calculate **n! = 1 \* 2 \* 3 \* … \* n**. For example, if **n = 5**, then the result would be: **5!** = 1 \* 2 \* 3 \* 4 \* 5 = **120**.

Here is how we can calculate factorial in more detail:

* We declare the variable **`n`**, to which we assign the integer value, received from the input of the console.
* We declare another variable - **`fact`**, with an initial value of 1. We will use it in the calculation and store the factorial value.
* For the loop condition we will use **`n > 1`**,  because each time we perform the calculations in the body of the loop, we willdecrease the value of **`n`** by 1.
* In the body of the loop:
   * We assign a new value to **`fact`**, which value is the product of multiplying the current **`fact`** with the current **`n`**.
   * We decrement на **`n`** with **1**.
* Outside the body of the loop we print the final factorial value.

![](/assets/chapter-7-1-images/08.Factorial-01.png)

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#7](https://judge.softuni.org/Contests/Practice/Index/1057#7).


### Example: Summing the Digits of a Number

Sum up the digits of the integer **positive** number **n**. For example, if **n = 5634**, then the output would bе: 5 + 6 + 3 + 4 = **18**.

We can use the following idea to solve the problem:

* We declare the variable **`n`**, to which we assign a value equal to the number received by the user.
* We create a second variable - **`sum`**, with an initial value of 0. We will use it for the calculation and storage of the result.
* As a loop condition, we will use **`n > 0`**, since, after each iteration of the loop, we will be removing the last digit from **`n`**.
* In the body of the loop:
   * We assign a new value to **`sum`**, which is the result of the sum of the current value of **`sum`** with the last digit of **`n`**.
   * We assign a new value to **`n`**,  which is the result of removing the last digit of **`n`**.
* utside the body of the loop, we print the final value of the sum.

![](/assets/chapter-7-1-images/09.Sum-digits-01.png)

<table><tr><td><img src="assets/alert-icon.png" style="max-width:50px;" /></td>
<td><code><strong>n % 10</strong></code>: <b>returns</b> the last digit of the number <code><strong>n</strong></code>.<br>
<code><strong>n // 10</strong></code>: <b>deletes</b> the last digit of <code><strong>n</strong></code>.</td>
</tr></table>

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#8](https://judge.softuni.org/Contests/Practice/Index/1057#8).


## Infinite loops and the operator break

So far, we were introduced to various types of loops, learning what structures they have and how they are applied. Now, we need to understand what an **infinite loop** is, when it occurs, and how we can **break** it using the **`break`** operator.

### Infinite Loop – Explanation

An **infinite loop** **runs infinitely** the code of its body. With the infinite **`while`** loops the end check is a conditional expression that **always** returns **`true`**. Here is an example of an **infinite `while`** loop:

![](/assets/chapter-7-1-images/00.Infinite-while-loop-01.png)


### The Break Operator

We already know that the infinite loop executes a certain code infinitely, but what if we want at some point under a given condition to interrupt and exit the loop? The **`break`** operator comes in handy in this situation.

<table><tr><td><img src="assets/alert-icon.png" style="max-width:50px" /></td>
<td>The operator <b><code>break</code></b> stops a loop's execution at the point it is called and the execution continues from the first line after the end of the loop. This means that the current iteration of the loop will not be completed accordingly and the rest of the code in the body of the loop will not be executed.</td>
</tr></table>

### Example: Prime Number Checking

The next problem we are going to solve is to **check whether a given number is prime**, but before that, we should remember what are prime numbers.

**Definition**: An integer is considered **prime**, if it is divisible only by itself and by 1. By definition, the prime numbers are positive and greater than 1. The smallest prime number is **2**.

We can assume that an integer **n** is a prime number if **n > 1** and **n** is not divisible by a number between **2** and **n-1**.

The first few prime numbers are: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, …

By contrast, **composite numbers** are integers, which can be obtained by multiplying several prime numbers.

Here are some examples of composite numbers: 
* **10** = 2 \* 5
* **42** = 2 \* 3 \* 7
* **143** = 13 \* 11

**An algorithm to check** whether a given number is **prime**: we check if **n > 1** and if **n** is divisible by **2**, **3**, …, **n-1** without remainder.
* If it is divisible by any of the numbers, it is **composite**.
* If it is not divisible by any of the numbers, then it is **prime**.

<table><tr><td><img src="assets/alert-icon.png" style="max-width:50px" /></td>
<td>We can optimize the algorithm by instead of checking until <code><strong>n-1</strong></code>, checking divisors only until <code><strong>√n</strong></code>. Think of the reasons why this is so.</td>
</tr></table>

### Example: check for a prime number. Break operator

You are tasked to write a function that takes a single input **n** integer and checks if it is prime. This can be implemented by checking if **n** is divisible by any numbers in the range between 2 and √n.

The steps of the **"prime checking algorithm"** are given below in bigger detail:

* We declare the variable **`n`**, to which we assign the integer passed by the console.
* We create a **`is_prime`** boolean with and an initial value of **`True`**. We assume that a number is prime until proven otherwise.
* We create a **`for`** loop, with the initial value set to 2, for a condition the **current value `<= √n`**. The stride is set to 1.
* In the **body of the loop** we check if **`n`**, divided by the **current value** has a remainder. If there is **no reminder** from the division, then we change **`is_prime`** to **`False`** and exit the loop through the **`break`** operator.
* Depending on the value of **`is_prime`** we print whether the input number is prime (**`True`**) or composite (**`False`**).

Here is a sample implementation of the prime checking algorithm, described above:

![](/assets/chapter-7-1-images/10.Check-if-prime-01.png)

What remains is to add a **condition that checks if the input number is greater than 1**, because, by definition numbers such as 0, 1, -1 and -2 are not prime.

#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#9](https://judge.softuni.org/Contests/Practice/Index/1057#9).


### Example: the break operator in an infinite loop

Write a function, which checks whether a given number **n**is even and if so - print it on the console. An even number can be divided by 2 without a remainder. If the number is invalid, we will print that the current number is not even and the user will need to input a new number.

Here is an idea for the solution:

* We declare a variable **`n`**, with an initial value of **0**.
* We create an infinite **`while`** loop, with a condition set to **`True`**.
* In **the body of the loop**:
   * We take the integer value, passed to our function, and assign it to **`n`**.
   * If **the number is even**, we exit the loop by a **`break`**. 
   * **Otherwise**, we print a message stating that **the number is not even**. Iterations continue, until an even number is entered.
* We print the even number on the console.

Here is an example implementation of the idea:

![](/assets/chapter-7-1-images/00.Break-in-infinite-loop-01.png)

Note: although the code above is correct, it will not work if the user enters text instead of a number, for example "**Invalid number**". Then the parse of the text to a number will break and the program will display **error message (exception)**. We will learn in a little time how to deal with this problem and how to catch and handle exceptions using the **`try-except` construct**.
#### Testing in the Judge System

Test your solution here: [https://judge.softuni.org/Contests/Practice/Index/1057#10](https://judge.softuni.org/Contests/Practice/Index/1057#10).


## Вложени цикли и операторът break

След като вече научихме какво са **вложените цикли** и как работи операторът **`break`**, е време да разберем как работят двете заедно. За по-добро разбиране, нека стъпка по стъпка да напишем **програма**, която трябва да направи всички възможни комбинации от **двойки числа**. Първото число от комбинацията е нарастващо от 1 до 3, а второто е намаляващо от 3 до 1. Задачата трябва да продължи изпълнението си, докато **`i + j`** **не** е равно на 2 (т.е. **`i = 1`** и **`j = 1`**).

Желаният резултат е:

![](/assets/chapter-7-1-images/00.Nested-and-break-desired-result-01.png)

Ето едно **грешно решение**, което изглежда правилно на пръв поглед:

![](/assets/chapter-7-1-images/00.Nested-and-break-desired-result-02.png)

Ако оставим програмата ни по този начин, резултатът ни ще е следният:

![](/assets/chapter-7-1-images/00.Nested-and-break-undesired-result-01.png)

Защо се получава така? Както виждаме, в резултата **липсва "1 1"**. Когато програмата стига до там, че **`i = 1`** и **`j = 1`**, тя влиза в **`if`** проверката и изпълнява **`break`** операцията. По този начин се **излиза от вътрешния цикъл**, но след това продължава изпълнението на външния. **`i`** нараства, програмата влиза във вътрешния цикъл и принтира резултата.

<table><tr><td><img src="/assets/alert-icon.png" style="max-width:50px" /></td>
<td>Когато във <b>вложен цикъл</b> използваме оператора <b><code>break</code></b>, той прекъсва изпълнението <b>само</b> на вътрешния цикъл.</td>
</tr></table>

Какво е **правилното решение**? Един начин за решаването на този проблем е чрез деклариране на **`bool` променлива**, която следи за това, дали трябва да продължава въртенето на цикъла. При нужда от изход (излизане от всички вложени цикли), се променя стойността на променливата на **`True`** и се излиза от вътрешния цикъл с **`break`**, а при последваща проверка се напуска и външния цикъл. Ето и примерна имплементация на тази идея:

![](/assets/chapter-7-1-images/00.Nested-and-break-undesired-result-02.png)

По този начин, когато **`i + j = 2`**, програмата ще направи променливата **`has_to_end = True`** и ще излезе от вътрешния цикъл. При следващото завъртане на външния цикъл, чрез **`if`** проверката, програмата няма да може да стигне до вътрешния цикъл и ще прекъсне изпълнението си.

### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1057#11](https://judge.softuni.org/Contests/Practice/Index/1057#11).

## Справяне с изключения: try-except

Последното, с което ще се запознаем в тази глава, е как да "улавяме" **грешки (exceptions)** чрез конструкцията **`try-except`**.

### Какво е try-except?

Програмната конструкция **`try-except`** служи за **прихващане и обработка на изключения (грешки)** по време на изпълнението на програмата.

В програмирането **изключенията (exceptions)** представляват уведомление за дадено събитие, което нарушава нормалната работа на една програма. Такива събития **прекъсват изпълнението** на програмата и тя търси кой да обработи настъпилата ситуация. Ако не намери, изключението се отпечатва на конзолата (т.е. програмата "гърми"). Ако намери, **изключението се обработва** и програмата продължава нормалното си изпълнение, без да "гърми". След малко ще видим как точно става това.

### Конструкция на try-except

Конструкцията **`try-except`** има различни варианти, но за сега ще се запознаем само с най-основния от тях: 

 ![](/assets/chapter-7-1-images/00.Try...except-01.png)



В следващата задача ще видим нагледно, как да се справим в ситуация, в която потребителят въвежда вход, различен от число (например **`string`** вместо **`int`**), чрез **`try-except`**.

### Пример: справяне с невалидни числа чрез try-except

Да се напише програма, която проверява дали едно число **n** е четно и ако е, да се отпечата на екрана. При **невалидно въведено** число да се изписва съобщение, че въведения вход не е валидно число и въвеждането да продължи отново.

Ето как можем да решим задачата:

* Създаваме безкраен **`while`** цикъл, като за условие ще зададем **`True`**.
* В тялото на цикъла:
	* Създаваме **`try-except`** конструкция.
	* В **`try`** блока пишем програмната логика за четене на потребителския вход, парсването му до число и проверката за четност.
	* При **четно число** го отпечатваме и излизаме от цикъла (с **`break`**). Програмата си е свършила работата и приключва.
	* При **нечетно число** отпечатваме съобщение, че се изисква четно число, без да излизаме от цикъла (защото искаме той да се повтори отново).
	* Ако **хванем изключение** при изпълнението на **`try`** блока, изписваме съобщение за невалидно въведено число (и цикълът съответно се повтаря, защото не излизаме изрично от него).

Ето и примерна имплементация на описаната идея:

![](/assets/chapter-7-1-images/11.Wrong-numbers-try-except-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1057#10](https://judge.softuni.org/Contests/Practice/Index/1057#10).

Сега вече решението трябва да работи винаги: независимо дали въвеждаме цели числа, невалидни числа (например твърде много цифри) или текст, които не съдържат числа.


## Задачи с цикли

В тази глава се запознахме с няколко нови вида цикли, с които могат да се правят повторения с по-сложна програмна логика. Да решим няколко задачи, използвайки новите знания.

### Задача: числа на Фибоначи

Числата на Фибоначи в математиката образуват редица, която изглежда по следния начин: **1, 1, 2, 3, 5, 8, 13, 21, 34, …**.

**Формулата** за образуване на редицата е:

```python
F0 = 1
F1 = 1
Fn = Fn-1 + Fn-2
```

#### Примерен вход и изход

|Вход (n)|Изход|Коментар|
|----|-----|---------|
|10|89|F(11) = F(9) + F(8)|
|5|8|F(5) = F(4) + F(3)|
|20|10946|F(20) = F(19) + F(18)|
|0|1| |
|1|1| |

Да се въведе **цяло** число **n** и да се пресметне **n-тото число на Фибоначи**.

#### Насоки и подсказки

Идея за решаване на задачата:

* Създаваме **променлива `n`**, на която присвояваме целочислена стойност от входа на конзолата.
* Създаваме променливите **`f0`** и **`f1`**, на които присвояваме стойност **1**, тъй като така започва редицата.
* Създаваме **`for`** цикъл от нула до **крайна стойност `n - 1`**.
* В **тялото на цикъла:**
   * Създаваме **временна** променлива **`f_next`**, на която присвояваме следващото число в поредицата на Фибоначи.
   * На **`f0`** присвояваме текущата стойност на **`f1`**.
   * На **`f1`** присвояваме стойността на временната променлива **`f_next`**.
* Извън цикъла отпечатваме числото n-тото число на Фибоначи.

Примерна имплементация:

![](/assets/chapter-7-1-images/12.Fibonacci-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1057#12](https://judge.softuni.org/Contests/Practice/Index/1057#12).


### Задача: пирамида от числа

Да се отпечатат **числата 1 … n в пирамида** като в примерите по долу. На първия ред печатаме едно число, на втория ред печатаме две числа, на третия ред печатаме три числа и т.н. докато числата свършат. На последния ред печатаме толкова числа, колкото останат докато стигнем до **n**.

#### Примерен вход и изход

|Вход |Изход                 |Вход |Изход          |Вход      |Изход                         |
|-----|----------------------|-----|---------------|----------|------------------------------|
|7    |1<br>2 3<br>4 5 6<br>7|5    |1<br>2 3<br>4 5|10        |1<br>2 3<br>4 5 6<br>7 8 9 10 |

#### Насоки и подсказки

Можем да решим задачата с **два вложени цикъла** (по редове и колони) с печатане в тях и излизане при достигане на последното число. Ето идеята, разписана по-подробно:

* Създаваме променлива **`n`**, на която присвояваме целочислена стойност, прочетена от конзолата.
* Създаваме променлива **`num`** с начална стойност 1. Тя ще пази броя на отпечатаните числа. При всяка итерация ще я **увеличаваме** с **1** и ще я принтираме.
* Създаваме **външен** **`for`** цикъл, който ще отговаря за **редовете** в таблицата. Наименуваме променливата на цикъла **`row`** и ѝ задаваме начална стойност 1. За крайна стойност слагаме **`n + 1`**.
* В тялото на цикъла създаваме **вътрешен** **`for`** цикъл, който ще отговаря за **колоните** в таблицата. Наименуваме променливата на цикъла **`col`** и ѝ задаваме начална стойност 1. За условие слагаме **`row + 1`** (**`row`** = брой цифри на ред).
* В тялото на вложения цикъл:
   * Проверяваме дали **`col > 1`**, ако да – принтираме разстояние. Ако не направим тази проверка, а директно принтираме разстоянието, ще имаме ненужно такова в началото на всеки ред.
   * **Отпечатваме** числото **`num`** в текущата клетка на таблицата и го **увеличаваме с 1**.
   * Правим проверка за **`num > n`**. Ако **`num`** е по-голямо от **`n`**, **прекъсваме** въртенето на **вътрешния цикъл**.
* Отпечатваме **празен ред**, за да преминем на следващия.
* Отново проверяваме дали **`num > n`**. Ако е по-голямо, **прекъсваме** изпълнението на **програмата ни** чрез **`break`**. 

Ето и примерна имплементация:

![](/assets/chapter-7-1-images/13.Pyramid-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1057#13](https://judge.softuni.org/Contests/Practice/Index/1057#13).


### Задача: таблица с числа

Да се отпечатат числата 1 … n в таблица като в примерите по-долу.

#### Примерен вход и изход

|Вход |Изход|Вход|Изход|
|--------|-----|-------|-----|
|3|1 2 3<br>2 3 2<br>3 2 1|4|1 2 3 4<br>2 3 4 3<br>3 4 3 2<br>4 3 2 1|

#### Насоки и подсказки

Можем да решим задачата с **два вложени цикъла** и малко изчисления в тях:

* Четем от конзолата размера на таблицата в целочислена променлива **`n`**.
* Създаваме **`for`** цикъл, който ще отговаря за редовете в таблицата. Наименуваме променливата на цикъла **`row`** и ѝ задаваме начална **стойност 0**. За крайна стойност слагаме **`n`**. Размерът на стъпката е 1.
* В **тялото на цикъла** създаваме вложен **`for`** цикъл, който ще отговаря за колоните в таблицата. Наименуваме променливата на цикъла **`col`** и ѝ задаваме начална **стойност 0**. За крайна стойност слагаме **`n`**. Размерът на стъпката е 1.
* В **тялото на вложения цикъл**:
   * Създаваме променлива **`num`**, на която присвояваме резултата от **текущият ред + текущата колона + 1** (+1, тъй като започваме броенето от 0).
   * Правим проверка за **`num > n`**. Ако **`num`** е **по-голямо** от **`n`**, присвояваме нова стойност на **`num`** равна на **два пъти **`n`** - текущата стойност за **`num`**. Това правим с цел да не превишаваме **`n`** в никоя от клетките на таблицата.
    * Отпечатваме числото от текущата клетка на таблицата.
* Отпечатваме **празен ред** във външния цикъл, за да преминем на следващия ред.

Ето и примерна имплементация на описаната идея:

![](/assets/chapter-7-1-images/14.Table-with-numbers-01.png)

#### Тестване в Judge системата

Тествайте решението си тук: [https://judge.softuni.org/Contests/Practice/Index/1057#14](https://judge.softuni.org/Contests/Practice/Index/1057#14).


## Какво научихме от тази глава?

Можем да използваме **`for`** цикли със **стъпка**:

```python
for i in range(1, n + 1, 3):
    print(i)
```

Циклите **`while`** се повтарят докато е в сила дадено **условие**:

```python
num = 1
while num <= n:
   print(num)
   num += 1
```

Ако се наложи да **прекъснем** изпълнението на цикъл, го правим с оператора **`break`**:

```python
n = 0
while True:
   n = int(input())
   if n % 2 == 0:
      break # even number -> exit from the loop
   print("The number is not even.")
print("Even number entered: {}".format(n))
```

Вече знаем как да прихващаме **грешки** по време на изпълнението на програмата ни:

```python
try:
   print("Enter even number: ", end="")
   n = int(input())
except ValueError:
   print("Invalid number.")
# Ако int(…) гръмне, ще се изпълни except блокът
```


## Упражнения: уеб приложения с по-сложни цикли

Сега вече знаем как да повтаряме група действия, използвайки **цикли**. Нека направим нещо интересно: **уеб базирана игра**. Да, истинска игра, с графика, с гейм логика. Да се позабавляваме. Ще бъде сложно, но ако не разберете нещо как точно работи, няма проблем. Сега още навлизаме в програмирането. Има време, ще напреднете с технологиите. Засега следвайте стъпките.

### Задача: уеб игра "Обстреляй плодовете!"

**Условие**: Да се разработи **Flask уеб приложение** – игра, в която играчът **стреля по плодове**, подредени в таблица. Успешно уцелените плодове изчезват, а играчът получава точки за всеки уцелен плод. При уцелване на **динамит**, плодовете се взривяват и играта свършва (както в игри като Fruit Ninja). Стрелбата се извършва по колони, отгоре надолу или отдолу нагоре, а местоположението на удара (колоната под обстрел) се задава чрез скролер (scroll bar). Заради неточността на скролера, играчът не е съвсем сигурен по коя колона ще стреля. Така при всеки изстрел има шанс да не улучи и това прави играта по-интересна (подобно на прашката в Angry Birds).

Играта ни трябва да изглежда по този начин:

![](/assets/chapter-7-1-images/15.Fruits-01.png) 

![](/assets/chapter-7-1-images/15.Fruits-02.png)

Следват стъпките за имплементация на уеб приложението "Обстреляй плодовете!".

### Празно PyCharm решение

Създаваме празно решение в PyCharm, за да организираме кода от приложението:

![](/assets/chapter-7-1-images/15.Blank-Python-project-01.png)

След това, задаваме смислено име на проекта, например "**Fruits-Web-Game**". Също така, задаваме Python интерпретатора на този по подразбиране:

![](/assets/chapter-7-1-images/15.Blank-Python-project-02.png)

Ще създадем нашето уеб приложение, ползвайки библиотеката **Flask**, с която вече се запознахме. Както вече знаем, преди да започнем да пишем код, трябва да я инсталираме. Отиваме в настройките на PyCharm [**File**] -> [**Settings**] и след това в [**Project: Fruit-Web-Game**] -> [**Project Interpreter**]. Там, натискаме бутона **`+`**, търсим и инсталираме **`Flask`**.

Сега трябва да вземем структурата на проекта от предоставените ни ресурси.

След това, добавяме **ресурсите** за играта (те са част от файловете със заданието за този проект и могат да бъдат свалени от [тук](https://github.com/SoftUni/Programming-Basics-Book-CSharp-Python/tree/master/assets/chapter-7-1-assets)). Копираме ги от Windows Explorer и ги поставяме в папката на проекта в PyCharm с **copy/paste**. След като поставим ресурсите, структурата на проекта трябва да изглежда така:

![](/assets/chapter-7-1-images/15.Fruits-06.png)

Ако отворим **app.py** и го пуснем с десен бутон -> [**Run 'app'**], би трябвало да се отвори приложението, след което да натиснем върху линка в конзолата и да се отвори нашия уеб браузър:

![](/assets/chapter-7-1-images/15.Fruits-07.png)

Сега създаваме контролите за играта. Целта е да добавим **скролиращи ленти** (scroll bars), с които играчът да се прицелва, и бутон за стартиране на **нова игра**. Затова трябва да редактираме файла **templates/index.html**. Изтриваме "**Hello World**" и на негово място въвеждаме следния код:
  
![](/assets/chapter-7-1-images/15.Fruits-08.png)

Този код създава уеб форма **`<form>`** със скролер (поле) **`position`** за задаване на число в интервала [**0 … 100**] и бутон [**Fire Top**] за изпращане на данните от формата към сървъра. Действието, което ще обработи данните, се казва **`/FireTop`**, което означава функция **`fire_top()`**, която се намира във файла **app.py**. Следват още две подобни форми с бутони [**Fire Bottom**] и [**New Game**].

Сега трябва да подготвим плодовете за рисуване в изгледа (view). Добавяме следния код в **app.py** файла:

![](/assets/chapter-7-1-images/15.Fruits-09.png) 

Горният код дефинира полета за **брой редове, брой колони**, за **таблицата с плодовете** (игралното поле), за натрупаните от играча **точки** и информация дали играта е активна или е **свършила** (поле **`gameOver`**). Игралното поле е с размери 9 колони на 3 реда и съдържа за всяко поле текст какво има в него: **`apple`, `banana`, `orange`, `kiwi`, `empty` или `dynamite`**. Главното действие **`index()`** подготвя игралното поле за чертане като записва елементите на играта и извиква изгледа, който ги чертае в страницата на играта (в уеб браузъра като HTML).

Трябва да генерираме случайни плодове. За да направим това, трябва да напишем метод **`generate_random_fruits()`** с кода от картинката по-долу. Този код записва в таблицата (матрицата) **`fruits`** имена на различни картинки и така изгражда игралното поле. Във всяка клетка от таблицата се записва една от следните стойности: **`apple`, `banana`, `orange`, `kiwi`, `empty` или `dynamite`**. След това, за да се нарисува съответното изображение в изгледа, към текста от таблицата ще се долепи **`.png`** и така ще се получи името на файла с картинката, която да се вмъкне в HTML страницата като част от игралното поле. Попълването на игралното поле (9 колони с по 3 реда) става в изгледа **`index.html`**, с два вложени **`for`** цикъла (за ред и за колона).

За да се генерират случайни плодове, за всяка клетка се генерира **случайно число** между 0 и 8 (вж. класа **`random`** в Python). Ако числото e 0 или 1, се слага **`аpple`**, ако е между 2 и 3, се слага **`banana`** и т.н. Ако числото е 8, се поставя **`dynamite`**. Така плодовете се появяват 2 пъти по-често отколкото динамита. Ето и кода:

![](/assets/chapter-7-1-images/15.Fruits-10.png)

Чертане на плодовете в **`index.html`**:

За да **попълним игралното поле** с плодовете, трябва да завъртим **два вложени цикъла** (за редовете и за колоните). Всеки ред се състои от 9 на брой картинки, всяка от които съдържа **`apple`, `banana`** или друг плод, или празно поле **`empty`**, или **`dynamite`**. Картинките се чертаят като се отпечата HTML таг за вмъкване на картинка: **`<img src="/images/apple.png" />`**. Девет картинки се подреждат една след друга на всеки от редовете, а след тях се преминава на нов ред с **`<br>`**. Това се повтаря три пъти за трите реда. Накрая се отпечатват точките на играча. Ето как изглежда **кодът** за чертане на игралното поле и точките:

![](/assets/chapter-7-1-images/15.Fruits-11.png)

Обърнете внимание на къдравите скоби – те служат за превключване между езика **HTML** и езика **Python** и идват от **Jinja2** синтаксиса за рисуване на динамични уеб страници.

Стартираме проекта с [**Shift+F10**]. Очаква се да бъде генерирано случайно игрово поле с плодове с размери 9 на 3 и да се визуализира в уеб страницата чрез поредица картинки:

![](/assets/chapter-7-1-images/15.Fruits-12.png)

Сега играта е донякъде направена: игралното поле се генерира случайно и се визуализира успешно (ако не сте допуснали грешка някъде). Остава да реализираме същината на играта: **стрелянето по плодовете**.

За целта добавяме действията [**New Game**], [**Fire Top**] и [**Fire Bottom**] във файла **app.py**:

![](/assets/chapter-7-1-images/15.Fruits-13.png) 

Чрез горния код дефинираме три действия:
*	**`reset()`** – стартира нова игра, като генерира ново случайно игрално поле с плодове и експлозиви, нулира точките на играча и прави играта валидна **(`gameOver = false`)**. Това действие е доста просто и може да се тества веднага с [**Shift+F10**], преди да се напишат другите.
*	**`fire_top()`** – стреля по ред **0** на позиция **`position`** (число от 0 до 100), взета от потребителя. Извиква се стреляне в посока **надолу** (+1) от ред **0** (най-горния). Самото стреляне е по-сложно като логика и ще бъде разгледано след малко.
*	**`fire_bottom()`** – стреля по ред **2** на позиция **`position`** (число от 0 до 100), взета от потребителя. Извиква се стреляне в посока **нагоре** (-1) от ред **2** (най-долния).

Имплементираме "стрелянето" – метода **`fire(position, start_row, step)`**:

![](/assets/chapter-7-1-images/15.Fruits-14.png)

Стрелянето работи по следния начин: първо се изчислява номера на колоната **`col`**, към която играчът се е прицелил. Входното число от скролера (между 0 и 100) се намаля до число между 0 и 8 (за всяка от 9-те колони). Номерът на реда **row** е или 0 (ако изстрелът е отгоре) или броят редове минус едно (ако изстрелът е отдолу). Съответно посоката на стрелба (стъпката) е **1** (надолу) или **-1** (нагоре).

За да се намери къде изстрелът поразява плод или динамит, се преминава в цикъл през всички клетки от игралното поле в прицелената колона и от първия до последния атакуван ред. Ако се срещне плод, той изчезва (замества се с **`empty`**) и се дават точки на играча. Ако се срещне **`dynamite`**, играта се отбелязва като свършила.

Оставаме на по-запалените читатели да имплементират по-сложно поведение, например да се дават различни точки при уцелване на различен плод, да се реализира анимация с експлозия (това не е твърде лесно), да се взимат точки при излишно стреляне в празна колона и подобни.

**Тестваме** какво работи до момента като стартираме приложението с [**Ctrl + Shift + F10**]:
*	**Нова игра** &rarr; бутонът за нова игра трябва да генерира ново игрално поле със случайно разположени плодове и експлозиви и да нулира точките на играча.
*	**Стреляне отгоре** &rarr; стрелянето отгоре трябва да премахва най-горния плод в уцелената колона или да предизвиква край на играта при динамит. Всъщност при край на играта все още нищо няма да се случва, защото в изгледа този случай още не се разглежда.
* **Стреляне отдолу** &rarr; стрелянето отдолу трябва да премахва най-долния плод в уцелената колона или да прекратява играта при уцелване на динамит.

![](/assets/chapter-7-1-images/15.Fruits-01.png)
 
За момента при **"Край на играта"** нищо не се случва. Ако играчът уцели динамит, в приложението се отбелязва, че играта е свършила **(`game_оver = Тrue`)**, но този факт не се визуализира по никакъв начин. За да заработи приключването на играта, е необходимо да добавим няколко проверки в изгледа:

![](/assets/chapter-7-1-images/15.Fruits-15.png)

Кодът по-горе проверява дали е свършила играта и показва съответно контролите за стреляне и игралното поле (при активна игра) или картинка с експлодирали плодове при край на играта.

След промяната в кода на изгледа стартираме с [**Ctrl + Shift + F10**] и **тестваме** играта отново:

![](/assets/chapter-7-1-images/15.Fruits-16.png)

Този път при уцелване на динамит, трябва да се появи дясната картинка и да се позволява единствено действието "нова игра" (бутонът [**New Game**]).

Сложно ли беше? Успяхте ли да направите играта? Ако не сте успели, не се притеснявайте, това е сравнително сложен проект, който включва голяма доза неизучавана материя. Ако срещнете някакви затруднения, може да питате във **форума на СофтУни**: https://softuni.bg/forum.
