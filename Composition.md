# Compositon vs Inheritance

## Composition
Composition is the design technique in object-oriented programming to implement **has-a** relationship between objects. Composition in java is achieved by using instance variables of other objects. For example, a person who has a Job is implemented like below in java object-oriented programming.

```java
public class Job {
// variables, methods etc.
}

public class Person {
  //composition has-a relationship
  private Job job;

  //variables, methods, constructors etc. object-oriented
```


## Inheritance
Inheritance is the design technique in object-oriented programming to implement is-a relationship between objects. Inheritance in Java is implemented using the extends keyword. For example, Cat is an Animal relationship in java programming will be implemented like below.

```java
public class Animal {
// variables, methods etc.
}
 
public class Cat extends Animal{
}
```
## Composition over Inheritance
- Inheritance is tightly coupled whereas composition is loosely coupled
- There is no access control in inheritance whereas access can be restricted in composition. We expose all the superclass methods to the other classes having access to subclass. So if a new method is introduced or there are security holes in the superclass, subclass becomes vulnerable. Since in composition we choose which methods to use, it’s more secure than inheritance.
- Composition provides flexibility in invocation of methods that is useful with multiple subclass scenario.
- One more benefit of composition over inheritance is testing scope. Unit testing is easy in composition because we know what all methods we are using from another class. We can mock it up for testing whereas in inheritance we depend heavily on superclass and don’t know what all methods of superclass will be used. So we will have to test all the methods of the superclass. This is extra work and we need to do it unnecessarily because of inheritance.

## Use inheritance only when you are sure that superclass will not be changed, otherwise go for composition.