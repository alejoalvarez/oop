# OOP
Object Oriented Programming (OOP)

Is a programming paradigm in which programs are organized around data, or based on the concept "objects", rather than functions and logic.

Basically an object can be defined as a data (attributes or properties) and behaviors (methods)

Simply put, OOP focuses on the objects that developers want to manipulate rather than the logic required to manipulate them. This approach to programming is well-suited for programs that are large, complex and actively updated or maintained. Due to the organization of an object-oriented program, this method is also conducive to collaborative development where projects can be divided into groups. Additional benefits of OOP include code reusability, scalability  and efficiency.

OOP was developed to increase the reusability and maintainability of source code. Transparent representation of the control flow had no priority and was meant to be handled by a compiler. With the increasing relevance of parallel hardware and multithreaded coding, developing transparent control flow becomes more important, something hard to achieve with OOP

## Principles of OOP
Object-oriented programming is based on the following principles:

- **Encapsulation**
The implementation and state of each object are privately held inside a defined boundary, or class. Other objects do not have access to this class or the authority to make changes but are only able to call a list of public functions, or methods. This characteristic of data hiding provides greater program security and avoids unintended data corruption.

  [Example Encapsulation](https://github.com/Alejo-Alvarezv/OOP/blob/master/Encapsulation/Recap.md)
- **Abstraction**
Objects only reveal internal mechanisms that are relevant for the use of other objects, hiding any unnecessary implementation code. This concept helps developers make changes and additions over time more easily.

- **Inheritance**
Relationships and subclasses between objects can be assigned, allowing developers to reuse a common logic while still maintaining a unique hierarchy. This property of OOP forces a more thorough data analysis, reduces development time and ensures a higher level of accuracy.

- **Polymorphism**
Objects are allowed to take on more than one form depending on the context. The program will determine which 
meaning or usage is necessary for each execution of that object, cutting down on the need to duplicate code.

  Refers to the ability of OOPs programming languages to differentiate between entities with the same name efficiently. This is done by Java with the help of the signature and declaration of these entities.
  


## Objects and classes
Exist two main concepts in OOP: Classes and objects.

**Classes**: Is a template that allow to create object, containt the definition of attributes and the procedure for the class
**Objects**: Instances of clases

Example:

**Class** Person

**Attributes**: name, last name, phone, address
**Methods**: getName, getLastName, getPhone, getAddress

**Objects**

- **Object 1** => name:Alejo, last name: Vargas Alvarez, phone: 0000000, address: Street 1234

- **Object 2** => name:Juan,  last name: Restrepo Perez, phone: 1111111, address: Street 2345.

We have two object with the same definition of class (or template) but with diferent information


### SOLID
Five design principles intended to make software designs more understandable, flexible and maintainable
Single responsibility principle
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
Is a general repeatable solution to a commonly occurring problem in software design. A design pattern isn't a finished design that can be transformed directly into code. It is a description or template for how to solve a problem that can be used in many different situations.
