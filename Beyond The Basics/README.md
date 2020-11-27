
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
Let's see another example of list comprehensions
## Reading 
```bash
pip install foobar
```

## Usage

```python
import foobar

foobar.pluralize('word') # returns 'words'
foobar.pluralize('goose') # returns 'geese'
foobar.singularize('phenomena') # returns 'phenomenon'
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
