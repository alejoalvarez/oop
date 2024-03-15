## Encapsulation

- “Encapsulation in Java can be defined as a mechanism using which the data and the methods that work on that data is wrapped to form a single unit.”

- Using encapsulation we can also hide the class data members (variables) from the other classes. These data member variables can be accessed indirectly using methods of the class in which they are declared. The methods in turn are accessed using the object of that class.

- Example (getters and setter methods)

- We can visualize encapsulation as a medical capsule. As we all know the medicine is enclosed inside a medical capsule. Similarly, data and methods are enclosed in a single unit in encapsulation.

<p align="center">
<img height="270" src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/encapsulation.png">
</p>

- Technically in encapsulation, the variables or data of a class is hidden from any other class and can be accessed only through any member function of own class in which they are declared.

- As in encapsulation, the data in a class is hidden from other classes, so it is also known as **data-hiding**.

- In other words, encapsulation is a programming technique that binds the class members (variables and methods) together and prevents them from being accessed by other classes.

## Encapsulation in java

We can achieve encapsulation in Java in the following ways.

- 1 Declaring the instance variable of the class as private. so that it cannot be accessed directly by anyone from outside the class.

- 2 Provide the public setter and getter methods in the class to set/modify the values of the variable/fields.

### Advantages

  **1**. The encapsulated code is more flexible and easy to change with new requirements.<br>
  **2**. It prevents the other classes to access the private fields.<br>
  **3**. Encapsulation allows modifying implemented code without breaking others code who have implemented the code.<br>
  **4**. It keeps the data and codes safe from external inheritance. Thus, Encapsulation helps to achieve security.<br>
  **5**. It improves the maintainability of the application.<br>
  **6**. If you don't define the setter method in the class then the fields can be made read-only.<br>
  **7**. If you don't define the getter method in the class then the fields can be made write-only<br>

### Disavantages
The main disadvantage of the encapsulation in Java is it increases the length of the code and slow shutdown execution.

### Tightly Encapsulated Class
If each variable is declared as private in the class, it is called tightly encapsulated class in Java. For tightly encapsulated class, we are not required to check whether class contains getter and setter method or not and whether these methods are declared as public or not.

:bulb: **Key points:** <br>
  **1**. It is highly recommended to declare data members as private in the class.<br>
  **2**. A combination of data hiding and abstraction is nothing but encapsulation.
        Encapsulation = Data Hiding + Abstraction <br>
If any component follows data hiding and abstraction, it is called an encapsulated component.


## **Why Do We Need Encapsulation**

**There are various reasons as to why encapsulation is essential in Java:**

- Encapsulation allows us to modify the code or A part of the code without having to change any other functions or code.
- Encapsulation controls how we access data.
- We can modify the code based on the requirements using encapsulation.
- Encapsulation makes our applications simpler.