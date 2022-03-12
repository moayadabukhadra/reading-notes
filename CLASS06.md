# Game of Greed 1

## How to use the Random Module in Python

- The random module provides access to functions that support many operations.

## Random functions:

1. Randint:

    *If we want a random integer, we can use the randint function*

- accepts two arguments (lowest,higest)
- generates a random number between them 

```
import random
print random.randint(0, 5)
```

2. Choice:
    *Generate a random value from the sequence*

```
random.choice( ['red', 'black', 'green'] ).
```

3. Shuffle

    *The shuffle function, shuffles the elements in list in place, so they are in a random order.*

```
    from random import shuffle

x = [[i] for i in range(10)]
shuffle(x)

# Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
```

4. Randrange
    *Generate a randomly selected element from range(start, stop, step)*

```
import random
for i in range(3):
    print random.randrange(0, 101, 5)
```

## What is Risk Analysis:
    
- In general Risk is The probability of any unwanted incident

- In Software Testing, risk analysis is the process of identifying the risks in applications or software

### Why use Risk Analysis?

- using risk analysis at the beginning of a project highlights the potential problem areas.

- helps the developers and managers to mitigate the risks.

### There are three perspectives of Risk Assessment:

1. Effect – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

2. Cause – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

3. Likelihood – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.









