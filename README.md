# Group Python
This is our webpage containing the Python-code for the Homework 1 assignments.

Siem van Staveren (1583115)
Eva Heslenfeld (1567063)
David Bogner (1482262)
Caya Papst (1050403)

#Homework Assignment 1

#Exercise 1
#This script generates a dictionary assigning an "odd" or "even" value to depending on the type of number
# Description:
    #The odd_even_dictionary function creates a dictionary with integers that represents the length of the sequences ranging from  to length - 1.
    #Each interger is paired with either a "odd" or "even" value, depending on whether the interger is even or odd.
#Parameters
    # length (int): The parameter length of the sequence to be created, must be a positive integer. If input lenght is negative a ValueError should be raised.
#Return
    # A dictionary should be returned. A dictionary where the numbers are integers from 0 to (length - 1) and  the values are strings "odd" or "even" based on the type of number.



def odd_even_dictionary(length):    #define function

   if length < 0:  #Raises an error if lenght is negative
      raise ValueError ("This integer is negative. Length must be a positive integer.")
   
   result = {}      #create an empty dicitionary


    for i in range(length):     # Loop over the range of the given length
        
        # Assign "even" if the number is divisible by 2, otherwise "odd"
        if i % 2 == 0:
            result[i] = "even"
        else:
            result[i] = "odd"

    # Return the populated dictionary
    return result


#Example
result = odd_even_dictionary(6)

print(result)

#Exercise 2

...

#Exercise 3

'''
# Prime Numbers List Generator-Version 1

## Description

    This Python script generates a list of all prime numbers between 2 and 100 using for loops and conditional statements.
    We excluded 1 since it is not a prime number. A prime number is defined as a a whole number greater than 1 that cannot
    be exactly divided by any whole number other than itself and 1.
    This code checks each number in the specified range to determine if it is a prime number.

## Parameters

    The script uses one parameter which is range:

    - **Range:** The range of numbers to be checked for prime numbers is from 2 to 100. The range does not include 1,
                as 1 is not considered a prime number.

## Structure

The script follows the structure:

1. Creating an empty list named `primes` store the prime numbers.

2.Using a `for` loop, all numbers (`num`) between 2 and 100 are ran through.

3. In the next step we check if these numbers are true prime numbers
   - For each number, the script assumes it is prime by setting a boolean variable `is_prime` to `True`.
   - A `for` loop checks divisibility of `num` by checking possible divisors from 2 up to the square root of `num`.
    This is done to optimize the check by reducing unnecessary computations. Because if the square root of n has 
    a divisor greater than the square root of n, there must also be a corresponding divisor less than square root n.
   - If `num` is found to be divisible by any divisor in this range, the Boolean variable `is_prime` is set to `False`, 
    indicating the number is not prime.
4. If after the inner loop, the `is_prime` flag remains `True`, the number is added to the `primes` list.

5. Output: the list of prime numbers is printed.

'''
#Code

# List to store prime numbers
prime_numbers = []

# Check numbers from 2 to 100 (1 is not a prime number)
for num in range(2, 101):
    is_prime = True  # Assume the number is prime

    # Check divisibility by any number from 2 to the square root of the number
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            is_prime = False  # Set to False if num is divisible by i
            

    # Only add the number to the list if it is still considered prime
    if is_prime:
        prime_numbers.append(num)

print(prime_numbers)



#Version 2
#Prime Numbers List Generator

  #This script generates a list of all prime numbers between 2 and 100. Prime numbers are integers greater than 1 that have no positive divisors other than 1 and themselves. This script uses list comprehension with `all()` function to identify prime numbers.

#Code
prime_numbers = [num for num in range(2, 101) if all(num % i != 0 for i in range(2, int(num ** 0.5) + 1))]
print(prime_numbers)
