## Activity Objective

The objective of this activity is to help students understand and implement control flow in Bash scripts using while loops, along with the use of `break` and `continue` statements. By the end of this activity, students will be able to:
1. Write and refactor Bash scripts using `while` loops for continuous user interaction.
2. Utilize `break` to exit loops gracefully based on specific conditions (e.g., user input).
3. Apply `continue` to skip certain iterations of a loop and prompt the user again when invalid input is detected.
4. Understand the importance of proper flow control in interactive scripts to handle user inputs, errors, and exits effectively.
5. Refactor existing scripts to improve readability, efficiency, and user experience using `while`, `break`, and `continue`.
Through this activity, students will gain hands-on experience with Bash loops and control flow, which are fundamental skills for writing more dynamic and user-friendly scripts.



## Activity Instructions
Refactor the code to use a while true loop that will repeatedly ask the user for input until they explicitly choose to exit, following the instructions below:
1. Wrap the entire logic for prompting and handling user input inside a `while` loop and set the condition to true in order to continuously ask for the user’s choice.
2. Inside the `while` loop, update the exit logic to include a `break` to exit the loop. This will allow the script to exit the infinite loop and finish the execution cleanly.
3. Inside the `while` loop, update the logic that handles invalid inputs to include a `continue`. This will ensure that after receiving an invalid input, the script will go back to the beginning of the loop and ask for the user's input again.
4. Validate and verify that your script will continue looping, asking the user for input, until the user selects the option to exit, and if the user selects an invalid option, the script will display an error message and prompt them again without performing any other operations.
5. Submit version 4 of your script.

