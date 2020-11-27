
# One Step Above The Basics

In basic python we introduced about list comprehension and lambda functions. Now  we will continue and talk about map() function ,slicing in lists, generator functions, and zip() function.

## List Comprehension

As disccussed previously Python gives us the ability to quickly create and modify lists through list comprehensions using the formula: [ expresson + context ] 
The context defines which list element to select and the expression defines how to modify each element before adding the result to the list.
```python
# List Comprehension Examples ;
ls = [ x*2 for x in range(3) ] ## Here "for x in range(3)" is the context and "x*2" is the expression.
                               ## The goal of expression is to modify each selected element before adding it to the list.
## ls = [0,2,4]
ls2 = [ x for x in range(5) ] # ls2 = [0,1,2,3,4]

ls3 = [(x,y) for x in range(3) for y in range(3) ] ## It generates a tuple from the context of variables x and y.
# ls3 = [(0,0),(0,1),(0,2),(1,0),(1,1),(1,2),(2,0),(2,1),(2,2)]

ls4 = [ _**2 for _ in range(10) if _%2 != 0 ] ## _ is a valid variable name as per the naming convention
## ls4 = [1,9,25,49,81]    --> Square of odd numbers less than 10.

ls5 = [ w.lower() for w in ["This","IS","Great","PYTHON"] ]
## all the elements in the list ls5 are in lowercase
#ls5 = ["this","is","great","python"]
```
Let us now see an example of how useful List Comprehensins can be and why we need to master them.
"We have a dictionary(or it can be any other iterable object) that contains list of students and ther marks in a subject. We need to print the students whose marks are greater than 65"
```python
students = {"Rahul" : 78 ,
            "Bill" : 56,
            "Eva" : 88
            "Frank" : 59
            "Rody" : 91 }
## Using Basic Python:
marks = []
for key, val in students.items():
     if val > 65:
          marks.append( (key,val) )
print(marks)

## Uisng List Comprehension

new_marks = [ (k,v) for k,v in students.items() if v > 65 ]     # Creates a tuple that stores the name and marks together.
print(new_marks)
```
It is clear that list comprehensions are a better and more concise way to write a program in Python.
Let's see another example of list comprehensions.
"Given a multiline string we need to create a list of words that have more than 3 characters". This is a major problem in Natural Language Processing where we need to filter out insignificant words( like the, a, an) and create tokens of words in an array.
```python
para = ''' Many of the words used in the phrase are insignificant and hold no meaning.
For example – English is a subject.
Here, ‘English’ and ‘subject’ are the most significant words and ‘ is ’, ‘ a ’ are almost useless.
English subject and subject English holds the same meaning even if we remove the insignificant words.
'''
word_list = [ [word for word in line.split() if len(word) > 3 ] for line in para.split("\n") ] ### Nested List Comprehension
print(word_list)
### [['Many', 'words', 'used', 'phrase', 'insignificant', 'hold', 'meaning.'],
['example', 'English', 'subject.'],
['Here,', '‘English’', '‘subject’', 'most', 'significant', 'words', 'almost', 'useless.'],
['English', 'subject', 'subject', 'English', 'holds', 'same', 'meaning', 'even', 'remove', 'insignificant', 'words' ] ]
```
## Reading a file in Python
In Python we can read a compelete file using the open function and store it as a list.
```python
list_file = [line.strip() for line in open("C://Mycomputer/readFile.py")]
```
## Lambda Functions and Map Function combo
Map() is a special function that takes a function as an argument and a sequence(or iterator)s. Map function applies that argument function on every element of that sequence.
Note: Map function returns a map object that can be converted to list.
```python
ls = ["1" ,"2" ,"3" ,"4" ,"5" ,"6"]   ## List of numbers stored as string.
ls = map( int , ls)
print(ls)     ### ls = [1, 2, 3, 4, 5, 6]  ---> Every object of ls converts to an integer.
```
Map function when combined with a Lambda function can prooved to be a very powerful tool.
```python
# Examples Of Lambda and Map function usage
ls = [1,2,3,4,5]
ls = list(map(lambda x: x**2 ,ls)
print(ls) ## ls = [ 1, 4, 9, 16, 25 ]

## Check if a word appears in a list of strings.
txt = [ "We are using a lambda function", 
        "These functions are anonnymous",
        "They don't have a name" ]
mark = map(lambda ss: (True, ss) if "function" in ss else (False ,ss) , txt)
# Creates a map function that contains tuple storing the bool value and the string.
print( list(mark) )  ## map object can only be printed after conversion to lists.
### mark = [ (True, 'We are using a lambda function'),
             (True, 'These functions are anonnymous'), 
             (False, "They don't have a name")]
```
## Slicing in Python
Slicing is the process of getting a subsequence of python's builtin data structures like lists,tuple,strings.
   var[start : stop : step]
#start is the starting index of the subsequence (Inclusive)
#stop is the ending index of the subsequence (Exclusive)
#step is the increment/gap python taken when traversing through the datastructure.
```python
string = "Say Hello"
string[0:3]         ## "sa"
string[3:0]         ## "" -> empty string because default value of step = 1
string[:5]          ## "Say H"
string[5:]          ## "ello"
string[:500]        ## "Say Hello"  --> automatically ends the operation at the end of the list
string[4:8:2]       ## "Hl"
string[::3]         ## "S l"
string[::-1]        ## "olleH yaS"    ---> Reverse of string equivalent to calling the reverse() function
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
