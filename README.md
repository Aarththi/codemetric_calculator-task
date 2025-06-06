# codemetric_calculator-task
Overview: What Does This Calculator Do?
This is a command-line calculator written in Python. It allows users to perform basic arithmetic operations:

Addition (+)

Subtraction (-)

Multiplication (*)

Division (/)

The calculator operates in a loop, continuously prompting the user for input until they type 'exit' to quit.

 Step-by-Step Explanation
1. Defining Arithmetic Functions
python
Copy
Edit
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b
Purpose: These functions perform the four basic arithmetic operations.

How it works: Each function takes two parameters (a and b) and returns the result of the operation.

2. Displaying Welcome Messages
python
Copy
Edit
print("Welcome to the Python Calculator!")
print("Type 'exit' at any time to quit.\n")
Purpose: Greets the user and provides instructions.

Note: The \n adds a newline for better readability.

3. Starting the Main Loop
python
Copy
Edit
while True:
    try:
        # Code for user input and calculations goes here
    except ValueError:
        print("Invalid input. Please enter numeric values only.\n")
    except ZeroDivisionError as e:
        print(f"Error: {e}\n")
    except Exception as e:
        print(f"Unexpected error: {e}\n")
Purpose: Continuously prompts the user for input until they decide to exit.

Error Handling:

ValueError: Catches non-numeric inputs.

ZeroDivisionError: Catches division by zero errors.

Exception: Catches any other unexpected errors.

4. Getting the First Number
python
Copy
Edit
num1 = input("Enter first number: ")
if num1.lower() == 'exit':
    break
num1 = float(num1)
Purpose: Prompts the user to enter the first number.

Details:

Checks if the user wants to exit.

Converts the input to a floating-point number for calculations.

5. Getting the Operation
python
Copy
Edit
op = input("Enter operation (+, -, *, /): ")
if op.lower() == 'exit':
    break
if op not in ['+', '-', '*', '/']:
    print("Invalid operator. Try again.\n")
    continue
Purpose: Prompts the user to enter the desired operation.

Details:

Checks if the user wants to exit.

Validates the operator; if invalid, prompts again.

6. Getting the Second Number
python
Copy
Edit
num2 = input("Enter second number: ")
if num2.lower() == 'exit':
    break
num2 = float(num2)
Purpose: Prompts the user to enter the second number.

Details:

Checks if the user wants to exit.

Converts the input to a floating-point number for calculations.

7. Performing the Calculation
python
Copy
Edit
if op == '+':
    result = add(num1, num2)
elif op == '-':
    result = subtract(num1, num2)
elif op == '*':
    result = multiply(num1, num2)
elif op == '/':
    if num2 == 0:
        raise ZeroDivisionError("Cannot divide by zero.")
    result = divide(num1, num2)
Purpose: Determines which operation to perform based on user input.

Details:

Calls the corresponding function for the operation.

Checks for division by zero and raises an error if detected.

8. Displaying the Result
python
Copy
Edit
print(f"Result: {num1} {op} {num2} = {result}\n")
Purpose: Shows the result of the calculation in a readable format.

9. Exiting the Calculator
python
Copy
Edit
print("Calculator closed. Goodbye!")
Purpose: Displays a farewell message when the user decides to exit.

🧪 Sample Output
Here's how the calculator might interact with a user:

sql
Copy
Edit
Welcome to the Python Calculator!
Type 'exit' at any time to quit.

Enter first number: 2
Enter operation (+, -, *, /): +
Enter second number: 8
Result: 2.0 + 8.0 = 10.0

Enter first number: 4
Enter operation (+, -, *, /): -
Enter second number: 4
Result: 4.0 - 4.0 = 0.0

Enter first number: 5
Enter operation (+, -, *, /): *
Enter second number: 6
Result: 5.0 * 6.0 = 30.0

Enter first number: 6
Enter operation (+, -, *, /): /
Enter second number: 5
Result: 6.0 / 5.0 = 1.2

Enter first number: exit
Calculator closed. Goodbye!
 Key Takeaways:
Functions: Encapsulate operations for reusability and clarity.

Loops: Allow continuous interaction until a specific condition is met.

Error Handling: Ensures the program can handle unexpected inputs gracefully.

User Input: Always validate and handle user inputs to prevent crashes.

