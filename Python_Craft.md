# Python

```python
# Built in functions
str() # takes a integer and returns a string object

# defining a custom function
def square():
  new_value = 4 ** 2
  print(new_value)

# adding parameters
def square(value):
  new_value = value ** 2
  print(new_value)

# returning the function value
def square(value):
  new_value = value ** 2
  return new_value

# docstrings
def square(value):
  """Returns the square of the value"""
  new_value = value ** 2
  return new_value

# use tuples to pass multiple parameters along with return multiple values
```

```python
# Status Codes
200 - Success OK
201 - Created
202 - Accepted
204 - No Content
400 - Bad Request (Client Error)
404 - Not Found
500 - Internal Server Error

from FastApi import HTTPException

raise HTTPException(status_code=404, details="Item not found")

from FastApi.testClient import TestClient
from .main import app

client = TestClient(app)


# successful workflows
- create then read
- create then update
- create the delete

- read without create
- update without create
```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Python.md&fileType=undefined&fileExtension=md