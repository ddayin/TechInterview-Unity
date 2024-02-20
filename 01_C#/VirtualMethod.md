In C#, the virtual keyword is used to modify a method, allowing it to be overridden in derived classes. When you declare a method as virtual in a base class, you're essentially saying that derived classes are allowed to provide their own implementations of that method.

Here's a simple example to illustrate the usage of virtual methods:

```C#
using System;

// Base class
class Animal
{
    // Virtual method
    public virtual void MakeSound()
    {
        Console.WriteLine("Some generic sound");
    }
}

// Derived class
class Dog : Animal
{
    // Override the virtual method from the base class
    public override void MakeSound()
    {
        Console.WriteLine("Woof!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal animal = new Animal();
        animal.MakeSound(); // Output: Some generic sound

        Dog dog = new Dog();
        dog.MakeSound(); // Output: Woof!
    }
}
```

In this example:

- The Animal class defines a virtual method MakeSound(). This method provides a default implementation that outputs "Some generic sound".
- The Dog class inherits from Animal and overrides the MakeSound() method with its own implementation, which outputs "Woof!".
- In the Main method, you create instances of both Animal and Dog, and call the MakeSound() method on each. The output demonstrates polymorphic behavior: the MakeSound() method invoked on Animal prints the default sound, while the MakeSound() method invoked on Dog prints the sound specific to dogs.
  
Using virtual methods in this way enables polymorphism, allowing you to write more flexible and extensible code by providing a way for derived classes to customize behavior defined in base classes.