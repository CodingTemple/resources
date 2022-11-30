# The 4 Pillars of Object-Oriented Programming:
<br>

Object-Oriented Programming (OOP) is a programming paradigm that can involve different languages and lingo.  Essentially the focus is designing software around objects that contain data and custom methods for handling that data. The 4 pillars provide a basic outline of the use and benefits of OOP.

### The 4 Pillars are:

<ul><strong>
<li>Abstraction
<li>Encapsulation
<li>Inheritance
<li>Polymorphism
</strong>
</ul>


**Abstraction** and **Encapsulation** are closely related as are <br>
**Inheritance** and **Polymorphism**.  It can be helpful for the sake of memory and comprehension to remember these relationships.
<br>

## **Abstraction**

*Abstraction* is commonly viewed as either hiding information within a class or only displaying relevant content.  Viewed through either lens the result is the same: internal implementation details may not be accessible or relevant.  Imagine starting a car.  We get in and press the button or turn the key and moments later the car is running.  Clearly the key doesn't make everything happen!  Example via Python to start a car:

    Fiero = Car()
    # creates an instance of the Car class

    Fiero.start_car()
    # executes the start_car method

#### vs just a peek of what's going on under the hood:

    class Car:
        def __init__(self):
            . . . 

        def starter(self):
            . . . 

        def ignition(self):
            . . . 
        
        . . . 

        def start_car(self):
            self.starter()
            self.ignition()
            self.fuel()
            self.lights()
            self.gauges()

## **Encapsulation**

*Encapsulation* refers to bundling data, and methods for manipulating said data, that makes a class.  Basically a class should contain everything it needs!  To go back to the car example from above; you probably wouldn't be happy if you had to bring a battery or seat to a car every time you needed it to go somewhere.  

On the flip side, data and methods *encapsulated* within a class may not not be accessible from outside.

    class User:
        def __init__(self, username, password, full_name):
            self.username = username
            self._full_name = full_name
            #    ^-- protected
            self.__password = password
            #    ^-- private
    
    d = User('bsmit', 'Supersecret!', 'Bill Smith')

    print(d.username)
    print(d._full_name)
    print(d.__password)

*Output:*
>bsmit

>Bill Smith

>AttributeError: 'User' object has no attribute '__password'

## **Inheritance**

*Inheritance* means that a class can gain the attributes of another just like a child may inherit attributes from their parents.  As an example here I've created a generic class called Book.  Because we're interested in reading books about programming languages we'll also create a class ProgrammingLanguageBooks that inherits the attributes and methods of Book:

    class Book:
        def __init__(self, title, subject, author):
            self.title = title
            self.subject = subject
            self.author = author

Now to create our child class that inherits from Book above:

    class ProgrammingLanguageBooks(Book):
        def __init__(self, title, subject, author):
            super().__init__(title, subject, author)

Finally let's add an attribute for our new class on top of what it has already inherited:

    class ProgrammingLanguageBooks(Book):
        def __init__(self, title, subject, author, prog_language):
            super().__init__(title, subject, author)
            self.prog_language = prog_language

## **Polymorphism**

*Polymorphism* can be broken down as a word for better understanding:
- Poly (Many)
- morph (form)

**Many Forms** is the essential understanding.  We'll take you as an example (yes, YOU!).  You may be a parent, student, academic, worker, programmer, soccer player, gamer, etc.  You can be all of this things at the same time while certain situations may only apply to specific ones (does your soccer team really care about your programming skills?).

### **Two examples in Python classes:**

Here we're calling methods regardless of class type:
    class GasCar:
        def replenish(self):
            print('Filling fuel tank. . .')
            print('Full Tank, let\'s roll!')

    class ElectricCar:
        def replenish(self):
            print('Charging Battery. . .')
            print('Fully Charged, let\'s rock!' )
    ford = GasCar()
    tess = ElectricCar()
    for x in (ford, tess):
        x.replenish()

*Output:*
>Filling fuel tank. . .

>Full Tank, let's roll!

>Charging Battery. . .

>Fully Charged, let's rock!


Here's an example using *Method Overriding* (re-defining a method in a child class):

    class Car:
        def replenish(self):
            print('Filling fuel tank. . .')
            print('Full Tank, let\'s roll!')

    class ElectricCar(Car):
        def replenish(self):
            print('Charging Battery. . .')
            print('Fully Charged, let\'s rock!' )
    ford = Car()
    tess = ElectricCar()
    for x in (ford, tess):
        x.replenish()

The output is the same as the previous example!  The difference is that ElectricCar has inherited the replenish method from Car and the method is overridden.