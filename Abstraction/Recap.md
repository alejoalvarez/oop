## Abstraction in Java

![alt_text](https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/abstraction.jpg)

It is the process of hiding internal implementation details from the user and providing only necessary functionality to the users. It removes all non-essential things and shows only important things to users.

Data Abstraction may also be defined as the process of identifying only the required characteristics of an object ignoring the irrelevant details.The properties and behaviors of an object differentiate it from other objects of similar type and also help in classifying/grouping the objects.

In other words, Abstraction in Java is a technique by which we can hide the data that is not required to a user

Example<br>
We all use an ATM machine for cash withdrawal, money transfer, retrieve min-statement, etc in our daily life. But we don't know internally what things are happening inside ATM machine when you insert ATM card for performing any kind of operations.

## Abstraction in java

There are two ways to achieve abstraction in java. They are as follows:<br>
  **1**. Abstract class (0 to 100%)<br>
  **2**. Interface (100%)

### Advantages

  **1**. It reduces the complexity of viewing the things.<br>
  **2**. Avoids code duplication and increases reusability.<br>
  **3**. Helps to increase security of an application or program as only important details are provided to the user.<br>
  **4**. Programmer can implement abstract method to perform different tasks depending on the need. 

### Abstract Class in Java
An abstract class is a class, which is declared with `abstract` keyword. It is just like a normal class but has two differences.<br> 
 **1**. We cannot create an object of this class. Only objects of its non-abstract (or concrete) sub-classes can be created.
 
 **2**. It can have zero or more abstract methods which are not allowed in a non-abstract class (concrete class).

 :bulb: **Key points:** <br>
  **1**. Abstract is a non-access modifier in java which is applicable for classes, interfaces, methods, and inner classes. It represents an incomplete class which depends on subclasses for its implementation. Creating subclass is compulsory for abstract class.<br>
  **2**. A non-abstract class is sometimes called a concrete class.<br>
  **3**. An abstract concept is not applicable to variables.

### Abstract Method in Java
A method which is declared with abstract modifier and has no implementation (means no body) is called an abstract method in java. It does not contain any body. It has simply a signature declaration followed by a semicolon. It has the following general form as given below.

Syntax: <br>
    abstract type MethodName(arguments); // No body <br>
For example: <br>
    abstract void msg(); // No body. <br>
Since the abstract method does not contain any body. Therefore, it is also known as an incomplete method in java. <br>
A non-abstract class cannot have an abstract method whether it is inherited or declared. In Java.

 :bulb: **Key points:** <br>
  **1**. Abstract method cannot be static.<br>
  **2**. It cannot be private because the abstract method must be implemented in the subclass. If we declare it as private, we cannot implement it from outside the class.<br>
  **3**. A concrete method is a method which has always the body. It is also called a complete method in java.
  
