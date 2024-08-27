# Python-Assignment
Python Assignment

## Explain with an example each when to use a for loop and a while loop.
For Loop
When to use it:

Use a for loop when you know in advance how many times you want to repeat a certain action. It's great for iterating over a fixed range or collection of items.

Example:

Imagine you have a list of 5 names and you want to print each name. You know exactly how many names there are, so you use a for loop.

Here’s how it looks in Python:

python
Copy code
names = ["Alice", "Bob", "Charlie", "David", "Eva"]
for name in names:
    print(name)
In this example, the loop goes through each name in the list and prints it. Since the list has a fixed number of items (5 names), a for loop is perfect here.

While Loop
When to use it:

Use a while loop when you want to keep doing something until a certain condition is met. You don’t always know in advance how many times you’ll need to repeat the action.

Example:

Imagine you’re playing a game where you keep rolling a dice until you get a 6. You don’t know how many rolls it will take, so you use a while loop.

Here’s how it might look in Python:

python
Copy code
import random

roll = 0
while roll != 6:
    roll = random.randint(1, 6)
    print(f"You rolled a {roll}")
print("You rolled a 6!")
In this example, the loop keeps rolling the dice and printing the result until you roll a 6. The number of rolls required is unknown, so a while loop is suitable.

Summary:

For loop: Use when you know in advance how many times you need to repeat an action (like iterating through a list).
While loop: Use when you keep repeating an action until a certain condition changes (like rolling dice until you get a 6).    

## Question: Certainly! Here’s how you can write a Python program to calculate and print the sum and product of the first 10 natural numbers using both for and while loops.

Using a For Loop
python
Copy code
# Using for loop
sum_for = 0
product_for = 1

for i in range(1, 11):  # Iterates from 1 to 10
    sum_for += i        # Add current number to sum
    product_for *= i   # Multiply current number to product

print("Using for loop:")
print("Sum of the first 10 natural numbers:", sum_for)
print("Product of the first 10 natural numbers:", product_for)
Using a While Loop
python
Copy code
# Using while loop
sum_while = 0
product_while = 1
i = 1

while i <= 10:          # Continue as long as i is less than or equal to 10
    sum_while += i      # Add current number to sum
    product_while *= i # Multiply current number to product
    i += 1              # Increment i by 1

print("Using while loop:")
print("Sum of the first 10 natural numbers:", sum_while)
print("Product of the first 10 natural numbers:", product_while)

Both loops will produce the same results:

The sum of the first 10 natural numbers is 55.
The product of the first 10 natural numbers is 3,628,800.

## Create a python program to compute the electricity bill for a household. The per-unit charges in rupees are as follows: For the first 100 units, the user will be charged Rs. 4.5 per unit, for the next 100 units, the user will be charged Rs. 6 per unit, and for the next 100 units, the user will be charged Rs. 10 per unit, After 300 units and above the user will be charged Rs. 20 per unit.   
You are required to take the units of electricity consumed in a month from the user as input.   
Your program must pass this test case: when the unit of electricity consumed by the user in a month is 310, the total electricity bill should be 2250. 


def calculate_bill(units_consumed):
    # Initialize the total bill
    bill = 0
    
    # Calculate bill based on the number of units consumed
    if units_consumed <= 100:
        bill = units_consumed * 4.5
    elif units_consumed <= 200:
        bill = (100 * 4.5) + ((units_consumed - 100) * 6)
    elif units_consumed <= 300:
        bill = (100 * 4.5) + (100 * 6) + ((units_consumed - 200) * 10)
    else:
        bill = (100 * 4.5) + (100 * 6) + (100 * 10) + ((units_consumed - 300) * 20)
    
    return bill

def main():
    try:
        # Get user input
        units = float(input("Enter the number of units consumed: "))
        
        if units < 0:
            print("Units consumed cannot be negative.")
            return
        
        # Calculate the bill
        bill_amount = calculate_bill(units)
        
        # Print the bill amount
        print(f"The electricity bill for {units} units is: Rs. {bill_amount:.2f}")
    
    except ValueError:
        print("Please enter a valid number.")

if __name__ == "__main__":
    main()


## Create a list of numbers from 1 to 100. Use for loop and while loop to calculate the cube of each number and if the cube of that number is divisible by 4 or 5 then append that number in a list and print that list. 

    To solve this problem, you need to:

Create a list of numbers from 1 to 100.
Calculate the cube of each number.
Check if the cube is divisible by 4 or 5.
Append such numbers to a new list.
Print the list.
Here’s how you can achieve this using both for and while loops.

Using a For Loop
python
Copy code
# List to store numbers whose cube is divisible by 4 or 5
divisible_by_4_or_5 = []

# Iterate through numbers from 1 to 100
for number in range(1, 101):
    cube = number ** 3
    if cube % 4 == 0 or cube % 5 == 0:
        divisible_by_4_or_5.append(number)

print("Numbers whose cube is divisible by 4 or 5 (using for loop):")
print(divisible_by_4_or_5)
Using a While Loop
python
Copy code
# List to store numbers whose cube is divisible by 4 or 5
divisible_by_4_or_5 = []

# Initialize starting number
number = 1

# Iterate while the number is less than or equal to 100
while number <= 100:
    cube = number ** 3
    if cube % 4 == 0 or cube % 5 == 0:
        divisible_by_4_or_5.append(number)
    number += 1  # Increment the number

print("Numbers whose cube is divisible by 4 or 5 (using while loop):")
print(divisible_by_4_or_5)


## Write a program to filter count vowels in the below-given string.  string = "I want to become a data scientist" 
ChatGPT said:
ChatGPT
To count the number of vowels in a given string, you can follow these steps:

Define the string to be analyzed.
Initialize a count for vowels.
Loop through each character in the string.
Check if the character is a vowel (both uppercase and lowercase).
Increment the count if the character is a vowel.
Print the total count of vowels.
Here's a Python program that performs these steps:

python
Copy code
def count_vowels(s):
    # Define the set of vowels
    vowels = "aeiouAEIOU"
    # Initialize vowel count
    vowel_count = 0
    
    # Loop through each character in the string
    for char in s:
        if char in vowels:
            vowel_count += 1
    
    return vowel_count

# Define the input string
input_string = "I want to become a data scientist"

# Call the function and print the result
vowel_count = count_vowels(input_string)
print(f"The number of vowels in the string is: {vowel_count}")
