
# Table of Contents
1. [Inheritance](#Inheritance)
2. [Type of inheritance](#type-inheritance)
    -  [Single Inheritance](#single-inheritance)
    -  [Multiple Inheritance](#multiple-inheritance) 
    -  [Multilevel Inheritance](#multilevel-inheritance)
    -  [Hierarchical Inheritance](#hierarchical-inheritance)
    -  [Hybrid Inheritance](#hybrid-inheritance)
3. [Aggregation](#aggregation)


## Inheritance
Inheritance is the mechanism by which an object acquires the some/all properties of another object.

The idea behind inheritance in Java is that you can create new classes that are built upon existing classes. When you inherit from an existing class, you can reuse methods and fields of the parent class. Moreover, you can add new methods and fields in your current class also.

In Oriented Object Programming, the computer programs are designed in such a way where everything is an object that interacts with one another object. It basically, helps in reusing the code and establish a relationship between different classes.

**Why use inheritance in java**
- For Method Overriding (so runtime polymorphism can be achieved).
- For Code Reusability.

Terms:
- **Class**: A class is a group of objects which have common properties. It is a template or blueprint from which objects are created.
- **Sub Class/Child Class**: Subclass is a class which inherits the other class. It is also called a derived class, extended class, or child class.
- **Super Class/Parent Class**: Superclass is the class from where a subclass inherits the features. It is also called a base class or a parent class.
- **Reusability**: As the name specifies, reusability is a mechanism which facilitates you to reuse the fields and methods of the existing class when you create a new class. You can use the same fields and methods already defined in the previous class.

Syntax:
```java
class Subclass-name extends SuperclassName{  
   //methods and fields  
} 
```

```java
class Employee{  
 float salary=40000;  
} 

class Programmer extends Employee{  
 
 int bonus = 10000;  
 
 public static void main(String args[]){  
   Programmer p = new Programmer();  
   System.out.println("Programmer salary is: " + p.salary);  
   System.out.println("Bonus of Programmer is: " + p.bonus);  
 }  
}
```

<p align="center">
<img height="270" src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/inheritance.jpg">
</p>

## Types of Inheritance
### Single Inheritance

In single inheritance, one class inherits the properties of another. It enables a derived class to inherit the properties and behavior from a single parent class. This will, in turn, enable code reusability as well as add new features to the existing code.

When a class inherits another class, it is known as a single inheritance. In the example given below, Dog class inherits the Animal class, so there is the single inheritance.

```java
class Animal{  
    void eat(){
        System.out.println("eating...");
    }  
}

class Dog extends Animal{  
    void bark(){
        System.out.println("barking...");
    }  
}

class TestInheritance{  
    public static void main(String args[]){  
        Dog d=new Dog();  
        d.bark();  
        d.eat();  
    }
}
```

```
Output:
barking...
eating..
```

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/single-Inheritance.png">
</p>

Here, Class A is your parent class and Class B is your child class which inherits the properties and behavior of the parent class

### Multiple Inheritance

To reduce the complexity and simplify the language, multiple inheritance is not supported in java.

```java
class A{  
    oid msg(){
        System.out.println("Hello");
    }  
}  
class B{  
    void msg(){
        System.out.println("Welcome");
    }  
}  
class C extends A,B{
   
    public static void main(String args[]){  
        C obj=new C();  
        obj.msg();//Now which msg() method would be invoked?  
    }  
}  

```

```
Output:

compile time error
```

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/multiple-inheritance.png">
</p>

### Multilevel Inheritance
When a class is derived from a class which is also derived from another class, i.e. a class having more than one parent class but at different levels, such type of inheritance is called Multilevel Inheritance.

When there is a chain of inheritance, it is known as multilevel inheritance. As you can see in the example given below, BabyDog class inherits the Dog class which again inherits the Animal class, so there is a multilevel inheritance.

```java
class Animal{  
    void eat(){
        System.out.println("eating...");
    }  
}  

class Dog extends Animal{  
    void bark(){System.out.println("barking...");}  
}  

class BabyDog extends Dog{  
    void weep(){System.out.println("weeping...");}  
}     

class TestInheritance2{  
    public static void main(String args[]){  
        BabyDog d=new BabyDog();  
        d.weep();  
        d.bark();  
        d.eat();  
    }
}

```

```
Output: 

weeping...
barking...
eating...
```

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/multilevel-Inheritance.png">
</p>

If we talk about the flowchart, class B inherits the properties and behavior of class A and class C inherits the properties of class B. Here A is the parent class for B and class B is the parent class for C. So in this case class C implicitly inherits the properties and methods of class A along with Class B. That’s what is multilevel inheritance.

### Hierarchical Inheritance
When a class has more than one child classes (subclasses) or in other words, more than one child classes have the same parent class

When two or more classes inherits a single class, it is known as hierarchical inheritance. In the example given below, Dog and Cat classes inherits the Animal class, so there is hierarchical inheritance.

```java
class Animal{  
    void eat(){
        System.out.println("eating...");
    }  
}  
class Dog extends Animal{  
    void bark(){
        System.out.println("barking...");
    }  
}  
class Cat extends Animal{  
    void meow(){
        System.out.println("meowing...");
    }  
}  
class TestInheritance3{  
    public static void main(String args[]){  
        Cat c=new Cat();  
        c.meow();  
        c.eat();  
        //c.bark();//Compile Time Error  
    }
} 

```

```
Output:

meowing...
eating...
```

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/hierarchical-inheritance.jpg">
</p>

### Hybrid Inheritance
Hybrid inheritance is a combination of two or more types of inheritance.

<p align="center">
<img src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/hybrid-inheritance.png">
</p>


## Aggregation 

If a class have an entity reference, it is known as Aggregation

Consider a situation, Employee object contains many informations such as id, name, emailId etc. It contains one more object named address, which contains its own information such as city, state, country, zipcode etc. as given below.

```java
class Employee{  
    int id;  
    String name;  
    Address address;//Address is a class  
...  
} 
```

In such case, Employee has an entity reference address, so relationship is Employee HAS-A address.

```java
class Operation{  
 int square(int n){  
  return n * n;  
 }  
}  
  
class Circle{  
 Operation op; //aggregation  
 double pi = 3.14;  
    
 double area(int radius){  
   op = new Operation();  
   int rsquare = op.square(radius);//code reusability (i.e. delegates the method call).  
   return pi * rsquare;  
 }  
  
     
    
 public static void main(String args[]){  
   Circle c=new Circle();  
   double result=c.area(5);  
   System.out.println(result);  
 }  
}  
```

Real example 

```java
public class Address {  
    String city,state,country;  
    
    public Address(String city, String state, String country) {  
        this.city = city;  
        this.state = state;  
        this.country = country;  
    }  
}  
```

```java
public class Employee {  
int id;  
String name;  
Address address;  
  
public Employee(int id, String name,Address address) {  
    this.id = id;  
    this.name = name;  
    this.address=address;  
}  
  
void printInformation(){  
    System.out.println(id+" "+name);  
    System.out.println(address.city+" "+address.state+" "+address.country);  
}  
  
public static void main(String[] args) {  
    Address address1=new Address("id1","name1","address1");  
    Address address2=new Address("id1","name2","address2");  
    
    Employee employee1=new Employee(111,"Alejo 1",address1);  
    Employee employee2=new Employee(222,"Alejo 2",address2);  
        
    employee1.printInformation();  
    employee2.printInformation();  
        
    }  
}  
```

