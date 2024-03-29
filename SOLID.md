# SOLID design principles

## Single responsibility principle

"A module should be responsible to one, and only one, actor."
All classes, functions, methods, modules should have one single responibility.
It should have only ONE reason to change.
Try not to cram many functionalities to a class, function, module.
Need to split apart functionalities.
Reason is when we need to change functionality.

## Open-closed principle

"Software entities (class, module, function) should be open for extension, but closed for modification."
We have to ability to make new types of things and allowing those new things to work automatically without having to make changes to the class/function.
(Do not follow this always, sometimes changing code is good).

## Liskov substitution

"If S is a subtype of T, then objects of type T may be replaced with objects of type S."
Composition.

## Interface segregation

"No code should be forced to depend on methods it does not use."

Interfaces and abstract classes.

## Dependency conversion

- High-level modules should not import anything from low-level modules. Both should depend on abstractions (e.g., interfaces).
- Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions.

Adapter pattern.
Code depends around a wrapper class and not the implementation classes.
Renderer -> DX12Renderer, OpenGLRenderer, VulkanRenderer