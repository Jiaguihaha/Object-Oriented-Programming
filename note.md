note.dt
# Object-Oriented Programming

Category: Unit 2
Created: March 22, 2023
Status: Open
Updated: April 13, 2023 9:17 PM

# Notes:

## Objects:

- In computer science :
    - a variable
    - data structure
    - function
    - method
    - a location in memory having a value that can be referenced by an identifier
- In object oriented programming:
    - instance of a class where this object can be either a
        - variable
        - function
        - data structure
        - a combination of such

## The OOP Paradigm (范例)

- Object Oriented Programming
    - Programming practice to design modular (模块化的) reusable software systems
    - OOP designs programs with creation of objects
    - Focuses on the definition of data rather then the input → processing → output logic
    - The goal is to create an object that we can define and provide functional functionality to solve problems
- Conceptual Differentiation
    - Procedure Oriented
        - A human may require:
            - Calculations
            - Logical Evaluations
            - Complete Repetitive tasks
            - Database
    - OOP
        - Creating a human object
            - What’s their name
            - What’s their address
            - What functions can this object have
    - OOP focuses on how to manipulate (操纵) the data of the object rather than the logic required to manipulate them
- In depth Analysis of an Object
    - Object: A combination of data and functional code because real world objects have states and behaviour **RECALL THAT AN OBJECT IS AN INSTANCE**
    - States: The characteristic, Measurable data of an object
    - Behaviour: The available functionality of the object (what can it do?)
    - Object’s Data → called: attributes
    - Object’s Code → called: methods
- Example Object We can Create → Dog
    - Dog may have the following **attributes**:
        - name
        - colour
        - breed
        - isHungry
        - isThirsty
    - Dog may have the following **methods**:
        - bark()
        - eat()
        - sleep()
    - If we populate the Dog’s attributes then we have an instance; therefore, an **object**
- Classes & Objects
    - **Class**: An abstract (抽象的) description of all objects that can be made from this set class where an object can be instantiated (实例化) from
    - A classes Contains **Attributes**
    - **Attributes**: An Objects’s accessible ***tools***
    - Fields: Variables that belong to an object or a class
        - Type 1: It belongs to the instance of the class
        - Type 2: It belongs to the class it self
    - Methods: Functions that the object or the object can call

## OOP in Python 3

- Keyword: class
    - class | keyword | → A built-in keyword in Python 3 that allows to create our own classes
    - Example:
    
    ```python
    #The most Basic Class
    
    class ClassName: #Notice that Class name are capitalized 
    	pass # An Empty Block
    # end of ClassName
    
    obj = ClassName()
    print(obj) 
    ```
    
    - First define the name of the class with the keyboard: classes
    - In its code block (indentation (缩进) ) define its attributes
    - Then you can assign a variable with an instantiation (实例化) of the class to interact with it
        - make sure to use parentheses (括号)  when calling the class name
- Example: the person class

```python
#Person Class 
Class Person: 
	pass # An empty block
#end of Person Class

student1 = Person() #student1 is now a Person Object 
print(student1) 
```

- Creating a Method for a Class
    - Classes can have methods. In Python 3, we just declare them like a new function (it doesn’t always need to return)
    - Example:
    
    ```python
    class Person: 
    	def greet(self): 
    		print("Hello, how are you?") 
    	#end of greet
    #end of class person
    p = Person()
    p.greet() # outputs the greet message ...
    #the method is accessed with a period (.) 
    ```
    
- The _ _ init _ _ method & self parameter
    - def _ _ init _ _ (self): → The _ _ init _ _ method (double underscores)
        - The initialization method is executed as soon as an object of the class is instantiated (实例化)
        - It helps us to do any initialization for the object’s attributes
        - **self** parameter is used to denote that the method is applied and accessible for the object itself
        - **self** will also treat its own attributes as local
    - Double underscore → These are key hidden features of Python that allow us to do some overwriting of Python features and hidden content
    - Example:
    
    ```python
    Class Person; 
    	def __init__(self, name): 
    		self.name = name 
    	#end of initialization
    
    	def greet(self): # the self parameter is always required
    		print("Hello, my name is", self.name) 
    	# end of greet
    #end of class Person
    
    p = Person("Mr. Park") 
    p.greet
    ```
    

## Example: List

- List is an Object in Python 3
    - L = [1, 2, 3, 4]
        - L is an instance of a <list class>; therefore, L is an object
    - Features;
    - L[i] → indexing … L[i : J] → Slicing
    - functions → len(), min(), max()
    - operators → + and *
    - methods → L.append(), L.count(), L.extend(), L.sort(), L.reverse()
    - NOTE: We didn’t need to know how these were coded

## Encapsulation (封装)

- What is Encapsulation ?
    - Encapsulation → Information Hiding: Restricting the access to the classes/objects’ certain attributes and methods
    - Why?
        - Data protection
        - Restricting certain methods to be callable
    - Note:
        - In Python, this isn’t really possible: hence we use a special system. → We hide attributes and methods by using a double underscore _ _ as a prefix
        
        ```python
        class Student: 
        	def __init__(self, nameF, nameL, num): 
        		self.firstName = nameF 
        		self.lastname = nameL 
        		self.__studentNumber = num
        
        	def __getStudentNumber(self): 
        		return self.__studentNumber
        
        #end of Student
        s1 = Student("Mr.", "Park", 10) 
        print(s1.__getStudentNumber()) # Will cause an error
        print(s1.__studentNumber) #Will also cause an error
        ```
        
- Importance of Encapsulation:
    
    ```python
    class Student:  
    	def __init__(self, nameF, nameL, num): 
    		self.firstName = nameF
    		self.lastName = nameL 
    		self.__studentNumber = num
    #end of Student
    
    s1 = Student("Mr.", "Park", 10) 
    print(s1.firstName) #Return/Outputs "Mr." 
    
    s1.firstName = "Ms." 
    print(s1.firstName) #Returns/Outputs "Ms." 
    
    ```
    
- Common Practice
    - Overriding allows the child class to provide specific implementation (执行) for a method that exists in the parent class

```python
class Student: 
	def __init__(self, nameF, nameL, num): 
		self.__firstName = nameF
		self.__lastName = nameL 
		self.__studentNumber = num

	def setFirstName(self, newName): 
		self.__firstName = newName

	def getFirstName(self): 
		return self.__firstName
```

## Overrides

- Overloading: Two methods in one class that have the same method name, but different parameters
- Overloading and Overriding
    - Overriding: Two methods with the same method name and parameters
        - One method is in the parent class
        - One method is in the child class
        - You can also override built-in magic-methods. OR Base-functions
    - There are NO OVERLOADING IN Python 3

## Polymorphism

- What is Polymorphism?
    - Polymorphism: A method that can be used across different classes and object that is dependent on the parameters
    - Ploy → Many
    - Morphism → Forms
    - Ideas:
        - different classes (non-inherited) can have the same named methods (Simple) → Polymorphism
        - Within a set of inherited classes have the same methods
- Example: Two Different Classes…Same Method
    
    ```python
    class Bear: 
    	def sound(self): 
    		print("Groarr") 
    
    class Dog: 
    	def sound(self): 
    		print("Woof Woof!") 
    
    def makeSound(animalType): 
    	animalType.sound()
    
    bearObj = Bear() 
    dogObj = Dog() 
    
    makeSound(bearObj) 
    makeSound(dogObj) 
    
    '''
    In Conclusion: We can give two different classes same methods;
    hence, polymorphism. 
    '''
    ```
    
- Polymorphism and Inheritance
    - Overloading → Illegal in Python 3, but it is a type of Polymorphism
    - Inherited Classes modifying Inherited Methods (Overriding) →
        - Polymorphism in Python 3
- Illegal Overloading Example:
    
    ```python
    class Person: 
    	def __init__(self, name, age): 
    		self.__name = name
    		self.__age = age
    
    	def show(self): 
    		return self.__name
    
    	def show(self, num): 
    		return "%s %d" % (self.__name, self.__age) 
    ```
    

## Base Overrides

- Override and Polymorphism with Python
    - We can have:
        - Two different classes have a same attributes and methods
        - A child of a parent have an overrided method where the child would utilize the method differently
    - These are the two fundamental concepts of overriding and polymorphism in Python
    - If we can override a built-in methods/operators that we use in Python 3 as well for our own objects
    - Some website calls them “magic methods”
- Example:
    
    ```python
    class Dog; 
    	def __init__(self, name): 
    		self.__name = name
    
    	def __str__(self): 
    		return "Woof, I'm %s." %. self.__name
    
    corgi = Dog("Tobasco") 
    print(corgi) -> "Woof, I'm Tobasco." 
    ```
    
- Why override built-in methods and operators?
    - Benefits:
        - can start to complete mathematical operations on custom Objects
        - Can start to compare equality between custom Objects
    - Therefore: You can start to manipulate how the Object behaves when met with built – in methods and operators

## _ _ repr_ _ () base function

- _ _ repr_ _ () base function
    
    ![Screenshot 2023-04-13 at 12.13.24 PM.png](Object-Oriented%20Programming%202135a9a8693a4921bd34d26a9890046a/Screenshot_2023-04-13_at_12.13.24_PM.png)
    
    - When we try to make out custom objects printable, we actually need to override _ _ repr _ _ and _ _ str _ _
    - _ _ repr _ _ → Allows us to prevent a printable version of our object
    - _ _ str _ _ → Allows us to convert our object to a string

## Inheritance

- What is Inheritance?
    - Inheritance: When an object or class is based on another class; where its features are from a parent class
    - Types:
        - Single Inheritance: A subclass inheriting the features of a single superclass / parent class
        - Multiple Inheritance: A subclass inheriting the features of a multiple parent classes
        - Multilevel Inheritance: A subclass is inheriting from another subclass… A→ B → C
    - Inheritance can have an hierarchy (branching like a tree) and/or be a hybrid: mixing the types of inheritances
- What can we do with Inheritance?
    - A child will receive all attributed and methods of the parent
    - A child can then enhance itself with new attributes and new methods
    - A child can OVERRIDE attributed and methods for their own liking/specialty
- Notes
    - If a child class inherits the parent class:
        - The child does not need a new _ _ init _ _ () method UNLESS it requires new attributes
        - The child does not need to reinstate the parent’s methods UNLESS you override them
- Single Inheritance in Python 3
    
    ```python
    class ParentClassName: 
    '''Define Parent Class'''
    .
    .
    .
    
    class InheritanceClass(ParentClassName): 
    	'''Define Inherited Class''' 
    	
    	def __init__(self, param, param2): 
    		ParentClassName.__init__(self, param) 
    		self.param2 = param
    ```
    
- Example
    - Parent class
        
        ```python
        class Person: 
        	def __init__(self, name): 
        		self.__name = name
        
        	def getName(self):
        		return self.__name
        ```
        
    - Inherited Class
        
        ```python
        class Student(Person): 
        	def __init__(self, name, num): 
        		Person.__init__(self, name) 
        		self.__sNum = num
        
        	def getStudentName(self): 
        		return("%s: %s" % (self.__sNum, self.getName()))
        ```
        
    - Execution
        
        ```python
        p = Perrson("Mr. Park") 
        s = Student("Random Child", "1234") 
        print(p.getName()) # Output: "Mr. Park" 
        print(s.getStudentName(), "and" , s.getName()) # Output: "1234: Random Child and Random Child" 
        ```
        
- What is super()?
    - Super() → is a built - in method for classes to refer their parent class
        - This prevent us from doing ParentClass.method(self)
        - The self with self gets confusing
- Example w/ super()
    - Parent Class
        
        ```python
        class Person: 
        	def __init__(self, name): 
        		self.__name = name
        	
        	def getName(self): 
        		return self.__name
        ```
        
    - Inherited Class
        
        ```python
        class Student(Person): 
        	def __init__(self, name, num): 
        		super().__init__(name) 
        		self.__sNum = num
        
        	def getStudentName(self): 
        		return("%s: %s" % (self.__sNum, self.getName()))
        ```
        
    - Execution
        
        ```python
        p = Person("Mr. park") 
        s = Student("Random Child", "1234") 
        print(p.getname()) 
        print(s.getStudentName(), "and" , s.getName()) 
        ```
        

## Inheritance Extended

- Types of Multiple Inheritances
    - Multi - Generational
        - Grandparent → Parent → Child
    - Multi - Parent (Not limited to two)
        - Parent A
        - +
        - Parent B
        - =
        - Child
    - Mixture of 1 and 2

## Polymorphism

- What is Polymorphism?
    - Polymorphism: A method that can be used across different classes and object that is dependent on the parameters.
    - poly → Many
    - Morphism → Forms
    - Ideas:
        - Different Classes (non-inherited) can have the same names methods (Simple) → Polymorphism
        - Within a set of inherited classes have the same methods
- Polymorphism and Inheritance
    - Overloading → Illegal in Python 3, but it is a type of Polymorphism
    - Inherited Classes modifying Inherited Methods (Overriding) →
        - Polymorphism in Python 3
- Polymorphism in Inherited Classes
    
    ```python
    class Parent: 
    	def method(self): 
    		pass
    
    class Child(Parent): 
    	def method(self): 
    		#something different
    		#Polymorphed to somehing else...
    		#same method name
    		pass
    ```

  class Point: 
  def __init__(self,x,y): 
    self.x = x
    self.y = y
  def __str__(self):
    return f"Point Object ({self.x}, {self.y})" 
    
  def __repr__(self): 
    return self.__str__() 
    
  def distance(self, other_point):
    diff_x = (self.x - other_point.x)**2
    diff_y = (self.y - other_point.y)**2
    result = (diff_x + diff_y)**0.5
    return result
    
  def __mul__(slef,num): 
    return Point(self.x * num, self.y * num) 
  
 
 test1 = Point(2,6)
 test2 = Point(-1,5)
 origin = Point(0,0)

