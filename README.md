# codemetric_calculator-task
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b

print("Welcome to the Python Calculator!")
print("Type 'exit' at any time to quit.\n")

while True:
    try:
        num1 = input("Enter first number: ")
        if num1.lower() == 'exit':
            break
        num1 = float(num1)

        op = input("Enter operation (+, -, *, /): ")
        if op.lower() == 'exit':
            break
        if op not in ['+', '-', '*', '/']:
            print("Invalid operator. Try again.\n")
            continue

        num2 = input("Enter second number: ")
        if num2.lower() == 'exit':
            break
        num2 = float(num2)

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

        print(f"Result: {num1} {op} {num2} = {result}\n")

    except ValueError:
        print("Invalid input. Please enter numeric values only.\n")
    except ZeroDivisionError as e:
        print(f"Error: {e}\n")
    except Exception as e:
        print(f"Unexpected error: {e}\n")

print("Calculator closed. Goodbye!")
