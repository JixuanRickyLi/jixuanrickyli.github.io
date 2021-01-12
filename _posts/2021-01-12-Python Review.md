
# Python Review  
<hr/>

## What is Python?

* <Strong>Interpreter based language</Strong>, allows the execution of one instruction at a time
* Support extensive basic data types:  numbers , strings, lists, dictionaries
* Variables can be strongly typed as well as dynamic typed
* Support OOP concepts -- class/ inheritance / obj/ module/ namespace
* cleaner exception handling 
* Automatic memory management 

## Where to use? 
* Data Science 
* Web Development 
* Image Processing
* Game Development 
* Rapid Development tool (CPython , Jython)



## Python Syntax

``` python
print( 'id:' , 1)
```

* Multiple lines code uses \ as the indicator

``` python
if 100 > 99 and \
    200 <= 300 and \
    True != False: \
        print('Yay')
```

* use ; to separate multiple statements in a single line
* expressions inside  () [] {} are not required to use \ for multilines

### Comment
    # Single Line comment

    ```
    multiline comment
    ```



# How to use user input?
name = input()
print(name)

age = input()
type(age)

#%% md

## Python Variables

* For memory optimization,
Python stores the same value variable to the same address
when value changes, it changes the address

#%%

type(10)



## Data Types

### Scalar types:
* int
* float
* complex (5+2j)
* bool  (True False)
* None

### Sequence Type
* String
* List
* Tuple  (not necessary in same data type)

### Mapping type
* Dictionary

### Set Type
* Set
* frozenset

### Mutable vs Immutable
* Number / Strings / Tuples are Immutable
* List / Dictionary / Set are mutable


## Number

### int
* _ can be deliminators
x = 1_232_234

int('5.5') = 5

### float

float('     -5') = -5.0

### Arithmetic Operators

+ - * / %

** exponent
// floor division

pow(2,3) = 8 
abs(-5) = 5



## String

String are immutable sequence data type.

'this is a string'
"this is also a string"
'''this is still  a string '''  (multiple line string)
"""well, string"""  (multiple line string)

#%%

s = 'i love you'
len(s)   # 10
# retrieve the length of the string

#%%

greet = 'hello'
greet[0]
greet[4]

#%% md

### str() class

str(100) -> '100'
str(True) -> 'True'
str1 = r'Welcome to \' Python \''
-> Welcome to \' Python \'
r before string is escaper's escaper

* operators:
    +     *    []     [ : ]     in    not in
* Methods:
    str.capitalize()
    str.index("hello") === first occurance of hello
    str.count("p") == count the num of P
    str.isdigit()
    str.split(' ')

#%% md

## List

### List Class
```python
myList = list('Hello')

nums = list({1:'one',2:'two'})
print(nums)  #  [ 1 , 2 ]

nums=list((10, 20, 30))
print(nums) #  [10, 20, 30]

nums=list({100, 200, 300})
print(nums) #  [100,200,300]

names = ["Jeff", "Bill", "Steve", "Mohan"]
del names[0] # removes item at index 0
print("After del names[0]: ", names)

names.remove("Bill") # removes "Bill"
print("After names.remove(\"Bill\"): ", names)

print(names.pop(0)) # return and removes item at index 0
print("After names.pop(0): ", names)

names.pop() # return removes item at last index
print("After names.pop(): ", names)

del names # removes entire list object
print(names)
```

list.append()
list.extend()
list.clear()
list.copy()
list.remove(element)
list.insert(index, value)
list.reverse()  => inplace reverse
list.sort(key=, reverse=True)   key : a function extract the key from each element
studentList.sort(key=lambda s: s.name)


#%% md

## Tuples
immutable
ordered collection, preserves the order of the elements
cannot declared by a single element  s = ('sss')  ==> string
must be  s = ('sss' , )   ===> tuple

names = ('mike', 'luke', 'rick')
names = 'mike', 'luke', 'rick'

a,b,c = names

update of the tuple element is not supported ---> error
del names

### class  tuple()
tuple('hello')

len(tuple)
max(tuple)
min(tuple)

#%% md

## Set

Mutable hashable distinct object collections.
Unordered: cannot get access by index

Set cannot add a list
set cannot add a set

set({1:'one', 2:'Two'})   dic -> set, conserve the keys
==> {1,2}

set.add(element)
set.update(another_set)
set.remove(element)

s1.union(s2)  s1|s2
s1.intersection(s2)  s1 & s2
s1.difference(s2)   s1 - s2
s1.symmetric_difference(s2)     s1^s2



#%% md

## Dictionary
Collection type:
not an ordered sequence, contain Key: value pairs.
list cannot be the key of dict. since list is mutable

* Accessing a Dict:
  dict.get("France")
  dict["France"] = "Paris"
  del dict["France"]
  del dict

  for k in dict.keys()

  for v in dict.values()

  for k, v in dict.items()



#%% md

## Built-in Modules
### Collections
1. namedtuple()
    collections.namedtuple('student', [name, age, marks]])

    s1 = student("Imran", 21, 98)

    s1.name
    s1[0]
2. collection.OrderedDict()

3. deque()
    q = collection.deque([10,20,30,40])
    q.appendleft(0)
    q.append(50)
    q.pop() ==> 50
    q.popleft() ==> 0

### Random
    random.random() ==> 0.0~1.0
    random.randint(1,100)
     random.randrange(1,10) ---> select one from the range
     random.randrange(0,100,10) ---> 20
     random.choice([1,2,3,5,7,3,2])
     random.shuffle([2,4,67,3,2,2,4])

#%% md

## Package

1. the python interpreter recognizes a folder as a package by its '__init__.py' file
2. __init__.py exposes specified resources from its modules to be imported
   empty= all exported

   from .functions (child file) import average, power(function name)

#%% md

## __main__

there's an default variable in python file: __name__
which indicates the current scope of the execution.
if the program is running at the basic level of python , aka direct run in the console,
the scope is __main__
however, if a script is imported as a module into other scripts.
now thwe scope is the package name itself. it's not __main__

Main is not the entry function like Java.


#%% md

## Iterator
iter()
Iterators are implicitly used whenever we deal with collections of Lists, tuple or strings
When we use
```python
for i in list:
    #do something
    pass
```
internally, it uses iter(list)
L1 = [1,2,3]
it = iter(L1)

it.__next__()
   (equals to)
next(it)

throw stopIteration error when nothing more to iterate.


#%% md

## Generator

other than iterator, this is the thing you can create your own iterator
this is a special type of function, it doesn't return a single value.
it returns an iterator object with a sequence of values.



#%% md

## Map Function
map is a built in function
the map function calls the specified function for each item of an iterable
it will return an iterable object,

map(function, iterable)

```python
def square(x):
    return x**2

numbers = [1,2,3,4,5]
sqrList = map(square, numbers)
```

```python
# map with lambda
sqrlist = map(lambda x : x*x, [1,2,3,4])
```




#%% md

## Filter Function
filter(function, iterable )  --> filter object (iterable)

#%% md

##Reduce Function

```python
import functools
def mult(x,y):
    print("x=",x," y=",y)
    return x*y

fact=functools.reduce(mult, range(1, 4))
print ('Factorial of 3: ', fact)
```

#%% md

## Class

Python is a OO language.  Every element in python is an Object of a class.
Number /  String / dict /

Define a class

class person:
    '''doc string: this is empty person class'''
    pass

p1 = person()

```python
class Person:
    count = 0 # class attribute
    def __init__(self):
       self.name = "unknown"
       self.age = 0
    def displayInfo(self):
       print(self.name, self.age)
```

__init__(self) is a constructor

private:

class employee:
    def __init__(self, name, sal):
        self.__name=name  # private attribute
        self.__salary=sal # private attribute
```python
>>> e1=employee("Bill",10000)
>>> e1._employee__salary
10000
>>> e1._employee__salary=20000
>>> e1._employee__salary
20000
```
