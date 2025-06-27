## Activity Objective

By the end of this activity, students will be able to:
1. Understand and apply the syntax of for loops in Bash scripting.
2. Write basic and advanced for loops to iterate through lists, ranges, and variables.
3. Use continue and break commands effectively within loops to control the flow of execution.
4. Solve real-world problems by utilizing for loops to automate tasks such as processing lists, performing calculations, and iterating through files.
5. Demonstrate problem-solving skills by creating and debugging Bash scripts with for loops.

## Activity Instructions

Complete the knowledge check below.

### Knowledge Check
1. What is the correct basic syntax for a `for` loop in Bash? 
   1. `for i in 1 to 5; do echo $i; done`  
   2. `for i=1 to 5; do echo $i; done`  
   3. `for i in 1 2 3 4 5; do echo $i; done`  
   4. `for (i=1; i<=5; i++) do echo $i; done`  
<details closed>
<summary>Answer</summary>
<code>for i in 1 2 3 4 5; do echo $i; done</code>
</details>

2. Which of the following for loop examples will print the numbers 1 through 5? Select all that apply.
   1. `for i in {1..5}; do echo $i; done`  
   2. `for i in 1 to 5; do echo $i; done`  
   3. `for i in 1 2 3 4 5; do echo $i; done`  
   4. `for i in {1..5}; do echo $i; fin`  
<details closed>
<summary>Answer</summary>
<code>for i in {1..5}; do echo $i; done</code> and <code>for i in 1 2 3 4 5; do echo $i; done</code> will print the numbers 1 - 5
</details>

3. What will the following loop print?
```bash
#!/bin/bash

my_array=("I" "Love" "Cyber" "Security")

for item in "${my_array[@]}"
do
  echo "$item"
done
```
<ol type="i">
    <li>The loop iterates through each index of the array and prints the index number.</li>
    <li>The loop iterates through each element in the array and prints it on a new line.</li>
    <li>The loop prints the entire array on a single line.</li>
    <li>The loop prints the word "I" four times, once for each loop element.</li>
</ol>
<details closed>
<summary>Answer</summary>
The loop iterates through each element in the array and prints it on a new line.
</details>

4. True or False: A for loop can iterate through a list of items provided by a variable.
   1. True
   2. False
<details closed>
<summary>Answer</summary>
True
</details>


5. True or False: The syntax `for ((i=1; i<=5; i++))` is used to create a for loop in Bash that increments i from 1 to 5.
   1. True
   2. False
<details closed>
<summary>Answer</summary>
True
</details>

6. What is the output of the following script?
```bash
#!/bin/bash

for i in {3..7}; do
  echo $((i * 2))
done
```
<ol type="i">
    <li>print: 0 2 4 6 8</li>
    <li>print: 2 4 6 8 10</li>
    <li>print: 4 6 8 10 12</li>
    <li>print: 6 8 10 12 14</li>
</ol>
<details closed>
<summary>Answer</summary>
print:<br>6<br>8<br>10<br>12<br>14
</details>

7. Write a bash `for` loop that will loop through all .sh files in your Downloads directory and print the name of each .sh file.
<details closed>
<summary>Answer</summary>
   
```bash
#!/bin/bash
for file in ~/Downloads/*.sh
do
  echo "$file"
done
```
</details>

8. You are given the following list of numbers: 10, 20, 30, 40. Write a for loop that prints each number squared (i.e., 100, 400, 900, 1600).
<details closed>
<summary>Answer</summary>

You can use a loop with a range from 10 to 40 with a step of 10 if you need to iterate over a continuous sequence and do not require random access or manipulation of individual elements:
```bash
#!/bin/bash

for i in {10..40..10}
do
  echo $((i * i))
done
```
or you can put the list of numbers into an array, and iterate through it:   
```bash
#!/bin/bash

numbers=(10 20 30 40)
for num in "${numbers[@]}"
do
  echo $((num * num))
done
```
</details>

9. Write a for loop that prints all the elements in the array arr=(apple banana cherry).
<details closed>
<summary>Answer</summary>
   
```bash
#!/bin/bash
arr=(apple banana cherry)
for item in "${arr[@]}"
do
  echo "$item"
done
```
</details>

