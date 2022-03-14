# Python Scope & the LEGB Rule: Resolving Names in Your Code

## scope

*the scope of a name defines the area of a program in which you can unambiguously access that name*

1. ### Global scope: The names that you define in this scope are available to all your code.


2. ### Local scope: The names that you define in this scope are only available or visible to the code within the scope.


- When you can access the value of a given name from someplace in your code, you’ll say that the name is "in scope".

- If you can’t access the name, then you’ll say that the name is "out of scope".

### Names and Scopes in Python:



|Operation|	Statement|
|---------|----------|
|Assignments|	x = value|
|Import operations|	import ||module or from module| import| name
|Function definitions|	def my_func(): ...|
|Argument definitions in the context of functions|	def my_func(arg1, arg2,... argN): ..|.
|Class definitions|	class MyClass: ...|


## Using the LEGB Rule for Python Scope:

*"The LEGB rule is a kind of name lookup procedure, which determines the order in which Python looks up names."*

## Functions: The Local Scope: 

*The local scope or function scope is a Python scope created at function calls. Every time you call a function, you’re also creating a new local scope.*

```
>>> def square(base):
...     result = base ** 2
...     print(f'The square of {base} is: {result}')
...
>>> square(10)
The square of 10 is: 100
>>> result  # Isn't accessible from outside square()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    result
NameError: name 'result' is not defined
>>> base  # Isn't accessible from outside square()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    base
NameError: name 'base' is not defined
>>> square(20)
The square of 20 is: 400
```


## Modules: The Global Scope

- The namespace of this module is the main global scope of your program.