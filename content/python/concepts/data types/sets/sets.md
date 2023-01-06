# Sets. What are they and when to use them?
<br>

A Set is a unordered, unchangeable (The items are unchangeable, but you can add or remove items as needed), and unindexed built-in data type for Python. They are generally represented using curly brackets, such as:

    my_set = {"This", "is", "a", "set"}

They can also be instantiated using set(): 

    emptySet = set()

    Example:
    favoriteFruits: set(['Pineapple', 'Strawberry', 'Blueberry'])

The question is though, why do you want to use a set? When would using this datatype be more useful than using a list or a dictionary?

## Remove Duplicates
There are three primary reasons that people, especially new python programmers, use sets:

The first is that it is an excellent way of removing **duplicates**. For example, lets say that you have a list of elements that you want to be unique, but somehow it got full of a lot of the same values. So long as order isn't something necessary, a set is a quick and easy solution for sorting out the problem. For example: 

    Let's say that you have a list of pies, but someone out there really wanted to prove that they love apple pie.
    You don't need all of these repeats, you're just looking for different pies, so what can you do? You can use a set:

    favoritePies = ['Apple', 'Pecan', 'Blueberry', 'Sweet Potato', 'Cherry', 'Apple', 'Apple', 'Apple', 'Apple', 'Apple', 'Blueberry', 'Fruit', 'Meringue', 'Tart']
    favoritePies = list(set(favoritePies))

    print(favoritePies)

*Output:*

>['Tart', 'Fruit', 'Cherry', 'Blueberry', 'Apple', 'Meringue', 'Pecan', 'Sweet Potato']

Depending on what you want your end datatype to be, you can either keep is as a set or return it back to being a list.
In this example, I converted the list of pies into a set, the reconverted it back into a list.

## Membership Tests

That is one reason. Another reason to use a set is because sets are great at *membership tests!*

For those that don't know, the goal of a membership test is to check whether a specific element is contained within something, such as a list, string, or even, you guessed it, a set. In comparison to lists, whose (average) time complexity for membership tests is O(n), a set has an (average) time complexity of O(1). This might seem irrelevant when used with our small list of pies form before, but for a list that is 10,000+ long, it makes the world of difference.


## Set Operations
The third and final reason for using sets is for the set operations! I.E. Math stuff. 

Do you happen to remember having to do things like union, intersection, difference and symmetric difference back in High School? It is fine if you don't, but essentially what these four operations do is allow you to compare two sets, and do some type of operation on them. For example:

If you use the **union()** you can combine two sets together

    setOne = {'cat', 'dog', 'mouse'}
    setTwo = {'mouse', 'bird', 'lizard'}
    setThree = setOne.union(setTwo)
    print(setThree)

*Output:*

>{'cat', 'bird', 'lizard', 'dog', 'mouse'}

You can use **intersection()** to find where two sets overlap

    setOne = {'cat', 'dog', 'mouse'}
    setTwo = {'mouse', 'bird', 'lizard'}
    setThree = setOne.intersection(setTwo)
    print(setThree)

*Output:*

>{'mouse'}

You can use **difference()** to find all the elements in the one set that are not in another set

    setOne = {'cat', 'dog', 'mouse'}
    setTwo = {'mouse', 'bird', 'lizard'}
    setThree = setOne.difference(setTwo)
    print(setThree)

*Output:*

>{'cat', 'dog'}

You can use **symmetric_difference()** to find all of the elements that are in one set or another, but not both

    setOne = {'cat', 'dog', 'mouse'}
    setTwo = {'mouse', 'bird', 'lizard'}
    setThree = setOne.symmetric_difference(setTwo)
    print(setThree)

*Output:*

>{'dog', 'cat', 'bird', 'lizard'}

<br>

In conclusion: 

Now of course there are not all of the use cases of sets, but these are at least the common ones that are seen and used out there!
