In C#, the ref keyword is used to pass parameters by reference to a method, which allows the method to modify the value of the parameter directly. When you pass a parameter by reference using ref, you're essentially passing a reference to the original variable rather than a copy of its value. This enables the method to modify the original variable, and those modifications persist outside the method scope.

Here's a basic example demonstrating the usage of ref:

```C#
using System;

class Program
{
    static void Main(string[] args)
    {
        int num = 10;
        
        // Passing the variable 'num' by reference to the ModifyNumber method
        ModifyNumber(ref num);
        
        // The value of 'num' is modified directly within the ModifyNumber method
        Console.WriteLine(num); // Output: 20
    }

    static void ModifyNumber(ref int number)
    {
        // Modifying the value of the parameter directly
        number = number * 2;
    }
}
```

In this example:

- We have a variable num initialized with the value 10.
- We pass num to the ModifyNumber method using the ref keyword.
- Inside the ModifyNumber method, the value of number (the parameter) is doubled.
- Since num was passed by reference, its value gets modified directly within the ModifyNumber method.
- When we print the value of num after calling ModifyNumber, it reflects the change made within the method.
  
It's important to note that both the method declaration and the method call must use the ref keyword to indicate that the parameter is passed by reference. Additionally, both the caller and the callee must agree on using ref for the parameter. Otherwise, a compile-time error will occur.