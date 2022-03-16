# List Comprehensions

Notes about Lists Comprehensions
- List comprehension methods are an elegant way to create and manage lists. 
- In Python, list comprehensions are a more compact way of creating lists. 
- More flexible than for loops, list comprehension is usually faster than other methods.

## Create a List with range()

example:
```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits)
```
output:

`[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`

## Create a List Using Loops and List Comprehension in Python

```
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

## Using functions in list comprehensions

Example 9: Adding arguments to list comprehension

 list comprehension with functions
 create a function that returns a number doubled
def double(x):
    return x*2
```
nums = [double(x) for x in range(1,10)]
print(nums)
```
Output
[2, 4, 6, 8, 10, 12, 14, 16, 18]

# Primer on Python Decorators

- decorators wrap a function, modifying its behavior.

example:

```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

def say_whee():
    print("Whee!")

say_whee = my_decorator(say_whee)
```

- if we call the function :
```
>>> say_whee()
Something is happening before the function is called.
Whee!
Something is happening after the function is called.
```

