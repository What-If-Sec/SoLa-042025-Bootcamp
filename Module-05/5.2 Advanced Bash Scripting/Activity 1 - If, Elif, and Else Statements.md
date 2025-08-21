## Activity Objective

By the end of this activity, students will be able to write and analyze Bash scripts using if, elif, and else statements to make decisions based on user input, file existence, and numerical comparisons. Students will gain hands-on experience applying common conditional operators to solve real-world logic problems using foundational Bash syntax.



## Activity Instructions

Complete the knowledge check.

### Knowledge Check


1. Which of the following is the correct way to begin an `if` statement in Bash?  
   1. `if (condition)`  
   2. `if [ condition ]; then`  
   3. `if condition then`  
   4. `if { condition }`  
<details closed>
<summary>Answer</summary>
<code>if [ condition ]; then</code>
</details>

2. What symbol is used to end an `if` statement in Bash?  
   1. `end if`  
   2. `done`  
   3. `fi`  
   4. `stop`  
<details closed>
<summary>Answer</summary>
<code>fi</code>
</details>

3. Which of the following evaluates to true if variable x equals 5? Select the preferred method for integers.
   1. `[ $x == 5 ]`  
   2. `[ $x -eq 5 ]`  
   3. `[ $x = 5 ]`  
   4. Both 2 and 3  
<details closed>
<summary>Answer</summary>
Although <code>[ $x == 5 ]</code> will also evaluate to true, <code>[ $x -eq 5 ]</code> is the preferred method for integers.
</details>

4. What is the correct way to check if a file exists in Bash?  
   1. `if exists file.txt; then`  
   2. `if [ file.txt ]; then`  
   3. `if [ -e file.txt ]; then`  
   4. `if file.txt exists then`  
<details closed>
<summary>Answer</summary>
<code>if [ -e file.txt ]; then</code>
</details>

5. Which operator checks if one number is less than another in Bash?  
   1. `<`  
   2. `-lt`  
   3. `-le`  
   4. `less`  
<details closed>
<summary>Answer</summary>
<code>-lt</code>
</details>

6. What does the `elif` keyword do in a conditional block?  
   1. Ends the current conditional block  
   2. Adds a loop inside an if statement  
   3. Adds another condition if the previous one fails  
   4. Declares a function  
<details closed>
<summary>Answer</summary>
Adds another condition if the previous one fails
</details>

7. True or False: The `else` clause in a Bash `if` statement is required.  
<details closed>
<summary>Answer</summary>
False
</details>

8. True or False: The `-ne` operator checks if two integers are not equal.  
<details closed>
<summary>Answer</summary>
True
</details>

9. True or False: You must always use `fi` to close every `if` block in Bash.  
<details closed>
<summary>Answer</summary>
True
</details>

10. True or False: You can use `elif` multiple times in a single `if` block.  
<details closed>
<summary>Answer</summary>
True
</details>

11. Write a Bash `if` statement that checks if a variable called `score` is greater than or equal to 90, and prints "Excellent!" if true.  
<details closed>
<summary>Answer</summary>

```bash
if [ $score -ge 90 ]; then
    echo "Excellent!"
fi
```
</details>

12. Explain what this code does:  
```bash
if [ $age -lt 18 ]; then
    echo "Minor"
elif [ $age -ge 18 ] && [ $age -lt 65 ]; then
    echo "Adult"
else
    echo "Senior"
fi
```
<details closed>
<summary>Answer</summary>
This checks the value of `age` and prints:  
<br>- "Minor" if age is less than 18  
<br>- "Adult" if age is between 18 and 64  
<br>- "Senior" if age is 65 or older
</details>

13. Correct the syntax in this code:  
```bash
if [$name = "Alice"]
    echo "Hello, Alice"
else
    echo "User not recognized"
fi
```
<details closed>
<summary>Answer</summary>

```bash
if [ "$name" = "Alice" ]; then
    echo "Hello, Alice"
else
    echo "User not recognized"
fi
```

</details>
