In C#, both structs and classes are used to define custom types, but they have some important differences in terms of their behavior and usage:

Classes:
1. Reference Types: Classes are reference types, meaning when you create an instance of a class, you're actually creating a reference to the object in memory.

2. Heap Allocation: Objects of a class are allocated memory on the heap. This means that they have dynamic memory allocation and deallocation, and their lifetimes are managed by the garbage collector.

3. Inheritance: Classes support inheritance, allowing you to create hierarchies of related types.

4. Mutable: Class instances are mutable by default, meaning you can change their state after creation.

5. Pass by Reference: When you pass an instance of a class to a method, you're passing it by reference. This means changes made to the object inside the method affect the original object.

Example:
```C#
class MyClass
{
    public int MyProperty { get; set; }
}
```

Structs:
1. Value Types: Structs are value types, meaning when you create an instance of a struct, you're working directly with the data itself, not a reference to it.

2. Stack Allocation: Struct instances are typically allocated on the stack. They have a fixed size determined by their members.

3. No Inheritance: Structs do not support inheritance. They cannot be used as a base for other structs or classes.

4. Immutable: Structs are immutable by default. Once created, their state cannot be changed.

5. Pass by Value: When you pass an instance of a struct to a method, you're passing it by value. This means changes made to the struct inside the method do not affect the original struct.

Example:
```C#
struct MyStruct
{
    public int MyField;
}
```

Choosing Between Structs and Classes:
- Use structs:
  - When you need lightweight objects.
  - When the object logically represents a single value, like a Point or a DateTime.
  - When you want value semantics, or if you need to pass the object by value frequently.

Use classes:
- For complex objects that require inheritance or are intended to be used as base classes.
- When you need reference semantics, or if you need to share the object across multiple parts of your code without making copies.
- 
Understanding these differences is crucial for designing efficient and effective solutions in C#.