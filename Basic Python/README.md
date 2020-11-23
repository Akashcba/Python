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
            print("Entered The Loop")    #This code is implemented. 
  ```
### Strings
In python strings are immutable objects and cannot be changed after their creation.
```python
# Strings can be created in the following ways;
string_1 = 'Yes' # Single quotes
strng_2  = "Yes double" # Double quotes
string_multi = ''' This is
                   a multi line string '''
string_from_int = str(76) # '76' ,str() is a builtin function that converts integer value to a string.
                          # We may use str() function to make a list of strings from integer values
                          # and these values can then be sorted lexicographically (i.e based on the first element)
string = string_1 + string_2  # Concatenation of string objects.
```
Python provides us with whitespace characters and the most frequently whitespace characters include newline character ("\n"), space character ("\s) and tab character("\t).
```python
# Most Useful String Methods
string = "              This string contains whitespace    "
print(string.strip()) ## Removes the leading and trailing whitespace characters from the string
                      # "This string contains whitespace"

print("helloWORLD".lower()) # returns the string in lowercase. 
                            # "helloworld"
print("lowercase".upper())  # returns the striing in uppercase
                            # LOWERCASE

print("Google Chrome".startswith("Goo")) # Returns true if the string's prefix matches with the argument of the function.
                                         # True
print("Google Chrome".endswith("ome")) # Returns True if the suffix of the string matches with the argument of the function.
                                       # True

print("coding".find("ing")) # Checks if the string in arguments is present in the main string.It then returns the beginning
                            # of the matched string. If string is not found it returns a -1
print("Life is life, live it great".replace("ife","***")) # replaces all instances of the argument in the main string
                                                          # "L*** is l***,live it great
print("".join(['c','o','d','e'])) # Joins all the characters of the iterable to return a string
                                  # "code"
print(len("Yellow")) # len is a builtin function that returns the length of the string.
                     # 6
# To check if a string is present in another string we can use the "in" operator
print("sim" in "simulation")   # True
```
### Container Data Structures
### List
List is a container data type that stores a sequence of elements. Unlike strings the lists are mutable and can have repeated elements.
```python
# Most Useful list functions

ls = [1,2,3,4]      # ls is a list container with 4 elements

# Adding Elements
ls.append(5)  # adds the element 5 in the end of the list  ## ls = [1,2,3,4,5]
ls.insert(6,2) # adds the element 6 at the index 2 position. Note- indexes start from 0 in python
               # ls = [1,2,6,3,4,5]
ls += [2,7,8] # Lists can be concatenated. --> ls = ls + [2,7,8]
              # ls = [1,2,6,3,4,5,2,7,8]   # Repetition allowed in lists
# The append operation is the fastest because it just adds the new element on the tail of the list.

ls.remove(1) # Removing Elements --> ls = [2,6,3,4,5,2,7,8]
             # Removes the first occurence of the element in the arguments.
ls.reverse() # Reverses the list. This operation of this function are reflected on the original list too.
             # ls = [8,7,2,5,4,3,6,2]
ls.sort()   # Sort the list  ---> ls = [2,2,3,4,5,6,7,8]
```
#### List Comprehension
Python gives us the ability to quickly create and modify lists through list comprehension using the formula:
                                                [ expression + context ]
Expression tells python what to do with each element in the list.
Context tells python which lists elements to select.
```python
names = [ ("XYZ" , 150),
            ("ABC" , 200),
            ("PQR" , 400) ]
print ( [ x for x,y in names if y >= 200 ] )  ## ["ABC" ,"PQR"]
```
### Stack
In python stack data structures (FIFO implementation) can be easily done using lists.
```python
stack = [2,3]
stack.append(4) # stack = [2,3,4]
stack.pop()     # stack = [2,3]
```
### Sets
In python sets is a basic collection data type that only stores unique (non repeating) copies of the elements.
#### Properties of Sets
(i) Sets only store those values that are hashable.
   A hash value of an object remains same and is used by set to compare objects.
Note: Lists are not hashable and cannot be stored in sets.
(ii) Elements in set are unordered. So we cannot access any elemets using the index values.
(iii) Only unique elements are stored in the set. (Hash value of any elements should not be same)
```python
set1 = {"Hello" ,"Boss"}
print(hash("Hello"))
print(hash(list("This is a string")))  ## Runtime error: Unhashable type: list
set2 = set(list("This is valid syntax"))
```
### Dictionary
Dictionary is a useful data structure for storing (key,vlaue) pairs.
Keys should be unique.
```python
di1 = {"one":1,"two":2,"three":3}
print(di1["one"] < di1["two"] ) # True
#keys() function can be used to access all keys in a dictionary.
print("five" in di1.keys() )   # False
#values() function can be used to access all the values stored in dictionary.
print(3 in di1.values())   # True
# items() function can be used to access the (key,value) pair
for key,value in di1.items():
            print("key= ",key) if key == "one" else None       # key= one
            print("value") if value == 3 else None             # value
```
### Lambda Functions
Lambda functions are anonymous functions that are not definedin the namespace (That is they are functions without a name)
Lambda functions are intended to make code shorter and more concise and easy to read.
lambda <arguments> : <return expression>
```python
print(lambda a : a + 3)(5)  # output = 8
```

## Note
There many useful python functions that were not mentioned here but you can read about them at https://docs.python.org/3/contents.html
We will be using lambda functions extensively in next articles. So, you should practice them as much as possible.
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
