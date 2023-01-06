---
Title: 'Testing your code before launch!'

Subjects:

  - 'Python'
  - 'Computer Science'
  - 'Software Testing'

---

## What is Software Testing even?
Testing Python code typically falls under the umbrella of Software Testing. Cool stuff! Software testing is the process of evaluating a software system or its components with the intent of finding defects and ensuring that the system meets the specified requirements. There are several different approaches to testing software, including manual testing, automated testing, and unit testing. Python code testing is often performed using automated testing tools, such as unit testing frameworks like PyTest or Nose, which allow developers to write test cases and automatically run them to check for correctness. Other tools, such as pytest-bdd and behave, allow developers to write tests in a natural language style, making them easier to read and understand.

In other words, testing your software ensures there are no bugs before your users interact with it!

As you can see there a couple different types of tests.

However, today we will chat more about unit testing 😊


## Brief Overview of Python Unit Testing
In Python when we are writing unit tests, the [unittest](https://docs.python.org/3/library/unittest.html). module is used. 

The difference between unit testing and other types of testing, is that a unit test is a test that checks a small component in your application, like a specific function or a class. Unit tests are typically designed to test these units of code in isolation, to ensure that they are correct and work as expected. Woah neat!!!


#### Here is a simple example of a test case using the `unittest` module: 

```py

import unittest

def add(x, y):
    return x + y

class TestAdd(unittest.TestCase):
    def test_add_two_positive_numbers(self):
        result = add(10, 15)
        self.assertEqual(result, 25)

```

In this example, we have a function `add` that takes two numbers and returns their sum. The `TestAdd` class is a test case that contains a single test method, `test_add_two_positive_numbers`. This method calls the `add` function with the numbers 10 and 15, and then uses the `assertEqual` method to check that the result is equal to 25.

#### To run this test, you can use the `unittest` module's `main` function:

```py

if __name__ == '__main__':
    unittest.main()
    
```

## The Pytest Library
If you thought that was cool, wait until you hear about the [Pytest Library](https://pypi.org/project/pytest/)!

The Pytest Library is considered a unit testing library in Python. It is a powerful and flexible library that is widely used for testing all types of Python code, including our friend, the unit tests. Why Pytest is so popular is that it makes it easy to write and run unit tests in Python, by providing a simple and intuitive API and a rich set of features that make it easy to write, organize, and run tests. It is widely used among the coolest of developers and used for a variety of contexts, including testing web applications, scientific code, and much much more.

So you might be asking, this is really neat but how the heck do I use it? Well look no further...


#### To install pytest, you can use our good friend pip, the package manager for Python:

```py

pip install pytest

```

#### Then you got to import that bad boy into your code:

```py

import pytest

```

Now you're ready to rock and roll!

Pytest has so many cool features that we now have access to.

### Here are a few examples of how to use Pytest:

1. Writing test functions: To write a test using Pytest, you can define a function that starts with `test_`. For example:

```py

def test_example():
    # code to test goes here
    assert foo() == 4

```

2. Testing for exceptions: You can use Pytest's `raises` function to test that a block of code raises a specific exception. For example:

```py

def test_zero_division():
    with pytest.raises(ZeroDivisionError):
        1 / 0

```

3. Testing for warnings: You can use Pytest's `warns` function to test that a block of code raises a warning. For example:

```py

def test_deprecation_warning():
    with pytest.warns(DeprecationWarning):
        some_deprecated_function()

```

4. Parameterizing tests: You can use Pytest's `parametrize` decorator to run the same test function with multiple different input values. For example:

```py

@pytest.mark.parametrize("x, y, expected", [(1, 2, 3), (2, 3, 5), (3, 4, 7)])
def test_addition(x, y, expected):
    assert x + y == expected

```

These are just a few examples of how to use Pytest. It has many more features and capabilities that can help you write effective tests for your Python code. Too too neat guys!!!


## Conclusion
Testing your code is crazy important for several cool reasons! 

- It helps you catch bugs early on in the development process saving loads of time and effort.
- It ensures that your code is correct and behaves as intended
- It helps you identify those nasty edge cases that you may not have thought of, improving the robustness of your code
- It makes it easier to refactor your code and makes changes, because you are confident changes you make won't break anything
- It also makes it way easier for other cool coders to use and contribute to your code, because they know its reliable

These are just a few of the many many cool reasons testing code is cool and makes you even more of a badass developer. So get out there, write some gnarly code but don't forget to get it tested early and often kids!!! 














