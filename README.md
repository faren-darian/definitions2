# Placeholder


Placeholder in Python is like a temporary spot or marker in your code where you plan to put some specific information later. It's a way to say "I'll fill in this part with actual data when I need to."

In other words, Placeholders are part of a broader concept called string formatting. They allow for dynamic string creation and manipulation.

-   What does a placeholder look like? In Python, placeholders are often written with curly braces {} inside a string.
    
-   When do we use placeholders? We use them when we want to create a string that will have some parts filled in later with specific values.
    
```bash
name = "Bob"
age = 30
message = f"My name is {name} and I am {age} years old."
print(message)
```
# Objects


An object is like a container that holds data and functions related to that data. Almost everything in Python is an object. Example:
```bash
my_car = "Toyota"  # my_car is a string object
my_numbers = [1, 2, 3]  # my_numbers is a list object
```
# Arguments


Arguments are pieces of information that you pass into a function when you call it. They're like inputs for the function to work with. Example:
```bash
def greet(name, time_of_day):
    print(f"Good {time_of_day}, {name}!")

greet("Alice", "morning")  # Outputs: Good morning, Alice!
```

# Parameteres


-   Parameters are variables listed in the definition of a function or method.
    
-   They will receive arguments when a new object is created.
    
-   They act as placeholders for the values that will be passed into the function when it's called.
    
-   Parameters have a scope limited to the function they're defined in.
    

# Attributes


-   Attributes are pieces of information attached to an object. They're like characteristics or properties of the object.
    
-   Attributes are variables that belong to an object.
    
-   They store data that is associated with that object.
    
-   Attributes have a lifespan as long as the object exists and can be accessed from various methods within the class.
    

## Key differences between parameteres and attributes


### 1. Lifespan:


-   Parameters exist only during the execution of the method.
-   Attributes persist as long as the object exists.

### 2. Scope:


-   Parameters are local to the method they're defined in.
-   Attributes can be accessed by any method in the class (and sometimes from outside the class).

### 3. Purpose:


-   Parameters are used to pass data into methods.
-   Attributes are used to store data that belongs to an object.

### 4. Assignment:


-   Parameters get their values when a method is called.
-   Attributes are typically assigned values within methods (often in  `__init__`), but can be modified later.

### 5. Syntax:


-   Parameters are listed in method definitions:  `def method(parameter1, parameter2)`:
-   Attributes are usually prefixed with  `self.`  inside class methods:  `self.attribute = value`
```bash
class Car:
    def __init__(self, make, model, year):
        self.make = make    # attribute
        self.model = model  # attribute
        self.year = year    # attribute
        self.mileage = 0    # attribute (not from a parameter)
        self.running = False  # attribute (not from a parameter)

    def start_engine(self):
        self.running = True
        print(f"The {self.year} {self.make} {self.model}'s engine is now running.")

    def drive(self, distance):
        if self.running:
            self.mileage += distance
            print(f"Drove {distance} miles. Total mileage is now {self.mileage}.")
        else:
            print("You need to start the engine first!")

The ```__init__``` method:

- This is a special method in Python classes, called a constructor.
- It initializes a new object of the class.
- The ```self``` parameter refers to the instance being created.

# Creating an instance (object) of the Car class
my_car = Car("Toyota", "Corolla", 2020)

# Using the object
my_car.start_engine()
my_car.drive(50)
```
Let's break this down:

### 1. Object:


An object is an instance of a class. In this example,  `my_car`  is an object of the  `Car`  class. Objects have their own set of attributes and can perform actions defined by their methods.

### 2. Parameters:


Parameters are variables in a method definition that act as placeholders for values passed when the method is called. In  `__init__(self, make, model, year)`,  `make`,  `model`, and  `year`  are parameters. In  `drive(self, distance)`, distance is a parameter.

### 3. Attributes:


Attributes are variables that belong to an object and store its state. In this example,  `self.make`,  `self.model`,  `self.year`,  `self.mileage`, and  `self.running`  are all attributes. Note that  `mileage`  and  `running`  are attributes that weren't created from parameters.

### 4. Instance:


An instance is a specific realization of a class. It's synonymous with "object" in this context.  `my_car`  is an instance of the  `Car`  class.

### 5. Arguments:


-   Arguments are the actual values passed to a method when it's called.
-   In  `Car("Toyota", "Corolla", 2020)`, "Toyota", "Corolla", and 2020 are arguments.
-   In  `my_car.drive(50)`, 50 is an argument.

Now, to address your question about why we don't define all attributes as parameters:

1.  Default or Calculated Values:

Some attributes might have default values or be calculated based on other attributes. For example,  `mileage`  starts at 0 for all new cars.

2.  Internal State:

Attributes like  `running`  represent the internal state of the object that doesn't need to be set during initialization.

3.  Flexibility:

Not all attributes need to be set when an object is created. Some might be set or changed later.

4.  Simplicity:

Having too many parameters can make object creation cumbersome. It's often better to have a few essential parameters and set other attributes as needed.

5.  Encapsulation:

Some attributes might be intended for internal use only, and not exposing them as parameters helps maintain encapsulation.

In our  `Car`  class,  `make`,  `model`, and year are essential for creating a car, so they're parameters. But  `mileage`  (which starts at 0) and running (which starts as False) don't need to be set during initialization, so they're not parameters.
