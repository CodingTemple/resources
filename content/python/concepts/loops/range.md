---
Title: 'range()'
Description: 'When to loop using range.'
Subjects:
  - 'Python'
  - 'Computer Science'
Tags:
  - 'loops'
  - 'range'
CatalogContent:
  - 'introduction-to-python'
  - 'paths/back-end-engineer-career-path'
---

## When do we need to loop through the list using range:

We can always loop through a list using the range loop. We can access every element using its index. There are times where we will be required to use the indecies, if we need to know the position of the elements. In that case we should use a range or enumerate loop.

Loops Through Every Index Using a Range of Numbers.

## Syntax

```py
ex_list = [1,2,3]
for num in range(len(ex_list)):
    pass
```

## Example 1

Print every number in a list if the element is equal to the index:

```py
practice_list=[0,8,5,3,4,9,10]
# passing one arguemnt into range defaults starting number to 0
# ending number is non inclusive, so not included
for i in range(len(practice_list)):
    if practice_list[i] == i:
        print(practice_list[i])
# output:
- 0
- 3
- 4
```
## Example 2

Print every number in a list if the next number to the right is 0:

```py
num_list=[1,0,3,3,4,0,5,0]
# passing the number returned from the len() of a list into range() 
# returns every index included in the list
for i in range(len(num_list)):
# we will check the next element in the list we have to break before getting to the last element
    if i == len(num_list)-1:
        break
    if num_list[i+1] == 0:
        print(i)
#  Output: 
# 1
# 4
# 5
```