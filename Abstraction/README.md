# Abstraction 

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

 :bulb: Key points: <br>
  **1**. Abstract is a non-access modifier in java which is applicable for classes, interfaces, methods, and inner classes. It represents an incomplete class which depends on subclasses for its implementation. Creating subclass is compulsory for abstract class.<br>
  **2**. A non-abstract class is sometimes called a concrete class.<br>
  **3**. An abstract concept is not applicable to variables.

```An abstract class can have a data member, abstract method, method body (non-abstract method), constructor, and even main() method.```


### Abstract Method in Java
A method which is declared with abstract modifier and has no implementation (means no body) is called an abstract method in java. It does not contain any body. It has simply a signature declaration followed by a semicolon. It has the following general form as given below.

Syntax: <br>
    abstract type MethodName(arguments); // No body <br>
For example: <br>
    abstract void msg(); // No body. <br>
Since the abstract method does not contain any body. Therefore, it is also known as an incomplete method in java. <br>
A non-abstract class cannot have an abstract method whether it is inherited or declared. In Java.

 :bulb: Key points: <br>
  **1**. Abstract method cannot be static.<br>
  **2**. It cannot be private because the abstract method must be implemented in the subclass. If we declare it as private, we cannot implement it from outside the class.<br>
  **3**. A concrete method is a method which has always the body. It is also called a complete method in java.
  

Example Abstract class
```java
abstract class Car{  
  abstract void run();  
}  

class Honda extends Car{  
  void run(){
    System.out.println("running safely");
  }  

  public static void main(String args[]){  
    Bike obj = new Honda4();  
    obj.run();  
  }  
} 
```

Another example

```java
//Example of an abstract class that has abstract and non-abstract methods  
abstract class Car{  
  Bike(){System.out.println("car is created");}  
  abstract void run();  
  void changeGear(){
    System.out.println("gear changed");
  }  
}  
//Creating a Child class which inherits Abstract class  
class Honda extends Car{  
  void run(){
    System.out.println("running safely");
}  
}  
//Creating a Test class which calls abstract and non-abstract methods  
class TestAbstraction2{  
  public static void main(String args[]){  
    Bike obj = new Honda();  
    obj.run();  
    obj.changeGear();  
  }  
} 

//RESULT
bike is created
running safely
gear changed
```

## Interface

Another way to achieve abstraction in Java, is with interfaces.

The interface in Java is a mechanism to achieve abstraction. There can be only abstract methods in the Java interface, not method body. It is used to achieve abstraction and multiple inheritance in Java.

Since Java 8, we can have default and static methods in an interface.

Since Java 9, we can have private methods in an interface.


An ```interface``` is a completely "abstract class" that is used to group related methods with empty bodies:

Example:

```java
// Interface
interface Animal {
  public void sound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

// Cat "implements" the Animal interface
class Cat implements Animal {
  public void sound() {
    // The body of sound() is provided here
    System.out.println("The cat says: Miau");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}

class Main {
  public static void main(String[] args) {
    Cat myCat = new Cat();  // Create a Cat object
    myCat.animalSound();
    myCat.sleep();
  }
}
```

### Multiple Interfaces <a name="multiple-interface"></a>

Example:

```java
interface FirstInterface {
  public void myMethod(); // interface method
}

interface SecondInterface {
  public void myOtherMethod(); // interface method
}

class DemoClass implements FirstInterface, SecondInterface {
  public void myMethod() {
    System.out.println("Some text..");
  }
  public void myOtherMethod() {
    System.out.println("Some other text...");
  }
}

class Main {
  public static void main(String[] args) {
    DemoClass myObj = new DemoClass();
    myObj.myMethod();
    myObj.myOtherMethod();
  }
}
```

**About Information:**
- Like abstract classes, interfaces cannot be used to create objects (in the example above, it is not possible to create an "Animal" object in the MyMainClass)
- Interface methods do not have a body - the body is provided by the "implement" class
- On implementation of an interface, you must override all of its methods
- Interface methods are by default ```abstract``` and ```public```
- Interface attributes are by default ```public```, ```static``` and ```final```
- An interface cannot contain a constructor (as it cannot be used to create objects)

**Why And When To Use Interfaces?**

  - To achieve security - hide certain details and only show the important details of an object (interface).
  - Java does not support "multiple inheritance" (a class can only inherit from one superclass). However, it can be achieved with interfaces, because the class can implement multiple interfaces. Note: To implement multiple interfaces, separate them with a comma (see example below).
  - It can be used to achieve loose coupling.


**Java 8 interface**

Since Java 8, interface can have default and static methods which is discussed later.

The Java compiler adds public and abstract keywords before the interface method. Moreover, it adds public, static and final keywords before data members.

In other words, Interface fields are public, static and final by default, and the methods are public and abstract.

Print.java
```java
inteface Print(){
  int NUMBER = 5;
  voud print();
}
```

Compiler

Print.class
```java
interface Print(){
  public static final int NUMBER = 5;
  public abstract void print();

}
```
