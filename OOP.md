# What is object-oriented programming?

Object-oriented programming (OOP) is a computer programming model that organizes software design around data, or objects, rather than functions and logic. An object can be defined as a data field that has unique attributes and behavior.

# Structure of object-oriented programming

The structure, or building blocks, of object-oriented programming include the following:

## Classes
User-defined data types that act as the blueprint for individual objects, attributes and methods.

## Objects
Instances of a class created with specifically defined data. Objects can correspond to real-world objects or an abstract entity. When class is defined initially, the description is the only object that is defined.

## Methods
Functions that are defined inside a class that describe the behaviors of an object. Each method contained in class definitions starts with a reference to an instance object. Additionally, the subroutines contained in an object are called instance methods. Programmers use methods for reusability or keeping functionality encapsulated inside one object at a time.

## Attributes
Defined in the class template and represent the state of an object. Objects will have data stored in the attributes field. Class attributes belong to the class itself.

# Benefits of OOP

## Modularity
Encapsulation enables objects to be self-contained, making troubleshooting and collaborative development easier.

## Reusability
Code can be reused through inheritance, meaning a team does not have to write the same code multiple times.

## Productivity
Programmers can construct new programs quicker through the use of multiple libraries and reusable code.

## Easily upgradable and scalable
Programmers can implement system functionalities independently.

## Interface descriptions
Descriptions of external systems are simple, due to message passing techniques that are used for objects communication.

## Security
Using encapsulation and abstraction, complex code is hidden, software maintenance is easier and internet protocols are protected.

## Flexibility
Polymorphism enables a single function to adapt to the class it is placed in. Different objects can also pass through the same interface.

# Object Oriented Principles
Object-oriented programming is based on the following principles:

## Encapsulation
Encapsulation is the mechanism of hiding of data implementation by restricting access to public methods. Instance variables are kept private and accessor methods are made public to achieve this.

```java
public class Employee {
  private String name;
  private Date dob;
  public String getName() {
      return name;
  }
  public void setName(String name) {
      this.name = name;
  }
  public Date getDob() {
      return dob;
  }
  public void setDob(Date dob) {
      this.dob = dob;
  }
}
```

## Abstraction
Abstract means a concept or an Idea which is not associated with any particular instance. Using abstract class/Interface we express the intent of the class rather than the actual implementation. In a way, one class should not know the inner details of another in order to use it, just knowing the interfaces should be good enough.

## Inheritance
Inheritances expresses “is-a” and/or“has-a” relationship between two objects. Using Inheritance, In derived classes we can reuse the code of existing super classes. In Java, concept of “is-a” is based on class inheritance (using extends) or interface implementation (using implements).

For example, FileInputStream "is-a" InputStream that reads from a file.

## Polymorphism
It means one name many forms. It is further of two types — static and dynamic. Static polymorphism is achieved using method overloading and dynamic polymorphism using method overriding. It is closely related to inheritance. We can write a code that works on the superclass, and it will work with any subclass type as well.