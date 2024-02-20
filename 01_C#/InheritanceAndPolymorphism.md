In C#, inheritance and polymorphism are fundamental concepts in object-oriented programming (OOP). They allow you to create relationships between classes, enabling code reuse and abstraction.

Inheritance:
Inheritance allows a class (called a subclass or derived class) to inherit the properties and behavior of another class (called a superclass or base class). This means that the subclass has access to all the members (fields, properties, methods) of the superclass.

```C#
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Animal is eating");
    }
}

class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog is barking");
    }
}
```
In the above example, the Dog class inherits from the Animal class. So, a Dog object can both Eat() (inherited from Animal) and Bark().

Polymorphism:
Polymorphism allows objects of different types to be treated as objects of a common base type. This means that a method can behave differently based on the object it is called with. There are two types of polymorphism in C#: compile-time polymorphism (method overloading) and runtime polymorphism (method overriding).

Method Overloading (Compile-time Polymorphism):
Method overloading allows you to define multiple methods with the same name but with different parameters in the same class. The appropriate method is called based on the arguments provided at compile time.

```C#
class MathOperations
{
    public int Add(int a, int b)
    {
        return a + b;
    }

    public double Add(double a, double b)
    {
        return a + b;
    }
}
```
Method Overriding (Runtime Polymorphism):
Method overriding allows a subclass to provide a specific implementation of a method that is already defined in its superclass. This is achieved by using the virtual keyword in the base class and the override keyword in the derived class.

```C#
class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Animal makes a sound");
    }
}

class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Dog barks");
    }
}
```
In the above example, if you call MakeSound() on a Dog object, it will execute the overridden method from the Dog class.

In summary, inheritance allows classes to inherit properties and behavior from other classes, while polymorphism enables flexibility and dynamic behavior in method invocation. These concepts are crucial for building modular, extensible, and maintainable code in C#.