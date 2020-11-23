# Basic Python
This file provides you with the basic python knowledge needed for more advanced topics we will be discussing.
Before you begin this roadmap you should have a basic understanding of Python syntax and programming logic.
If you are a compelete beginner then you should first familiarize yourself with the syntax and then move forward.

## Basic Data Structures

### Numerical Data Types
#### (i) integer type (int)
An integer is a positive or negative number without a floating point.
eg: 1,2,3 (represent integer values)
#### (ii) float type (float)
A float is a positive or negative number with floating point precision.

Arithmetic Operations
```python
x,y = 3,2
print(x+y) # = 5
print(x-y) # = 1
print(x*y) # = 6
print(x/y) # = 1.5, '/' represents floating point division
print(x//y) # = 1, '//' represents integer division. here the result of division is rounded to lower value.
print(x%y) # = 1, modulo division that returns the remainder when x is divided by y.
print(-x) # = -1
print(abs(-x)) # = 3, returns absolute value (only positive value)
print(int(3.9)) # = 3, returns an integer
print(float(x)) # = 3.0
print(x**y) # = 9, returns x to the power y.
            # x**(1/2) ---> Gives the square root of x
```
### Boolean Data Type
Boolean type can take two values - either True or False.
In Python False is represented by 0, and True is represented by 1.
```python
x = 1>2  # x is a boolean type object storing False
print(x) # Output is False
print(int(x)) # Output is 0

y = 2>1
print(y) # Output is True
print(type(y)) # Output is <'class bool'>
print(int(y)) # 1
```
#### and ,or,not keywords
boolean expressions along with and,or,not keywords can be used as basic logical operators.
Syntax
(exp1)and(exp2) # Evaluates to True if both exp1 and exp2 are true else returns a false.
(exp1)or(exp2) # Evaluates to True if any or both of the expressions is true.
not(exp) # Evaluates to True if exp is false else it returns a True (if exp is False)

The highest priority (or precedence) is given to not , followed by and ,then or.
not > and > or (Order of precedence)
```python
##Boolean Opeartions
x,y = True,False  # Multi-assignment available in python
print(x and not y) # Output is True because the prcedence of not is higher than and
print(not x and y or x) # True
```
In Python " None, 0, 0.0, '', [], {}, set() " represent a False condition.
```python
if not(None or 0 or 0.0 or '' or [] or {} or set()) :
  print("Entered The Loop")
  ```
### Strings
In python strings are immutable objects and cannot be changed after their creation. 
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.co
