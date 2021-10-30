# Python 101 xD
 
Alright, if you know programming and you just want to jump into python, this crashcourse is for you!<br />
It's just the basics of the python's syntax to boost you a little bit. :)<br />
without wasting time, let's crack on!

# Hello World


```python
# First program in python!
# Yay and blah blah blah!
print("Hello World!")
# Done!
```

    Hello World!
    

# Variables


```python
# There is no such thing as "data type".
# Wait what?
my_variable = 12 #int
my_variable = 12.0 #float
my_variable = True #boolean
my_variable = "This is a 'string' " #string
my_variable = 'This is also a "string" '
# '' and "" are pretty much the same thing 
```

# Comments


```python
# There are two ways to write comments.
# Frist with '#' as you see now
# And with ''' '''
# Or """ """
'''This is a comment'''

"""
You
can
write
multiline
comments    
"""
# This is a string as well, look below!
print("""
    This is a string
    So
    I can
    Print it!
    :)
""")
# With '#' you can write only one line comments
```

    
        This is a string
        So
        I can
        Print it!
        :)
    
    

# Data Structures

## List


```python
# In python, we have list, Tuple and Dictionary as main Data Structures
# We only talk about lists in this part
```


```python
'''
So lists are like arrays.
But!
you don't need to initialize a lenght for it! :)
For example:
'''
my_list = list()
''' Yep! That's it! '''

# You can also define a list this way
my_list = []
```


```python
# Let me show you something intersting!
my_list = [1, 2, 12.0, 'bullshit', True]
# See! You can put any type in a list! Interesting huh!



# Let's see how we can add something in our list!
my_list.append(13) # my_list = [1, 2, 12.0, 'bullshit', True, 13]
# "append" method will add to the end of the list.


# We can also add data to our list with "insert" method. First argument is index and the second one is data.
my_list.insert(1, 12) # my_list = [1, 12, 2, 12.0, 'bullshit', True, 13]



# Lists also can be used as stacks.
# As you know "append" method adds to the end of the list.
#Then we have the "pop" method. It will remove from the end of the list and return that item.
poped_item = my_list.pop() # my_list = [1, 12, 2, 12.0, 'bullshit', True] , poped_item: 13


# Lists as queues?
# The pop method can also get an argument as an index. So we have a queue here! TADA!
poped_item = my_list.pop(0) # my_list = [12, 2, 12.0, 'bullshit', True] , poped_item: 12


# You can also delete an item directly from your list.
# Simply call the "remove" method! Cool right? :)
my_list.remove(12.0)
# Our list should be like this: [2, 12.0, 'bullshit', True]

# Hold on now! What happened there?
# We wanted to delete 12.0 not 12!
# So in Python, 12 and 12.0 are equal!

# "remove" method starts iterating on the list and checks if the item is what we want to remove or not.
# And if we have similar items in our list, "remove" method will delete the item that has the lowest index.
# In this case, the first item in my_list is 12 and we want 12.0. These are the same to python so it just deleted 12.

print(my_list)
```

    [2, 12.0, 'bullshit', True]
    


```python
# The first index in python is 0
print(my_list[0])

# If you want to find the lenght of any object(obviously it has to be iterable) you can use "len" method.
# In our case, the iterable object is the list
print(len(my_list))

# FYI: "list" is not the only iterable object
```

    2
    4
    


```python
# Question:
# What do you expect when you see this syntax "my_list[-1]" ?
# Let's try it
print(my_list[-1])
```

    True
    


```python
# What happened?
# Our list is [2, 12.0, 'bullshit', True]. Then the last object in the list is "True".
# So... Yup! We have negative index in python!
# But you should be careful with that.
# For example:
print(my_list[-5])
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-6-4f99dcda318a> in <module>
          4 # But you should be careful with that.
          5 # For example:
    ----> 6 print(my_list[-5])
    

    IndexError: list index out of range



```python
# You can only go up to the end of list
my_list[-len(my_list)]
```




    2




```python
# Imagine I have a list like this
my_list = [1, 2, 4,4,3,6,8, 5,9]

# And I want some part of it! for example from index 2 up to index 5
# In other programming languages like C we do something like this:
'''
for(int i=2; i < 6; i++){
   newList[i-2] = my_list[i]; #as you may know we creates a new list and called it newList and etc 
} 
'''
# But it's way easier in python:
print(my_list[2:6])
# From index "i" till index "j-1"(in this case i=2 and j=6)
# We call this "slicing"!
```

    [4, 4, 3, 6]
    


```python
# There is also a third argument that defines step!
# For example I want to go from index 1 up to index 5 with step=2: [2, 4, 6]
my_list[1:6:2]
# That's it!
```




    [2, 4, 6]




```python
# There are many built-in methods in "list" object. One of them is "sort"
print('Not sorted list: ',my_list)
my_list.sort()
print('Sorted list: ', my_list)
```

    Not sorted list:  [1, 2, 4, 4, 3, 6, 8, 5, 9]
    Sorted list:  [1, 2, 3, 4, 4, 5, 6, 8, 9]
    


```python
# What if I wanted to reverse my list?
# Python is a language for lazy poeple(like me :D)
print('Not reversed list: ',my_list)
my_list.reverse()
print('Reversed list: ', my_list)
# EZ PZ
```

    Not reversed list:  [1, 2, 3, 4, 4, 5, 6, 8, 9]
    Reversed list:  [9, 8, 6, 5, 4, 4, 3, 2, 1]
    


```python
# There is another way if you don't like to use that method
'''
Remember the slicing part?
We can pass a step arg to list, right?
What if I pass -1 for step?
'''
my_list = [1, 2, 3, 4, 4, 5, 6, 8, 9] # This is my_list before the reverse method, right?
# Check this out!
print(my_list[::-1]) # [9, 8, 6, 5, 4, 4, 3, 2, 1]
```

    [9, 8, 6, 5, 4, 4, 3, 2, 1]
    


```python
# It's simply reversed!

# Next, we're gonna talk about tuples
```

## Tuples


```python
# Tuples are very similar to lists

# You can define a tuple like a list
my_tuple = tuple()
# or
my_tuple = (1, 2, 12.0, 'bullshit', True, [], ())
# And you can put anything in tuples and lists, because we don't have any data type in python. 
```


```python
# What if I wanted to define a one item tuple?
# Using the keyword
my_tuple_with_one_item = tuple([1]) # What is that list doing in there?
# tuple() has one optional argument and it has to be an iterable object
# Also I can get the same result:
my_tuple_with_one_item = (1, )
# What is that comma?
# it has to be there for python to understand that this is a tuple, otherwise the python interpreter recognizes
# this is a normal number and the perentesis as the operators
print(my_tuple_with_one_item)
```

    (1,)
    


```python
# We can iterate on tuples like lists and any other iterable object
print(my_tuple[0])
print(my_tuple[::-1])
```

    1
    ((), [], True, 'bullshit', 12.0, 2, 1)
    


```python
# You can use everything that we talked about in list, for tuples
"""EXCEPT ONE THING!"""
# tuples are immutable!
# What does it mean?
# It means you can't change the data stored in tuples!
```


```python
my_tuple[0] = 2
'''
TypeError: 'tuple' object does not support item assignment
'''
# That's what I'm talking about.
# Avoid these for safety measures.
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-17-ffab84a18bfc> in <module>
    ----> 1 my_tuple[0] = 2
          2 '''
          3 TypeError: 'tuple' object does not support item assignment
          4 '''
          5 # That's what I'm talking about.
    

    TypeError: 'tuple' object does not support item assignment


## Python is a good calculator


```python
# Python is also a very good calculator
# Normal arithmetic operators like '+', '-', '*', '/' are similar to other programing languages
print('1 + 2 = ', 1 + 2)
print('2 * 4.5 = ', 2 * 4.5)
print('10 - 2.5 = ', 10 - 2.5)
print('1 / 2 = ', 1/2)# '/' operator returns float numbers.
# If you don't like floats you can use '//' operator. This returns just the integer part of the number
print('5 // 2 = ', 5//2)
# You can also use '**' operator as power
print('2 ** 3 = ',2**3)
```

    1 + 2 =  3
    2 * 4.5 =  9.0
    10 - 2.5 =  7.5
    1 / 2 =  0.5
    5 // 2 =  2
    2 ** 3 =  8
    

## Dictionary


```python
# Dictionary is a non sequence datastructure with a "key, value" system.
# it means that you define a key and add a value for that specific key.
# You can define an empty dictionary with the 'dict()' method.
my_dict = dict()
print(my_dict)
```

    {}
    


```python
# Or you can define it like this.
# key, and ":" , value.
my_dict = {
    'key': 'value',
    'key1': 'value1',
    'key2': 'value2',
}
# There is no data type, so your key and value can be anything you want.
# But keys are uniqe! Just try to keep your code clean xD
print(my_dict)
```

    {'key': 'value', 'key1': 'value1', 'key2': 'value2'}
    


```python
# You can simply call a key and it will return the expected value.
print(my_dict['key']) # Should be 'value'
```

    value
    


```python
# If you want to add a pair of <key, value> you can do this:
# my_dict[<key>] = <value>
# For example
my_dict['key3'] = 'value3'
print( my_dict)
print(my_dict['key3'])
```

    {'key': 'value', 'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}
    value3
    


```python
# Dictionary has a "popitem()" method.
# It'll delete and return the last added "key, value".
my_dict.popitem()
```




    ('key3', 'value3')




```python
# It also has an optional argument that using which you can pass a key and it'll delete the expected value and return it.
my_dict.pop("key")
print(my_dict)
```

    {'key1': 'value1', 'key2': 'value2'}
    

## Statements


```python
# There are a few operators like '==', '!=', '>=', '<=' using which you can compare two objects.
print(1 == 2)
print(1 >= 2)
print(1 <= 2)
print(1 != 2)
# You can also do chain operators
print(1 < 2 < 3 < 10 > 5)
# If one of them is false, the whole statement is false.
print(1 < 2 < 3 > 10 > 5)
```

    False
    False
    True
    True
    True
    False
    

## if


```python
# For 'if' we do this:
if 1 == 2:
    print('blah blah blah')
else:    
    print('blah blah blah 2')

# There is also nested if.
if 1 == 2:
    print('1 == 2')
else:
    if 2 == 2:
        print('2 == 2')
    else:
        print('blah blah blah 3')
        
# But this is so ugly!
# Then let me introduce you to 'elif'.
# 'elif' is else then if!
if 1 == 2:
    print('1 == 2')
elif 2 == 2:
    print('2 == 2')
else:
    print('blah blah blah 3')
```

    blah blah blah 2
    2 == 2
    2 == 2
    

## while


```python
# The first kind of loop :)
"""
while condition:
    do something!
"""
# That's it!
# Example: 
i = 0
while i < 10:
    print('I is: ', i)
    i += 1
```

    I is:  0
    I is:  1
    I is:  2
    I is:  3
    I is:  4
    I is:  5
    I is:  6
    I is:  7
    I is:  8
    I is:  9
    


```python
# You want to stop the while whenever you want?
# No problem!
i = 0
while True:
    i += 1
    if i > 15:
        break
# 'break' will stop the while and moves on to the rest of the code
```

## for


```python
# 'for' In python is like 'for each' in java
my_list = [1, 2, 3, 4]
for item in my_list:
    print('item is: ', item)
```

    item is:  1
    item is:  2
    item is:  3
    item is:  4
    


```python
# What if I want to use 'for' like a normal for?
# Well, check this out!
for i in range(0, 10):
    print('I is: ', i)
```

    I is:  0
    I is:  1
    I is:  2
    I is:  3
    I is:  4
    I is:  5
    I is:  6
    I is:  7
    I is:  8
    I is:  9
    


```python
# range() is a built-in function that returns a range from the first argument up to the second argumnet
# with the step of the third argument.
# for example:
for i in range(0, 10):
    print(i)
'''
out:
0
1
2
3
4
5
6
7
8
9
'''
for i in range(5, 10, 2):
    print(i)
'''
out:
5
7
9
'''
```


```python
# You can put any iterable object after 'in' when using 'for':
my_dict = {
    'item 1': 'value 1',
    'item 2': 'value 2',
    'item 3': 'value 3',
    'item 4': 'value 4'
}
for item in my_dict:
    print(my_dict[item])
```

    value 1
    value 2
    value 3
    value 4
    

# Functions


```python
# To define finctions:
'''
def <function name>():
    whatever!
'''
# That's it! You're all set!
def my_func():
    print('Yay! My function is working!')
```


```python
# What if I wanted to get argumants for my function?
# Simple!
'''
def <function name>(arg1, arg2, arg3):
    whatever!
'''
def my_func2(name, family, age):
    print('Hi! my name is ' + name + ' ' + family + ". and I'm " + age)
# How am I gonna use it?
# By calling it!
my_func2('Ali', 'Daghighi', '21')
```

    Hi! my name is Ali Daghighi. and I'm 21
    


```python
# If you want, you can give them a default value by assigning the value to each argument while you're writing the function
def my_func3(name='Ali', family='Daghighi', age='21'):
    print('Hi! my name is ' + name + ' ' + family + ". and I'm " + age)
    
my_func3()
```

    Hi! my name is Ali Daghighi. and I'm 21
    


```python
# What if we don't know the number of arguments?
# Ez Pz

def my_func4(name='Ali', *other_stuff):
    print("Hi my name is " + name + " and some other stuff xD")
    for var in other_stuff:
        print(var)

my_func4('Ali', 'Some', 'Random', 'Other', 'Stuff')
```

    Hi my name is Ali and this is some other stuff xD
    Some
    Random
    Other
    Stuff
    


```python
# What about return?
# You just have to return whatever you want at the end of the function

def my_func5(*args):
    resault = 0
    for arg in args:
        resault += arg
    return resault

print(my_func5(1 ,2, 3, 4))
```

    10
    

# Scope of Variables


```python
# "So All variables in a program may not be accessible at all locations in that program."
# What does it mean?
# That means "where have you declared a variable?"
# let me elaborate:
# In python we have "Global variables" and "Local variables" 

total = 0; # This is a global variable.
# Now we have this function:
def sum( arg1, arg2 ):
    # Add both parameters and return them."
    total = arg1 + arg2; # the total is a local variable.
    print("Inside the function local total : ", total)
    return total;

# Now you can call the "sum" function
sum( 10, 20 );
print("Outside the function global total : ", total)
```

    Inside the function local total :  30
    Outside the function global total :  0
    


```python
# What if we needed access to the global variable?

# Check this example:

name = "Bianca Peterson"
print("Before:\t", name)
def setName():
    global name
    name = "Bianca Lucinda Peterson"

setName()
print("After:\t", name)

# Using the keyword "global" you can access the outer scope
```

    Before:	 Bianca Peterson
    After:	 Bianca Lucinda Peterson
    

# files


```python
# Python has a built-in "open()" function for opening a file.
# This function returns a file object, also called a handle, as it is used to read or modify the file accordingly

f = open("test.txt")    # open file in current directory

#                       "OR"

f = open("C:/Python38/README.txt")  # specifying full path
```


```python
# The default is reading in text mode
# On the other hand, binary mode returns bytes and this is the mode to be used when dealing with -
# non-text files like images or executable files

# There are a few modes that you can use to open a file:

# r : Opens a file for reading. (default)

# w : Opens a file for writing. Creates a new file if it does not exist
#     or truncates the file if it exists.

# x : Opens a file for exclusive creation.
#     But if the file already exists, the operation fails.

# a : Opens a file for appending at the end of the file without truncating it.
#     Creates a new file if it does not exist

# t : Opens in text mode. (default)

# b : Opens in binary mode.

# + : Opens a file for updating (reading and writing)


f = open("test.txt")      # equivalent to 'r' or 'rt'
f = open("test.txt",'w')  # write in text mode
f = open("img.bmp",'r+b') # read and write in binary mode
```


```python
# For closing file:

f.close()
# Tada!
```


```python
# Since we are working with files, it's time to see how error handling works in Python
```

# Exceptions Handling


```python
# we are gonna use the "try" and "except" statments for handling exceptions.
# This is a simple try and except block:

try:
   # your operations here
   
except ExceptionI:
   # If there is ExceptionI, execute this block.

except ExceptionII:
   # If there is ExceptionII, execute this block.

else:
   # If there is no exception, execute this block. 

```


```python
# Let's try that
try:
    fh = open("testfile", "r")
    fh.write("This is my test file for exception handling!!")
except IOError:
    print("Error: can\'t find file or read data")
else:
    print("Written content in the file successfully")
    fh.close()
```

    Error: can't find file or read data
    


```python
# What if I want to have multiple exceptoins?

try:
   # Your operations here

except(Exception1[, Exception2[,...ExceptionN]]):
   # If there is any exception from the given exception list, 
   # then execute this block.
   
else:
   # If there is no exception, execute this block.
```


```python
# There is also a try-finally Clause

try:
   # Your operations here
   # ......................
   # Due to any exception, this may be skipped.

finally:
   # This would always be executed.
   # ......................

```


```python
# For the argument of an Exception we can do this:

try:
   # Your operations here
   # ......................

except ExceptionType, Argument:
   # Print value of Argument here...
```

# class


```python
# Python has been an object-oriented language since the beginning.
# Creating and using classes and objects are easy

######################################## BREAKING POINT ########################################

# I assume that you know OOP(object-oriented programming)
# But if you don't know..... well I can't tell you the whole OOP paradigm here but here are some pointer:

"""
Class − A user-defined prototype for an object that defines a set of attributes that characterize any object of the class.
        The attributes are data members (class variables and instance variables) and methods, accessed via dot notation.

Class variable − A variable that is shared by all instances of a class.
                Class variables are defined within a class but outside any of the class's methods.
                Class variables are not used as frequently as instance variables are.

Data member − A class variable or instance variable that holds data associated with a class and its objects.

Function overloading − The assignment of more than one behavior to a particular function.
                       The operation performed varies by the types of objects or arguments involved.

Instance variable − A variable that is defined inside a method and belongs only to the current instance of a class.

Inheritance − The transfer of the characteristics of a class to other classes that are derived from it.

Instance − An individual object of a certain class. An object obj that belongs to a class Circle,
           for example, is an instance of the class Circle.

Instantiation − The creation of an instance of a class.

Method − A special kind of function that is defined in a class definition.

Object − A unique instance of a data structure that's defined by its class.
         An object comprises both data members (class variables and instance variables) and methods.

Operator overloading − The assignment of more than one function to a particular operator
"""
```


```python
# Defining a class is similar to a function:

class ClassName:
   # 'Optional class documentation string'
   #  class_suite

```


```python
# Let's see an example

class Employee:
    'Common base class for all employees'
    empCount = 0

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
        Employee.empCount += 1
   
    def displayCount(self):
        print("Total Employees " + Employee.empCount)

    def displayEmployee(self):
        print("Name : ", self.name,  ", Salary: ", self.salary)
        
# But this is not similar to functions at all!

# Let's go step by step.
# We have a keyword definition for class which is "class", and the name of the class.
# After that we have the "empCount" which is the base attribute for the Employee class.
# Then we have "def __init__"
# The __init__() Function:
# All classes have a function called __init__() which is always executed when the class is being initiated
# And the other two functions are the methods of the class.
# You declare other class methods like normal functions with the exception that the first argument to each method is "self"
# Python adds the self argument to the list for you, so you do not need to include it when you call the methods.
```


```python
# To create instances of a class, you call the class using the class name
# and pass in whatever arguments its __init__ method accepts

# This creates the first object of the Employee class
emp1 = Employee("Zara", 2000)

# This creates the second object of the Employee class
emp2 = Employee("Manni", 5000)
```


```python
# You can access the object's attributes using the dot operator with an object like java
emp1.displayEmployee()
emp2.displayEmployee()
print("Total Employees: " + str(Employee.empCount))
```

    Name :  Zara , Salary:  2000
    Name :  Manni , Salary:  5000
    Total Employees: 2
    


```python
# You can add, remove, or modify attributes of classes and objects at any time.

emp1.age = 7  # Add an 'age' attribute.
emp1.age = 8  # Modify 'age' attribute.
del emp1.age  # Delete 'age' attribute.
```


```python
# Instead of using the normal statements to access attributes, you can use the following functions:

# The getattr(obj, name[, default]) − to access the attribute of object.
# The hasattr(obj,name) − to check if an attribute exists or not.
# The setattr(obj,name,value) − to set an attribute. If attribute does not exist, then it would be created.
# The delattr(obj, name) − to delete an attribute.

setattr(emp1, 'age', 8) # Set attribute 'age' at 8
getattr(emp1, 'age')    # Returns value of 'age' attribute
hasattr(emp1, 'age')    # Returns true if 'age' attribute exists
delattr(emp1, 'age')    # Delete attribute 'age'
```


```python
# There are a few built-in Class Attributes:

# __dict__ − Dictionary containing the class's namespace
# __doc__ − Class documentation string or none, if undefined
# __name__ − Class name.
# __module__ − Module name in which the class is defined. This attribute is "__main__" in interactive mode
"""
yeah I haven't talked about the modules.
"""
# __bases__ − A possibly empty tuple containing the base classes, in the order of their occurrence in the base class list.

# Let's try these for the Employee class

print("Employee.__doc__:", Employee.__doc__)
print("Employee.__name__:", Employee.__name__)
print("Employee.__module__:", Employee.__module__)
print("Employee.__bases__:", Employee.__bases__)
print("Employee.__dict__:", Employee.__dict__)
```

    Employee.__doc__: Common base class for all employees
    Employee.__name__: Employee
    Employee.__module__: __main__
    Employee.__bases__: (<class 'object'>,)
    Employee.__dict__: {'__module__': '__main__', '__doc__': 'Common base class for all employees', 'empCount': 2, '__init__': <function Employee.__init__ at 0x00000218210FF550>, 'displayCount': <function Employee.displayCount at 0x00000218210FF280>, 'displayEmployee': <function Employee.displayEmployee at 0x00000218210FF1F0>, '__dict__': <attribute '__dict__' of 'Employee' objects>, '__weakref__': <attribute '__weakref__' of 'Employee' objects>}
    


```python
# Destroying Objects?
# Like java, Python deletes unneeded objects (built-in types or class instances) -
# automatically to free the memory space

# Python's garbage collector runs during program execution and is triggered when an object's reference count reaches zero.
# An object's reference count changes as the number of aliases that point to it changes
```

## Class Inheritance


```python
# A class in python can have many parents

class SubClassName (ParentClass1[, ParentClass2, ...]):
    'Optional class documentation string'
    class_suite
```


```python
# Let's see an example:

class Parent:        # define parent class
    parentAttr = 100
    def __init__(self):
        print("Calling parent constructor")

    def parentMethod(self):
        print('Calling parent method')

    def setAttr(self, attr):
        Parent.parentAttr = attr

    def getAttr(self):
        print("Parent attribute :", Parent.parentAttr)

class Child(Parent): # define child class
    def __init__(self):
        print("Calling child constructor")

    def childMethod(self):
        print('Calling child method')

c = Child()          # instance of child
c.childMethod()      # child calls its method
c.parentMethod()     # calls parent's method
c.setAttr(200)       # again call parent's method
c.getAttr()          # again call parent's method
```

    Calling child constructor
    Calling child method
    Calling parent method
    Parent attribute : 200
    


```python
# you can drive a class from multiple parent classes in a similar way, as follows

class A:        # define class A
    # .....

class B:         # define class B
    # .....

class C(A, B):   # subclass of A and B
    # .....
```

## Overriding Methods


```python
# You can always override the parent methods using:

class Parent:        # define parent class
    def myMethod(self):
        print('Calling parent method')

class Child(Parent): # define child class
    def myMethod(self):
        print('Calling child method')

c = Child()          # instance of child
c.myMethod()         # child calls overridden method
```

    Calling child method
    

## Data Hiding


```python
# If you want an object's attributes to not be visible outside the class definition,
# You need to name attributes with a double underscore prefix
# Those attributes will not be directly visible to outsiders
# Let's see an example

class JustCounter:
    __secretCount = 0 # Our secret attr
  
    def count(self):
        self.__secretCount += 1
        print(self.__secretCount)

counter = JustCounter()
counter.count()
counter.count()
print(counter.__secretCount) # We're gonna get an error for this line
```

    1
    2
    


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-48-4c10b3a36e61> in <module>
         14 counter.count()
         15 counter.count()
    ---> 16 print(counter.__secretCount) # We gonna ge an error for this line
    

    AttributeError: 'JustCounter' object has no attribute '__secretCount'


----

### This is it for now!

I'm gonna end the file here. <br />
If you need someone to ask for help, you can find me in [GitHub](https://github.com/alidaghighi) <br />
or just use google it!<br />
<br />
<b> Happy coding! </b>
