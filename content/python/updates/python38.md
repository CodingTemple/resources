<div class="cell markdown">

## Positional Only Arguments

<b>As of python 3.8</b> <p>Using a slash ( / ) as a parameter of a
function makes all the preceding parameters positional only arguments.
<br> This means you can not call the arguments by keyword. </p><br> <p>
This is useful when it is hard to name your parameters in a unambiguous
way. It is also good to know in case you are using a function defined
this way. <br> This is extremely useful when working with live code. If
the function has several other programs that rely on it, then changes
parameter name can break all those programs, but forcing positional only
allow the parameter names to change without breaking the code. </p>

</div>

<div class="cell code" data-execution_count="13" data-scrolled="false">

``` python
#You can see looking at the documentation of list that the functions take an extra ( / ) argument
help(list)
```

<div class="output stream stdout">

``` 
Help on class list in module builtins:

class list(object)
 |  list(iterable=(), /)
 |  
 |  Built-in mutable sequence.
 |  
 |  If no argument is given, the constructor creates a new empty list.
 |  The argument must be an iterable if specified.
 |  
 |  Methods defined here:
 |  
 |  __add__(self, value, /)
 |      Return self+value.
 |  
 |  __contains__(self, key, /)
 |      Return key in self.
 |  
 |  __delitem__(self, key, /)
 |      Delete self[key].
 |  
 |  __eq__(self, value, /)
 |      Return self==value.
 |  
 |  __ge__(self, value, /)
 |      Return self>=value.
 |  
 |  __getattribute__(self, name, /)
 |      Return getattr(self, name).
 |  
 |  __getitem__(...)
 |      x.__getitem__(y) <==> x[y]
 |  
 |  __gt__(self, value, /)
 |      Return self>value.
 |  
 |  __iadd__(self, value, /)
 |      Implement self+=value.
 |  
 |  __imul__(self, value, /)
 |      Implement self*=value.
 |  
 |  __init__(self, /, *args, **kwargs)
 |      Initialize self.  See help(type(self)) for accurate signature.
 |  
 |  __iter__(self, /)
 |      Implement iter(self).
 |  
 |  __le__(self, value, /)
 |      Return self<=value.
 |  
 |  __len__(self, /)
 |      Return len(self).
 |  
 |  __lt__(self, value, /)
 |      Return self<value.
 |  
 |  __mul__(self, value, /)
 |      Return self*value.
 |  
 |  __ne__(self, value, /)
 |      Return self!=value.
 |  
 |  __repr__(self, /)
 |      Return repr(self).
 |  
 |  __reversed__(self, /)
 |      Return a reverse iterator over the list.
 |  
 |  __rmul__(self, value, /)
 |      Return value*self.
 |  
 |  __setitem__(self, key, value, /)
 |      Set self[key] to value.
 |  
 |  __sizeof__(self, /)
 |      Return the size of the list in memory, in bytes.
 |  
 |  append(self, object, /)
 |      Append object to the end of the list.
 |  
 |  clear(self, /)
 |      Remove all items from list.
 |  
 |  copy(self, /)
 |      Return a shallow copy of the list.
 |  
 |  count(self, value, /)
 |      Return number of occurrences of value.
 |  
 |  extend(self, iterable, /)
 |      Extend list by appending elements from the iterable.
 |  
 |  index(self, value, start=0, stop=9223372036854775807, /)
 |      Return first index of value.
 |      
 |      Raises ValueError if the value is not present.
 |  
 |  insert(self, index, object, /)
 |      Insert object before index.
 |  
 |  pop(self, index=-1, /)
 |      Remove and return item at index (default last).
 |      
 |      Raises IndexError if list is empty or index is out of range.
 |  
 |  remove(self, value, /)
 |      Remove first occurrence of value.
 |      
 |      Raises ValueError if the value is not present.
 |  
 |  reverse(self, /)
 |      Reverse *IN PLACE*.
 |  
 |  sort(self, /, *, key=None, reverse=False)
 |      Sort the list in ascending order and return None.
 |      
 |      The sort is in-place (i.e. the list itself is modified) and stable (i.e. the
 |      order of two equal elements is maintained).
 |      
 |      If a key function is given, apply it once to each list item and sort them,
 |      ascending or descending, according to their function values.
 |      
 |      The reverse flag can be set to sort in descending order.
 |  
 |  ----------------------------------------------------------------------
 |  Static methods defined here:
 |  
 |  __new__(*args, **kwargs) from builtins.type
 |      Create and return a new object.  See help(type) for accurate signature.
 |  
 |  ----------------------------------------------------------------------
 |  Data and other attributes defined here:
 |  
 |  __hash__ = None

```

</div>

</div>

<div class="cell code" data-execution_count="8" data-scrolled="true">

``` python
#Works
list([1,2,3])
#Gives TypeError
list(iterable=[1,2,3])
```

<div class="output error" data-ename="TypeError" data-evalue="list() takes no keyword arguments">

    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    <ipython-input-8-29856004340d> in <module>
          1 list([1,2,3])
    ----> 2 list(iterable=[1,2,3])
    
    TypeError: list() takes no keyword arguments

</div>

</div>

<div class="cell code" data-execution_count="12">

``` python
#Use in a function
def greet(first_name, middle_name, /, last_name):
    print(f"Hello {first_name} {middle_name} {last_name}!")

#Works    
greet("John", "Q", "Public")
#Works
greet("John", "Q", last_name="Public")
#Gives TypeError
greet("John", middle_name="Q", last_name="Public")
```

<div class="output stream stdout">

    Hello John Q Public!
    Hello John Q Public!

</div>

<div class="output error" data-ename="TypeError" data-evalue="greet() got some positional-only arguments passed as keyword arguments: &#39;middle_name&#39;">

    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    <ipython-input-12-d7ab98fdeab5> in <module>
          8 greet("John", "Q", last_name="Public")
          9 #Doesn't work
    ---> 10 greet("John", middle_name="Q", last_name="Public")
    
    TypeError: greet() got some positional-only arguments passed as keyword arguments: 'middle_name'

</div>

</div>

<div class="cell markdown">

## Keyword Only Arguments

This is nothing new, but the converse of the positional only argument.
<br> This is the asterisk( \* ) argument. Every parameter following the
asterisk with be a keyword only argumeter. <br> This can be combines
with positional arguments.

</div>

<div class="cell code" data-execution_count="18">

``` python
def get_info(first_name, last_name, / , weight, *, height, hair_color):
    print(f"{first_name} {last_name} is {weight} pounds, {height} inches tall, and has {hair_color} hair")
    
#Works
get_info("Jessica", "Alba", 121, height=67, hair_color="brown" )
#Works
get_info("Jessica", "Alba", weight=121, height=67, hair_color="brown" )
#Doesn't work
get_info("Jessica", "Alba", 121, 67, hair_color="brown" )
```

<div class="output stream stdout">

    Jessica Alba is 121 pounds, 67 inches tall, and has brown hair
    Jessica Alba is 121 pounds, 67 inches tall, and has brown hair

</div>

<div class="output error" data-ename="TypeError" data-evalue="get_info() takes 3 positional arguments but 4 positional arguments (and 1 keyword-only argument) were given">

    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    <ipython-input-18-d379977e8664> in <module>
          7 get_info("Jessica", "Alba", weight=121, height=67, hair_color="brown" )
          8 #Doesn't work
    ----> 9 get_info("Jessica", "Alba", 121, 67, hair_color="brown" )
    
    TypeError: get_info() takes 3 positional arguments but 4 positional arguments (and 1 keyword-only argument) were given

</div>

</div>

<div class="cell markdown">

### The Assignment Expression -- The Walrus := Operator<br>

<b>As of Python 3.8</b><br><p> The assignment expression allows the
assignment and the return of a value in the same expression <br> This
does not do anything that cannot be without it, but it makes some
constructs easier to achieve with better readability <br> The scope of
the assigned varible will leak out of the while loop. </p>

</div>

<div class="cell code" data-execution_count="25">

``` python
#You can assign a varible
food = "Taco"
#Then use the varible
print(food)
```

<div class="output stream stdout">

    Taco

</div>

</div>

<div class="cell code" data-execution_count="26" data-scrolled="true">

``` python
#You cannot assign the varible and use it at the same time, because it will be treated as a keyword argument
print(food="Taco")
```

<div class="output error" data-ename="TypeError" data-evalue="&#39;food&#39; is an invalid keyword argument for print()">

    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    <ipython-input-26-68a1af5422bd> in <module>
          1 #You cannot assign the varible and use it at the same time, because it will be treated as a keyword argument
    ----> 2 print(food="Taco")
    
    TypeError: 'food' is an invalid keyword argument for print()

</div>

</div>

<div class="cell code">

``` python
#The walrus operator changes that
print(food:="Taco")
print(f"I Love {food}'s!")
```

</div>

<div class="cell markdown">

### Usage in While loops

<br> <p>Follow the evolution of the following command line program to
create a word bank from user input</p>

</div>

<div class="cell code" data-execution_count="22">

``` python
# This works but you have to ask for input twice 
word_bank=list()
word=input("Enter a word or type Q to Quit: ")
while(word != "Q"):
    word_bank.append(word)
    word=input("Enter a word or type Q to Quit: ")
    
```

<div class="output stream stdout">

    Enter a word or type Q to Quit: I
    Enter a word or type Q to Quit: ain't
    Enter a word or type Q to Quit: got
    Enter a word or type Q to Quit: no
    Enter a word or type Q to Quit: game,
    Enter a word or type Q to Quit: it's
    Enter a word or type Q to Quit: just
    Enter a word or type Q to Quit: some
    Enter a word or type Q to Quit: bitches
    Enter a word or type Q to Quit: understand
    Enter a word or type Q to Quit: my
    Enter a word or type Q to Quit: story
    Enter a word or type Q to Quit: Q

</div>

</div>

<div class="cell code" data-execution_count="23">

``` python
# This is better but harder to understand how the loop breaks
word_bank=list()
while True:
    word=input("Enter a word or type Q to Quit: ")
    if word=="Q":
        break
    word_bank.append(word)
```

<div class="output stream stdout">

    Enter a word or type Q to Quit: I'm
    Enter a word or type Q to Quit: out
    Enter a word or type Q to Quit: for
    Enter a word or type Q to Quit: dead
    Enter a word or type Q to Quit: presidents
    Enter a word or type Q to Quit: to
    Enter a word or type Q to Quit: represent
    Enter a word or type Q to Quit: me
    Enter a word or type Q to Quit: Q

</div>

</div>

<div class="cell code" data-execution_count="24">

``` python
#The Walrus operator allows this to be done in less lines with better readability
word_bank=list()
while word:=input("Enter a word or type Q to Quit: ") != "Q":
    word_bank.append(word)
```

<div class="output stream stdout">

    Enter a word or type Q to Quit: I
    Enter a word or type Q to Quit: never
    Enter a word or type Q to Quit: sleep
    Enter a word or type Q to Quit: 'cause
    Enter a word or type Q to Quit: sleep
    Enter a word or type Q to Quit: is
    Enter a word or type Q to Quit: the
    Enter a word or type Q to Quit: cousin
    Enter a word or type Q to Quit: of
    Enter a word or type Q to Quit: death.
    Enter a word or type Q to Quit: Q

</div>

</div>

<div class="cell code">

``` python
#The scope of the assigned varible word is now
word_bank=list()
while word:=input("Enter a word or type Q to Quit: ") != "Q":
    word_bank.append(word)
```

</div>

<div class="cell markdown">

### Usage in comprehensions

</div>

<div class="cell code" data-execution_count="39">

``` python
#You can reduce redunancy in comprehensions
def cubed(n):
    return n**3
#instead of
cubed_dictionary={x: cubed(x) for x in [1,2,3,4,5] if cubed(x) < 500}
print (cubed_dictionary)

#we can now (notice the parentheses)
cubed_dictionary={x: new_var for x in [1,2,3,4,5] if (new_var:=cubed(x)) < 500}
print(cubed_dictionary)
print(new_var) # new_var leaks the scope of the comprehension
```

<div class="output stream stdout">

    {1: 1, 2: 8, 3: 27, 4: 64, 5: 125}
    {1: 1, 2: 8, 3: 27, 4: 64, 5: 125}
    125

</div>

</div>
