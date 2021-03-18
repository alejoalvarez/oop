## Encapsulation


<p align="center">
<img height="270" src="https://github.com/Alejo-Alvarezv/OOP/blob/master/Images/encapsulation.png">
</p>

Encapsulation is defined as the wrapping up of data under a single unit. It is the mechanism that binds together code and the data it manipulates.Other way to think about encapsulation is, it is a protective shield that prevents the data from being accessed by the code outside this shield.

Technically in encapsulation, the variables or data of a class is hidden from any other class and can be accessed only through any member function of own class in which they are declared.
As in encapsulation, the data in a class is hidden from other classes, so it is also known as **data-hiding**.
Encapsulation can be achieved by: Declaring all the variables in the class as private and writing public methods in the class to set and get the values of variables.

The process of binding data and corresponding methods (behavior) together into a single unit is called encapsulation in Java. 

In other words, encapsulation is a programming technique that binds the class members (variables and methods) together and prevents them from being accessed by other classes, thereby we can keep variables and methods safes from outside interference and misuse.

Every Java class is an example of encapsulation because we write everything within the class only that binds variables and methods together and hides their complexity from other classes.

In the encapsulation technique, we declare the fields as private in the class to prevent other classes from accessing them directly. The required encapsulated data can be accessed by using public Java getter and setter method.

If the field is declared private in the class then it cannot be accessed by anyone from outside the class and hides the field within the class. Therefore, it is also called data hiding. 

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
