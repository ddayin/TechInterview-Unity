In C#, the terms "call by value" and "call by reference" describe the way arguments are passed to methods. Understanding these concepts is crucial for understanding how method parameters behave.

Call by Value:
- Value Types: When you pass a variable of a value type (such as a struct or a basic data type like int or float) as an argument to a method, you're passing it by value.
- Copy of Value: A copy of the variable's value is passed to the method. Any changes made to the parameter inside the method do not affect the original variable.
- Immutable: Value type parameters are immutable inside the method.

Example:

```C#
using System;

class Program
{
    static void Main(string[] args)
    {
        int number = 10;
        Console.WriteLine("Original value: " + number);

        // Passing the variable 'number' to the ChangeNumber method
        ChangeNumber(number);

        // The original value of 'number' remains unchanged
        Console.WriteLine("Value after method call: " + number);
    }

    static void ChangeNumber(int num)
    {
        // Incrementing the parameter 'num'
        num++;
        Console.WriteLine("Value inside method: " + num);
    }
}
```

Call by Reference:
- Reference Types: When you pass a variable of a reference type (such as a class) as an argument to a method, you're passing it by reference.
- Reference to the Object: Instead of passing a copy of the value, a reference to the original object in memory is passed.
- Mutability: Changes made to the parameter inside the method affect the original object.
Example:

```C#
using System;

class Program
{
    static void Main(string[] args)
    {
        MyClass obj = new MyClass();
        obj.MyProperty = 10;
        Console.WriteLine("Original value: " + obj.MyProperty);

        // Passing the object 'obj' to the ChangeObject method
        ChangeObject(obj);

        // The value of 'MyProperty' has been changed inside the method
        Console.WriteLine("Value after method call: " + obj.MyProperty);
    }

    static void ChangeObject(MyClass obj)
    {
        // Modifying the 'MyProperty' of the passed object
        obj.MyProperty = 20;
        Console.WriteLine("Value inside method: " + obj.MyProperty);
    }
}

class MyClass
{
    public int MyProperty { get; set; }
}
```

Summary:
- Call by value passes a copy of the value to the method, while call by reference passes a reference to the original object.
- Value types are passed by value, and reference types are passed by reference.
- Value type parameters are immutable inside the method, while reference type parameters can be mutated.