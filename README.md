# OOP - Object Oriented Programming

Is a programming paradigm in which programs are organized around data, or based on the concept "objects", rather than functions and logic.

Basically an object can be defined as a data (attributes or properties) and behaviors (methods)

Simply put, OOP focuses on the objects that developers want to manipulate rather than the logic required to manipulate them. This approach to programming is well-suited for programs that are large, complex and actively updated or maintained. Due to the organization of an object-oriented program, this method is also conducive to collaborative development where projects can be divided into groups. Additional benefits of OOP include code reusability, scalability  and efficiency.

OOP was developed to increase the reusability and maintainability of source code. Transparent representation of the control flow had no priority and was meant to be handled by a compiler. With the increasing relevance of parallel hardware and multithreaded coding, developing transparent control flow becomes more important, something hard to achieve with OOP

## Principles of OOP
<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/Pillar-OOP.jpg">
</p>

**Object Oriented Programming is based on the following principles**:

```Encapsulation```
The implementation and state of each object are privately held inside a defined boundary, or class.

Other objects do not have access to this class or the authority to make changes but are only able to call a list of public functions, or methods. This characteristic of data hiding provides greater program security and avoids unintended data corruption.

The meaning of **Encapsulation**, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:

  - declare class variables/attributes as ```private```
  - provide public get and set methods to access and update the value of a ```private``` variable
  
  **Get and Set**
  
  You learned from the previous chapter that ```private``` variables can only be accessed within the same class (an outside class has no access to it). However, it is possible to access them if we provide public **get** and **set** methods.

  The ```get``` method returns the variable value, and the ```set``` method sets the value.

  Syntax for both is that they start with either ```get``` or ```set```, followed by the name of the variable, with the first letter in upper case:
  
  Example 
  
  ```java
  public class Person {
    private String name; // private = restricted access

    // Getter
    public String getName() {
      return name; // return the value of the variable name
    }

    // Setter
    public void setName(String newName) {
      this.name = newName; // The set method takes a parameter (newName) and assigns it to the name variable
    }
  }
  
  ```
  **Why Encapsulation?**
 
  - Better control of class attributes and methods
  - Class attributes can be made read-only (if you only use the get method), or write-only (if you only use the set method)
  - Flexible: the programmer can change one part of the code without affecting other parts
  - Increased security of data

  [See more about Encapsulation](https://github.com/Alejo-Alvarezv/OOP/blob/master/Encapsulation)
 
```Abstraction```
Objects only reveal internal mechanisms that are relevant for the use of other objects, hiding any unnecessary implementation code. This concept helps developers make changes and additions over time more easily.

  [See more about Abstraction](https://github.com/Alejo-Alvarezv/OOP/blob/master/Abstraction)

```Inheritance```
Subclass and superclass

Relationships and subclasses between objects can be assigned, allowing developers to reuse a common logic while still maintaining a unique hierarchy. This property of OOP forces a more thorough data analysis, reduces development time and ensures a higher level of accuracy.

Is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:

  - **subclass** (child) - the class that inherits from another class
  - **superclass** (parent) - the class being inherited from

To inherit from a class, use the ```extends``` keyword.

Example

```java
class Vehicle {
  protected String brand = "Audi";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    System.out.println("Tuut, tuut!");
  }
}

class Car extends Vehicle {
  private String modelName = "Mercedez";    // Car attribute
  public static void main(String[] args) {

    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (from the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
    System.out.println(myCar.brand + " " + myCar.modelName);
  }
}
```
**Why And When To Use "Inheritance"?**

- It is useful for code reusability: reuse attributes and methods of an existing class when you create a new class.

  [See more about Inheritance](https://github.com/Alejo-Alvarezv/OOP/tree/master/Inheritance)

```Polymorphism```
Objects are allowed to take on more than one form depending on the context. The program will determine which 
meaning or usage is necessary for each execution of that object, cutting down on the need to duplicate code.

  Refers to the ability of OOPs programming languages to differentiate between entities with the same name efficiently.

  [See more about Polymorphism](https://github.com/Alejo-Alvarezv/OOP/blob/master/Polymorphism)


## Objects and classes
Exist two main concepts in OOP: Classes and objects.

**Classes**: <br>
Is a template that allow to create object, containt the definition of attributes and the procedure for the class

  A class is a user defined blueprint or prototype from which objects are created. It represents the set of properties or methods that are common to all objects of one type. In general, class declarations can include these components, in order:
  - **Modifiers**: A class can be public or has default access (Refer this for details).
  - **Class name**: The name should begin with a initial letter (capitalized by convention).
  - **Superclass(if any)**: The name of the class’s parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
  - **Interfaces(if any)**: A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
  - **Body**: The class body surrounded by braces, { }.
  
**Objects**: <br>
Instances of clases

  It is a basic unit of Object Oriented Programming and represents the real life entities. A typical Java program creates many objects, which as you know, interact by invoking methods. An object consists of:<br>
  - **State** : It is represented by attributes of an object. It also reflects the properties of an object.
  - **Behavior** : It is represented by methods of an object. It also reflects the response of an object with other objects.
  - **Identity** : It gives a unique name to an object and enables one object to interact with other objects.

**Method**: <br>
  A method is a collection of statements that perform some specific task and return result to the caller. A method can perform some specific task without returning anything. Methods allow us to reuse the code without retyping the code. In Java, every method must be part of some class which is different from languages like C, C++ and Python.
Methods are time savers and help us to reuse the code without retyping the code.

  Method Declaration: In general, method declarations has six components:

  - **Access Modifier**: Defines access type of the method i.e. from where it can be accessed in your application. In Java, there 4 type of the access specifiers.<br>
    - **public**: accessible in all class in your application.<br>
    - **protected**: accessible within the package in which it is defined and in its subclass(es)(including subclasses declared outside the package)<br>
    - **private**: accessible only within the class in which it is defined.<br>
    - **default** (declared/defined without using any modifier): accessible within same class and package within which its class is defined.<br>
  - **The return type**: The data type of the value returned by the method or void if does not return a value.
  - **Method Name**: the rules for field names apply to method names as well, but the convention is a little different.
  - **Parameter list**: Comma separated list of the input parameters are defined, preceded with their data type, within the enclosed parenthesis. If there are no parameters, you must use empty parentheses ().
  - **Exception list**: The exceptions you expect by the method can throw, you can specify these exception(s).
  - **Method body**: it is enclosed between braces. The code you need to be executed to perform your intended operations.

## SOLID
<p align="center">
<img src="https://github.com/Alejo-Alvarezv/SOLID">
</p>

![alt text](https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/SOLID.jpg "SOLID")

Five design principles intended to make software designs more understandable, flexible and maintainable.

- **Single responsibility principle**
A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.

- **Open/closed principle**
"Software entities ... should be open for extension, but closed for modification."

- **Liskov substitution principle**
"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program".

- **Interface segregation principle**
"Many client-specific interfaces are better than one general-purpose interface."

- **Dependency inversion principle**
One should "depend upon abstractions, [not] concretions".

## Design patterns
[View complete definition](https://github.com/Alejo-Alvarezv/DesingPatterns)

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/DesignPatterns.png">
</p>

Is a general repeatable solution to a commonly occurring problem in software design. A design pattern isn't a finished design that can be transformed directly into code. It is a description or template for how to solve a problem that can be used in many different situations.
