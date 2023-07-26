---
title: "Collections in python"
date: 2023-07-24T08:52:42+05:30
draft: true
---

# Collections in python

In addition to the four data structures , python also provides additional specialized data structures. These Specialized Data Structures are stored in **Collections** module.

Data Structures present in the collections module are :

1. namedtuple()

2. deque

3. ChainMap

4. Counter

5. OrderedDict

6. defaultdict

7. UserDict

8. UserList

9. UserString

### 1. namedtuple()

Namedtuple enables us to assign a name to each of its fields. This allows us to access the elements either by index or by name. This impoves code readability.

```python
# importing namedtuple from collections
from collections import namedtuple

# var = namedtuple("tuple_name","field_list")
vehicle = namedtuple("vechicle",["name","color","year"])

car = vehicle("BMW X3","red","2023")
bike = vehicle("TVS raider","black","2022")


print(car)  # vechicle(name='BMW X3', color='red', year='2023')

# Accessing car element using its corrosponding name
print(car.name) # BMW X3

# Accessing car elements using index
print(car[0]) # BMW X3

print(bike) # vechicle(name='TVS raider', color='black', year='2022')
print(bike.color) # black
print(bike.year) # 2022
```

### 2. Deque

Deque(Double -ended quque) allows us to add and remove elements from either side of the queue. It is better to use deque then list when we need to perform pop and append operations on both the sides of the container. Deque has *O(1)*  time complexity for both append and pop operations while list has *O(n)* time complexity.

```python
from collections import deque

fruits = deque() 
# adds elements to the right side 
fruits.append("apple") 
fruits.append("banana")
fruits.append("grape")

print(fruits) # deque(['apple', 'banana', 'grape'])

# adding elements to the left side 
fruits.appendleft("pineapple")
fruits.appendleft("watermelon")


print(fruits) # deque(['watermelon', 'pineapple', 'apple', 'banana', 'grape'])


# popping from right side 
v = fruits.pop()
print(v) # grape

# popping from the left side 
v = fruits.popleft()
print(v) # watermelon

# we can also extend left and extend right
# extend the right side of the queue.
fruits.extend(["mango","peach","avacado"])

print(fruits) # deque(['pineapple', 'apple', 'banana', 'mango', 'peach', 'avacado'])


# exntenx the left side of the queue
fruits.extendleft(["blueberry","pear","raspberry"])

print(fruits) # deque(['raspberry', 'pear', 'blueberry', 'pineapple', 'apple', 'banana', 'mango', 'peach', 'avacado'])
```

### 3. ChainMap

Chainmap  combines multiple dictionaries or mappings into a single ,updatable view. The underlying mappings are stored in a list. A ChainMap incorporates the underlying mappings by rederence. So, if one of the underlying mappings get updated, those changes are reflected in ChainMap.

```python
from collections import ChainMap

x = {"a":15 , "b":20}
y = {"c":11} , "d":13}


abc = ChainMap(x,y)
```

![](/collections_chainmap_viz.png)







