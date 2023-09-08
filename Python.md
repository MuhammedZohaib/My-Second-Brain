```python
print(7 + 5)
print(5 * 5)
print(10 - 10)
print(5 / 2)
```

### Variables:

```python
# Specific, case-sensitive name
# any specific name is a variable
height = 10
weight = 20
bmi = weight / height ** 2
fname = 'Muhammad'
lname = "Zohaib"


# check the type of any value simply by the type function
type(bmi)
type(lname) # str

# type conversions
float(value)
str(value)
int(value)
```

### Lists

```python
# area variables (in square meters)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# house information as list of lists
house = [["hallway", hall],
         ["kitchen", kit],
         ["living room", liv],
         ["bedroom",bed],
         ["bathroom",bath],
         ]
# Print out house
print(house)
# Print out the type of house
print(type(house))

house[2]
# we can also use negative index to access the elements from the end of the list

# list slicing
new_house = house[0:3] #[inclusive:exclusive]
new_house = house[:3]
new_house = house[5:]

# manipulation
house[0][1] = 12.25 
del(house[2])
house_ext = house + [[garage,10]]
```

### Functions

```python
# built-in functions
max()
len()
type()
float()
str()
int()
round()
sorted()

# list methods
list.index()
list.count()
```

```python 
import numpy
import numpy as np
from numpy import array
```
