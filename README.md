# inheritance-in-Python
Sure, here's a practice question for inheritance in Python along with a solution and explanation:

Practice Question:

Consider the following scenario:

You are building a program to model different types of vehicles. You have a `Vehicle` class that represents the basic attributes and behaviors of any vehicle. You also have specific classes for `Car` and `Motorcycle`, which inherit from the `Vehicle` class.

Define the `Vehicle` class with the following attributes and methods:
- Attributes:
  - `make` (string): representing the make of the vehicle (e.g., "Toyota", "Honda", etc.)
  - `model` (string): representing the model of the vehicle (e.g., "Camry", "Accord", etc.)
  - `year` (integer): representing the manufacturing year of the vehicle (e.g., 2010, 2020, etc.)
- Methods:
  - `__init__(self, make, model, year)`: constructor to initialize the attributes.
  - `display_info(self)`: method to display the information of the vehicle (make, model, year).

Define the `Car` class and `Motorcycle` class, both inheriting from the `Vehicle` class. Each subclass should have an additional attribute `num_doors` for `Car` and `num_wheels` for `Motorcycle`, along with their own `__init__` methods to initialize these attributes.

Now, create an instance of each class and demonstrate inheritance by calling the `display_info` method for each instance.

Solution:

```python
class Vehicle:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
    
    def display_info(self):
        print(f"Make: {self.make}, Model: {self.model}, Year: {self.year}")

class Car(Vehicle):
    def __init__(self, make, model, year, num_doors):
        super().__init__(make, model, year)
        self.num_doors = num_doors

class Motorcycle(Vehicle):
    def __init__(self, make, model, year, num_wheels):
        super().__init__(make, model, year)
        self.num_wheels = num_wheels

# Create instances
car1 = Car("Toyota", "Camry", 2015, 4)
motorcycle1 = Motorcycle("Harley-Davidson", "Sportster", 2020, 2)

# Demonstrate inheritance
car1.display_info()
motorcycle1.display_info()
```

Explanation:

- The `Vehicle` class is defined with attributes `make`, `model`, and `year`, along with a method `display_info` to print out the information of the vehicle.
- The `Car` class and `Motorcycle` class inherit from the `Vehicle` class using the syntax `class Car(Vehicle)` and `class Motorcycle(Vehicle)`, respectively.
- Each subclass has its own `__init__` method to initialize additional attributes (`num_doors` for `Car` and `num_wheels` for `Motorcycle`), and they call the superclass's `__init__` method using `super().__init__(...)` to initialize inherited attributes.
- Instances of `Car` and `Motorcycle` are created (`car1` and `motorcycle1`), and the `display_info` method inherited from the `Vehicle` class is called for each instance to demonstrate inheritance.
