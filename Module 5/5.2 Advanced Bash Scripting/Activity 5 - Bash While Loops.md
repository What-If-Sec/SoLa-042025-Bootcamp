## Activity Objective

The objective of this activity is to help students understand and effectively use Bash while loops in various scenarios. By the end of the activity, students should be able to:
1. Recognize and implement the syntax of while loops in Bash.
2. Understand and apply the different use cases for while loops, such as iterating based on conditions or repeated user input.
3. Identify scenarios where a while loop is more appropriate than a for loop and vice versa.
4. Refactor simple scripts to use while loops for more flexible and dynamic behavior.
5. Troubleshoot and debug common issues associated with infinite loops and incorrect conditionals.



## Activity Instructions

Complete the knowledge check.

### Knowledge Check
1. What do the `continue` and `break` commands do in a for or while loop in Bash?
   1. `continue` exits the loop, while `break` skips to the next iteration.
   2. `continue` skips the current iteration and moves to the next one, while `break` exits the loop entirely.
   3. Both `continue` and `break` skip the current iteration and move to the next one.
   4. Both `continue` and `break` exit the loop, but continue does it after the first iteration, and break does it after the second iteration.  
<details closed>
<summary>Answer</summary>
`continue` skips the current iteration and moves to the next one, while `break` exits the loop entirely.
</details>

2. What is the correct syntax for a Bash `while` loop? Where command represents the sequence of commands inserted into the loop.
   1. `while [ condition ]; do command; done`  
   2. `while condition do command; done`  
   3. `while [ condition ] do command; done`  
   4. `while condition; do command`  
<details closed>
<summary>Answer</summary>
<code>while [ condition ]; do command; done</code>
</details>

3. Which of the following `while` loops will print the numbers 1 through 5 if i=1?
   1. `while [ $i -le 5]; do echo $i; ((i++)); done`  
   2. `while [ $i =< 5 ]; do echo $i; ((i++)); done`  
   3. `while [$i -le 5 ]; do echo $i; ((i++)); done`  
   4. `while [ $i -le 5 ]; do echo $i; ((i++)); done`  
<details closed>
<summary>Answer</summary>
<code>while [ $i -le 5 ]; do echo $i; ((i++)); done</code>
</details>

4. In the following code, what will be printed?
```bash
#!/bin/bash

count=1
while [ $count -le 3 ]; do
    echo "Hello"
    ((count++))
done
```
   1. 1 2 3
   2. Hello 1 2 3 
   3. Hello Hello Hello 
   4. Hello Hello
<details closed>
<summary>Answer</summary>
prints:<br>Hello <br>Hello <br>Hello 
</details>

5. Which of the following is a correct use case for a `while` loop?
   1. Iterating over a fixed range of numbers.
   2. Repeatedly performing an action until a condition is met.
   3. Iterating through an array.
   4. Accessing specific elements in a list.
<details closed>
<summary>Answer</summary>
Repeatedly performing an action until a condition is met.
</details>

6. Write a `while` loop that prints all even numbers between 1 and 20.
<details closed>
<summary>Answer</summary>

```bash
#!/bin/bash

i=2
while [ $i -le 20 ]; do
    echo $i
    ((i+=2))
done
```  
</details>

7. What is the difference between a while loop and a for loop in Bash? Select all that apply.
   1. A `while` loop is used when the number of iterations is unknown or depends on a condition.
   2. A `for` loop is used when the number of iterations is unknown or depends on a condition.
   3. A `while` loop is typically used when you know the exact number of iterations in advance.
   4. A `for` loop is typically used when iterating over a fixed range of numbers or an array.
   5. A `while` loop is used for iterating over arrays or fixed ranges.
   6. A `for` loop can be used to repeatedly read user input based on a condition.
<details closed>
<summary>Answer</summary>
A <code>while</code> loop is used when the number of iterations is unknown or depends on a condition, and a <code>for</code> loop is typically used when iterating over a fixed range of numbers or an array.
</details>

8. Write a while loop that asks the user to input a number. If the number is less than 10, the loop should continue asking for input until the user enters a number greater than or equal to 10.
<details closed>
<summary>Answer</summary>

```bash
#!/bin/bash

while true; do
    read -p "Enter a number greater than or equal to 10: " num
    if [ $num -ge 10 ]; then
        break
    fi
done
``` 
</details>

9. True or False: A `while` loop can only be used when you know the exact number of iterations in advance.
   1. True
   2. False
<details closed>
<summary>Answer</summary>
False. A <code>while</code> loop is typically used when the number of iterations is not known in advance, but rather depends on the condition being true.
</details>

10. True or False: The `while` loop in Bash executes its commands as long as the given condition evaluates to true.
      1. True
      2. False
<details closed>
<summary>Answer</summary>
True. The <code>while</code> loop continues executing its commands as long as the condition evaluates to true.
</details>

11. What could happen if you accidentally forget to increment the counter inside a `while` loop, like shown below.

```bash
#!/bin/bash

count=1
while [ $count -le 5 ]; do
    echo $count
done
```

<ol type="i">
    <li>The script will execute once, print an error message to the user, and then exit.</li>
    <li>The script will prompt for user input, before exiting with an error message.</li>
    <li>The script will not run, and will print an error message to the user.</li>
    <li>This script will run infinitely because the condition will always be true.</li>
</ol>
<details closed>
<summary>Answer</summary>
This script will run infinitely because the condition will always be true.
</details>
