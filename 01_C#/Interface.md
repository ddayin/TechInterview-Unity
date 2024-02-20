In C#, an interface defines a contract that specifies a set of members that classes must implement. Interfaces can contain methods, properties, events, and indexers, but they cannot contain any implementation code.

Here's a basic example of an interface in C#:

```C#
// Define an interface named IShape
interface IShape
{
    double Area(); // Method signature
}

// Implementing the interface in a class
class Rectangle : IShape
{
    public double Width { get; set; }
    public double Height { get; set; }

    // Implementing the Area method required by the IShape interface
    public double Area()
    {
        return Width * Height;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Rectangle rectangle = new Rectangle { Width = 5, Height = 10 };
        Console.WriteLine("Area of rectangle: " + rectangle.Area());
    }
}
```

In this example:

- IShape is the interface, which declares a method Area().
- Rectangle class implements the IShape interface by providing an implementation for the Area() method.
- The Main method in the Program class demonstrates how to use the Rectangle class, calling its Area() method.

Interfaces are commonly used in C# for defining contracts that classes must adhere to, enabling polymorphism and providing a way for classes to share common behavior without sharing a common base class.