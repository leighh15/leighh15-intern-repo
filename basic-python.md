# Task 1: Hello, Python!

greeting = "Good Morning Starshine, the Earth says 'Hello'!"

print(greeting)

# Task 2: Simple Math

num1 = float(input("Please enter the first number: "))

num2 = float(input("Please enter the second number: "))

print("Sum: ", num1 + num2)

print("Difference: ", num1 - num2)

print("Product: ", num1 * num2)

if num2 == 0:
    print("Quotient: undefined, cannot divide by zero.")
else:
    print("Quotient: ", num1 / num2)

# Task 3: Your Age in Dog Years

humanage = int(input("Please state your age: "))

print("Your age in dog years is", humanage * 7, "years!")

# Task 4: Favourite Food

favefood = input("What's your favourite food of all time? ")

print("When someone confesses their love to you, you should say, 'Thanks, but you're not " + favefood.lower() + "'.")

# Task 5: Number Guessing Game

from random import randint

secret_number = randint(1,10)

while True:
    guess = int(input("I'm thinking of a number from 1 to 10, can you guess my number? "))
    if guess > secret_number:
        print("Lower!")
        continue
    elif guess < secret_number:
        print("Higher!")
        continue
    else:
        print("Correct!")
        break

The image below shows the output of my python code.
<img width="644" height="300" alt="Screenshot 2025-08-15 at 10 38 12 am" src="https://github.com/user-attachments/assets/36ab3524-2da0-4ea5-a623-c7c25c509157" />

Reflection

I found the last task the most fun, the number guessing game. I enjoy working with if-else statements and because I also did not know the number, it feels like a game for myself as well. 

It was exciting to see my code come to life, and also excited to see myself improve in Python so I can see more interactive and complex code. 

I can imagine some automation through Python can help make daily tasks easier such as checking through to-do-lists, creating reminders, noting deadlines, budgeting, etc. I can simply input things and Python can do the optimisation. 

As an example, I can create a simple to-do list. I can view all my tasks, add a task, remove a task, etc. 
