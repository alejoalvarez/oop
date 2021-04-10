
# Table of Contents
1. [Object Oriented Programming](#OOP)
2. [Principles of OOP](#principles-OOP)
    -  [Encapsulation](#encapsulation)
    -  [Abstraction](#abstraction) 
    -  [Inheritance](#inheritance)
    -  [Polymorphism](#polymorphism)
    -  [Coupling](#coupling)
    -  [Cohesion](#cohesion)
    -  [Association](#association)
    -  [Aggregation](#aggregation)
    -  [Composition](#composition)
3. [Object and Clases](#objects-classes)
    -  [Classes](#classes)
    -  [Objects](#objects)
    -  [Methods](#method)
        -  [Constructor](#constructor)
    -  [static](#static)
    -  [this](#this)     
4. [SOLID](#solid)

## OOP - Object Oriented Programming <a name="OOP"></a>

Is a programming paradigm in which programs are organized around data, or based on the concept "objects", rather than functions and logic.

Basically an object can be defined as a data (attributes or properties) and behaviors (methods)

Simply put, OOP focuses on the objects that developers want to manipulate rather than the logic required to manipulate them. This approach to programming is well-suited for programs that are large, complex and actively updated or maintained. Due to the organization of an object-oriented program, this method is also conducive to collaborative development where projects can be divided into groups. Additional benefits of OOP include code reusability, scalability  and efficiency.

OOP was developed to increase the reusability and maintainability of source code. Transparent representation of the control flow had no priority and was meant to be handled by a compiler. With the increasing relevance of parallel hardware and multithreaded coding, developing transparent control flow becomes more important, something hard to achieve with OOP

## Principles of OOP <a name="principles-OOP"></a>
<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/Pillar-OOP.jpg">
</p>

**Object Oriented Programming is based on the following principles**:

### ```Encapsulation``` <a name="encapsulation"></a>
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
   
### ```Abstraction``` <a name="abstraction"></a>
Abstract Classes and Methods

Objects only reveal internal mechanisms that are relevant for the use of other objects, hiding any unnecessary implementation code. This concept helps developers make changes and additions over time more easily.

Data abstraction is the process of hiding certain details and showing only essential information to the user.
Abstraction can be achieved with either abstract classes or interfaces (which you will learn more about in the next chapter).

- **Abstract class**: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
- **Abstract method**: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).

An abstract class can have both abstract and regular methods:

Example:
```java
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void sound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Cat extends Animal {
  public void sound() {
    // The body of sound() is provided here
    System.out.println("The cat says: Miau");
  }
}

class Main {
  public static void main(String[] args) {
    Cat myCat = new Cat(); // Create a Cat object
    myCat.animalSound();
    myCat.sleep();
  }
}
```

  [See more about Abstraction](https://github.com/Alejo-Alvarezv/OOP/blob/master/Abstraction)

### ```Inheritance``` <a name="inheritance"></a>
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

### ```Polymorphism``` <a name="polymorphism"></a>
Objects are allowed to take on more than one form depending on the context. The program will determine which 
meaning or usage is necessary for each execution of that object, cutting down on the need to duplicate code.

Refers to the ability of OOPs programming languages to differentiate between entities with the same name efficiently.

Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.

Like we specified in the previous chapter; Inheritance lets us inherit attributes and methods from another class. Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways

Example 

```java
class Animal {
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Cat extends Animal {
  public void animalSound() {
    System.out.println("The cat says: Miau");
  }
}

class Dog extends Animal {
  public void animalSound() {
    System.out.println("The dog says: Guau");
  }
}

class Main {
  public static void main(String[] args) {
    Animal myAnimal = new Animal();  // Create a Animal object
    Animal myCat = new Cat();  // Create a Cat object
    Animal myDog = new Dog();  // Create a Dog object
    myAnimal.animalSound();
    myCat.animalSound();
    myDog.animalSound();
  }
}
```

**Why And When To Use "Inheritance" and "Polymorphism"?**

It is useful for code reusability: reuse attributes and methods of an existing class when you create a new class.

  [See more about Polymorphism](https://github.com/Alejo-Alvarezv/OOP/blob/master/Polymorphism)


### Coupling <a name="coupling"></a>
Coupling refers to the knowledge or information or dependency of another class. It arises when classes are aware of each other. If a class has the details information of another class, there is strong coupling. In Java, we use private, protected, and public modifiers to display the visibility level of a class, method, and field. You can use interfaces for the weaker coupling because there is no concrete implementation.

### Cohesion <a name="cohesion"></a>
Cohesion refers to the level of a component which performs a single well-defined task. A single well-defined task is done by a highly cohesive method. The weakly cohesive method will split the task into separate parts. The java.io package is a highly cohesive package because it has I/O related classes and interface. However, the java.util package is a weakly cohesive package because it has unrelated classes and interfaces.

### Association <a name="association"></a>
Association represents the relationship between the objects. Here, one object can be associated with one object or many objects. There can be four types of association between the objects:

- One to One
- One to Many
- Many to One, and
- Many to Many

Let's understand the relationship with real-time examples. For example, One country can have one prime minister (one to one), and a prime minister can have many ministers (one to many). Also, many MP's can have one prime minister (many to one), and many ministers can have many departments (many to many).

Association can be undirectional or bidirectional.

### Aggregation <a name="aggregation"></a>
Aggregation is a way to achieve Association. Aggregation represents the relationship where one object contains other objects as a part of its state. It represents the weak relationship between objects. It is also termed as a has-a relationship in Java. Like, inheritance represents the is-a relationship. It is another way to reuse objects.

### Composition <a name="composition"></a>
The composition is also a way to achieve Association. The composition represents the relationship where one object contains other objects as a part of its state. There is a strong relationship between the containing object and the dependent object. It is the state where containing objects do not have an independent existence. If you delete the parent object, all the child objects will be deleted automatically.

## Objects and classes  <a name="objects-classes"></a>
Exist two main concepts in OOP: Classes and objects.

### Classes: <a name="classes"></a>

Is a template that allow to create object, containt the definition of attributes and the procedure for the class

- They are used to represent entities or concepts
- Each object created from a class is called an instance of the class
- Has methods (Performs a task)
- It has attributes, by convention they must be private
- The name must begin with a capital letter

**Static class:** 
- No need to create instances to call them
- Only static methods can be called

A class is a user defined blueprint or prototype from which objects are created. It represents the set of properties or methods that are common to all objects of one type. In general, class declarations can include these components, in order:
  - **Modifiers**: A class can be public or has default access (Refer this for details).
  - **Class name**: The name should begin with a initial letter (capitalized by convention).
  - **Superclass(if any)**: The name of the class’s parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
  - **Interfaces(if any)**: A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
  - **Body**: The class body surrounded by braces, { }.
  
### **Objects**: <a name="objects"></a>
- Instances of clases
- Object = instance

An instance is created so you can use the methods that that class defines.

  It is a basic unit of Object Oriented Programming and represents the real life entities. A typical Java program creates many objects, which as you know, interact by invoking methods. An object consists of:<br>
  - **State** : It is represented by attributes of an object. It also reflects the properties of an object.
  - **Behavior** : It is represented by methods of an object. It also reflects the response of an object with other objects.
  - **Identity** : It gives a unique name to an object and enables one object to interact with other objects.

### Method: <a name="method"></a>

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

**Ways to initialize object**

There are 3 ways to initialize object in Java.

- By reference variable
- By method
- By constructor


we can create objects with 6 different methods which are:

- By new keyword
- By newInstance() method of Class class
- By newInstance() method of constructor class
- By clone() method
- By deserialization
- By factory method

```Java Object Creation by new keyword```
It is the most simple and common way of creating an object of a class. By using the new keyword, we can call any type of constructor of the class that is, either the parameterized constructor or non-parameterized constructor.

```java
ClassName ObjectName = new ClassName();
```

```Java Object Creation by newInstance() method of Class class```
This is another technique to create an object of the class. We use the newInstance() method of a Class class to create an object. This newInstance() method calls the no-arg constructor of the class to create the object.

```java
Class cls = Class.forName("ClassName");
ClassName objectName = (ClassName) cls.newInstance();
```

```Java Object Creation by newInstance() method of Constructor class```
We can also use the newInstance() method of java.lang.reflect.Constructor class to create an object. The newInstance() method of the Constructor class is similar to the newInstance() method of the Class class.

```java
Constructor<ClassName> constructor = ClassName.class.getConstructor();
ClassName objectName = constructor.newInstance();
```

```Java Object Creation by clone() method```
When we call the clone() method through an object, the Java compiler automatically creates a new object of that class. JVM actually copies all content of the older object into the newly created object.

To use the clone() method on an object we have to implement the Cloneable interface and override the clone() method in our class.

```java
ClassName object1 = new ClassName();
ClassName object2 = (ClassName) object1.clone();
```

```Java Object Creation using deserialization```
When we serialize an object and then deserialize it, JVM creates a new object. To deserialize an object, we need to implement the java.io.Serializable.


```Initialization through reference:```
Initializing an object means storing data into the object. Let's see a simple example where we are going to initialize the object through a reference variable.

```java
class Student{  
 int id;  
 String name;  
}  

class Main{  
 public static void main(String args[]){  
  Student student1 = new Student();  
  student1.id=1;  
  student1.name="Alejo";  
  System.out.println(student1.id + " " + student1.name);
 }  
} 
```

```Initialization through method:```

We are creating the two objects of Student class and initializing the value to these objects by invoking the insertInformation method. Here, we are displaying the state (data) of the objects by invoking the printInformation() method.

```java
class Student{  
 int id;  
 String name;  

 void insertInformation(int r, String n){  
  id=r;  
  name=n;  
 }  
 void printInformation(){
   System.out.println(id + " " + name);
   }  
}  

class Main{  
 public static void main(String args[]){  
  Student student1=new Student();  
  Student student2=new Student();  
  student1.insertInformation(1,"Alejo");  
  student2.insertInformation(2,"Alejo 1");  
  student1.printInformation();  
  student2.printInformation();  
 }  
}  
```
As you can see in the above figure, object gets the memory in heap memory area. The reference variable refers to the object allocated in the heap memory area. Here, s1 and s2 both are reference variables that refer to the objects allocated in memory.

```Initialization through a constructor:```

```java
class Employee{  
    int id;  
    String name;  
    float salary; 

    void insertInformation(int i, String n, float s) {  
        id=i;  
        name=n;  
        salary=s;  
    }  
    void prprintInformationint(){
      System.out.println(id + " " + name + " " + salary);
    }  
}  

public class TestEmployee {  
public static void main(String[] args) {  
    Employee employee1=new Employee();  
    Employee employee2=new Employee();  
      
    employee1.insertInformation(1,"Alejo 1",45000);  
    employee2.insertInformation(2,"Alejo 2",25000);  
  
    employee1.printInformation();  
    employee2.printInformation();      
}  
} 
```

#### Constructor <a name="constructor"></a>

In Java, a constructor is a block of codes similar to the method. It is called when an instance of the class is created. At the time of calling constructor, memory for the object is allocated in the memory.

It is a special type of method which is used to initialize the object.

Every time an object is created using the new() keyword, at least one constructor is called.

It calls a default constructor if there is no constructor available in the class. In such case, Java compiler provides a default constructor by default.

There are two types of constructors in Java: no-arg constructor, and parameterized constructor.

Note: It is called constructor because it constructs the values at the time of object creation. It is not necessary to write a constructor for a class. It is because java compiler creates a default constructor if your class doesn't have any.

- Create the class
- Has the same name as the class
- The default classes are created with an empty constructor
- Occurs when an object of the type defined by the class is created
- It helps us to initialize an object
- Class method

There are two rules defined for the constructor.

- Constructor name must be the same as its class name
- A Constructor must have no explicit return type
- A Java constructor cannot be abstract, static, final, and synchronized

<p align="center">
<img height="270" src="https://github.com/alejoalvarez/Images/blob/trunk/Java/constructors.jpeg">
</p>

### static <a name="static"></a>

The static keyword in Java is used for memory management mainly. We can apply static keyword with variables, methods, blocks and nested classes. The static keyword belongs to the class than an instance of the class.

The static can be:

- Variable (also known as a class variable)
- Method (also known as a class method)
- Block
- Nested class

**static variable**

If you declare any variable as static, it is known as a static variable.

- The static variable can be used to refer to the common property of all objects (which is not unique for each object), for example, the company name of employees, college name of students, etc.
- The static variable gets memory only once in the class area at the time of class loading.

Advantages of static variable
It makes your program memory efficient (i.e., it saves memory).

```java
class Student{  
   int id;//instance variable  
   String name;  
   static String college ="TEST";//static variable  
     
   Student(int i, String n){  
   id = i;  
   name = n;  
   }  
   //method to display the values  
   void printInformation (){
     System.out.println(id + " " + name + " " + college);
    }  
}  
//Test class to show the values of objects  
public class TestStaticVariable1{  
 public static void main(String args[]){  
 Student student1 = new Student(111,"Alejo 1");  
 Student student2 = new Student(222,"Alejo 2");  
 //we can change the college of all objects by the single line of code  
 //Student.college="TEST";  
 student1.printInformation();  
 student2.printInformation();  
 }  
} 
```

**static method**

If you apply static keyword with any method, it is known as static method.

- A static method belongs to the class rather than the object of a class.
- A static method can be invoked without the need for creating an instance of a class.
- A static method can access static data member and can change the value of it.

```java
class Student{  
     int id;  
     String name;  
     static String college = "TEST";  
     
     //static method to change the value of static variable  
     static void change(){  
      college = "TEST2";  
     }  
     
     
     Student(int i, String n){  
      id = r;  
      name = n;  
     }  
     
     void printInformation(){
       System.out.println(id + " " + name + " " + college);
      }  
}  
//Test class to create and display the values of object  
public class TestStaticMethod{  
    public static void main(String args[]){  
      Student.change();//calling change method  
      
      Student student1 = new Student(111,"Alejo1");  
      Student student2 = new Student(222,"Alejo2");          
      
      s1.printInformation();  
      s2.printInformation();  
      s3.printInformation();  
    }  
}
```
There are two main restrictions for the static method. They are:

- The static method can not use non static data member or call non-static method directly.
- this and super cannot be used in static context.

```Why is the Java main method static?```
It is because the object is not required to call a static method. If it were a non-static method, JVM creates an object first then call main() method that will lead the problem of extra memory allocation.

**static  block**
- Is used to initialize the static data member.
- It is executed before the main method at the time of classloading.

```java
class Main{  
  static{
    System.out.println("static block is invoked");
  }  
  
  public static void main(String args[]){  
   System.out.println("Hello main");  
  }  
}  
```

```sh
Output:static block is invoked
       Hello main
```

```Can we execute a program without main() method?```
No, one of the ways was the static block, but it was possible till JDK 1.6. Since JDK 1.7, it is not possible to execute a Java class without the main method.

### this

There can be a lot of usage of java this keyword. In java, this is a reference variable that refers to the current object.

Here is given the 6 usage of java this keyword.

- **this** can be used to refer current class instance variable.
- **this** can be used to invoke current class method (implicitly)
- **this()** can be used to invoke current class constructor.
- **this** can be passed as an argument in the method call.
- **this** can be passed as argument in the constructor call.
- **this** can be used to return the current class instance from the method.


**(this) refer current class instance variable.**

The this keyword can be used to refer current class instance variable. If there is ambiguity between the instance variables and parameters, this keyword resolves the problem of ambiguity.

```java
class Student{  
  int id;  
  String name;  
  float fee;  

  Student(int id,String name,float fee){  
    this.id = id;  
    this.name = name;  
    this.fee = fee;  
  }  

  void printInformation(){
    System.out.println(id + " " + name + " " + fee);
  }
}  
    
  class TestThis2{  
  public static void main(String args[]){  
    Student student1=new Student(111,"Alejo1",5000f);  
    Student student2=new Student(22,"Alejo2",6000f);  
    student1.printInformation();  
    student2.printInformation();  
  }
}  
```

**(this) to invoke current class method**
You may invoke the method of the current class by using the this keyword. If you don't use the this keyword, compiler automatically adds this keyword while invoking the method. Let's see the example

```java
class Example{  
  void sayHelllo1(){
    System.out.println("hello 1");
  }  
  
  void sayHello2(){  
  System.out.println("hello 2");  
  //m();//same as this.m()  
  this.m();  
  }  
}  

class TestThis4{  
  public static void main(String args[]){  
  Example example=new Example();  
  example.sayHelllo2();  
  }
} 

//RESULT
hello 2
hello 1
```
**(this) to invoke current class constructor**

The this() constructor call can be used to invoke the current class constructor. It is used to reuse the constructor. In other words, it is used for constructor chaining.

```java
class Example{  
  Example(){
    System.out.println("hello 1");
  }  
  
  Example(int x){  
  this();  
  System.out.println(x);  
  }  
  
}  
class TestThis5{  
  public static void main(String args[]){  
    Example example = new Example(10);  
  }
}

//RESULT
hello 1
10
```

Real example
```java
class Student{  
  int id;  
  String name,course;  
  float fee;  

  Student(int id,String name,String course){  
  this.id=id;  
  this.name=name;  
  this.course=course;  
  }  

  Student(int id,String name,String course,float fee){  
  this(id,name,course);//reusing constructor  
  this.fee=fee;  
  }  

  void printInformation(){
    System.out.println(id + " " + name + " " + course + " " + fee);
  }

}  
  class TestThis7{  
  public static void main(String args[]){  
    Student student1=new Student(111,"Alejo1","java1");  
    Student student2=new Student(112,"sumit","java2",6000f);  
    student1.printInformation();  
    student2.printInformation();  
  }
} 
```

**(this) to pass as an argument in the method**

The this keyword can also be passed as an argument in the method. It is mainly used in the event handling. Let's see the example:

```java
class Example{  
  void printInformation(Example obj){  
    System.out.println("method is invoked");  
  }  

  void process(){  
    printInformation(this);  
  }  
  public static void main(String args[]){  
    Example example1 = new Example();  
    example1.process();  
  }  
}

//RESULT 
method is invoked
```

**(this) to pass as argument in the constructor call**

We can pass the this keyword in the constructor also. It is useful if we have to use one object in multiple classes. Let's see the example:

```java
class B{  
  A4 obj;  
  B(A4 obj){  
    this.obj=obj;  
  }  
  void display(){  
    System.out.println(obj.data);//using data member of A4 class  
  }  
}  
  
class A4{  
  int data=10;  
  A4(){  
   B b=new B(this);  
   b.display();  
  }  
  public static void main(String args[]){  
   A4 a=new A4();  
  }  
}  

//RESULT
10
```

**(this) keyword can be used to return current class instance**

We can return this keyword as an statement from the method. In such case, return type of the method must be the class type (non-primitive). Let's see the example:

```java
class A{  
  A getA(){  
    return this;  
  } 

  void msg(){
    System.out.println("Hello java");
  }

} 
  class Test1{  
    public static void main(String args[]){  
    new A().getA().msg();  
  }  
}  

//RESULT

Hello java
```

## SOLID <a name="solid"></a>
[View complete definition](https://github.com/alejoalvarez/SOLID)

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/SOLID.jpg">
</p>

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
