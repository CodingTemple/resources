---
Title: 'If Statement'
Description: 'Control structures allow us to evaluate the code and informs the code to choose one course of action or another based on a condition.'
Subjects:
  - 'Web Development'
  - 'Computer Science'
Tags:
  - 'Control Flow'
  - 'Structures'
CatalogContent:
  - 'introduction-to-python'
---

**Control Structures**  allow us to evaluate the code and informs the code to choose one course of action or another based on a condition. 


### `If` Statement
In Python, the `if` statement allows for a conditional expression to execute a statement or a group of statement based on the value of the expression.

```py
if <expression>:
    <statement>
```
If `<expression>` evaluates to `True`, then `<statement>` is executed. If `False`, then `<statement>` will be skipped over.

```py
>>> x = 10
>>> y = 5

>>> if x > y: # Evaluates to True
...    print('yes')
...
yes # 'yes' is printed

>>> if x < y: # Evaluates to False
...     print('yes')
...
# Nothing is printed because expression was False
```

### Indentation
In Python, indentation has special significance. Indentation is used to define a block. Statements that are at the same indentation are considered to be in the same code block.

```py
if <expression>:
    <statement>
    <statement>
<final statement>
```
In the above example, the two statements at the same indentation level (lines 2-3) are considered the same block. If `<expression>` is `True`, both `<statement>` will be executed. However, if the `<expression>` is `False`, both lines will be skipped. In both scenarios, `<final statement>` is executed.

Consider the following:
```py
x = 10
y = 5

if x > y:   # Evaluates to True
    print('x is greater than y')
    print('y is less than x')
    print('x is not equal to y')
print('x and y are integers')
```
After execution, we would see the following output:
```
x is greater than y
y is less than x
x is not equal to y
x and y are integers
```
Because the expression `x > y` evaluates to `True`, the three print statements indented below the `if <expression>` are executed.

Now consider the following code:
```py
x = 10
y = 5

if x < y:   # Evaluates to False
    print('x is greater than y')
    print('y is less than x')
    print('x is not equal to y')
print('x and y are integers')
```
After execution, we would see the following output:
```
x and y are integers
```
Because the expression evaluates to `False`, the code skips over all of the lines that are indented and continues to the print statement that matches the initial `if` statement.