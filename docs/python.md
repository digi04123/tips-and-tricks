# Python

## Enum

* Use `IntEnum` if you need to compare the value of the Enum
* Add `@unique` if the value is unique

## Dict

* Use `defaultdict` for default value during initialization
* Use `namedtuple` for having a tuple-like object, without defining a class. i.e.

````py
from collections import namedtuple

Student = namedtuple("Student", field_names=["name", "age", "scores"])

# Create an instance of the one-line namedtuple class.
student = Student(name="John", age=15, scores=["A", "B", "B", "C", "C", "C"])

# The type is a class.
type(student)
# __main__.Student

# We can access values by indexes like a tuple.
student[0]  # John

# Convert namedtuple to dict using _asdict method
student._asdict()
````

* Use pydantic whenever possible