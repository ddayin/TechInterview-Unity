Serialization in C# refers to the process of converting an object into a format that can be easily stored, transmitted, or reconstructed later. This process is commonly used when you need to save an object's state to a file, send it over a network, or store it in a database. Conversely, deserialization is the process of reconstructing an object from its serialized form.

C# provides built-in support for serialization through the System.Runtime.Serialization namespace. There are several ways to perform serialization in C#, including XML Serialization, Binary Serialization, and JSON Serialization.

XML Serialization: This approach involves converting objects into XML format, which is human-readable and can be easily processed by other systems.

```C#
using System;
using System.IO;
using System.Xml.Serialization;

[Serializable]
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        Person person = new Person { Name = "John", Age = 30 };

        XmlSerializer serializer = new XmlSerializer(typeof(Person));
        using (TextWriter writer = new StreamWriter("person.xml"))
        {
            serializer.Serialize(writer, person);
        }

        // Deserialization
        Person deserializedPerson;
        using (TextReader reader = new StreamReader("person.xml"))
        {
            deserializedPerson = (Person)serializer.Deserialize(reader);
        }

        Console.WriteLine($"Name: {deserializedPerson.Name}, Age: {deserializedPerson.Age}");
    }
}
```

Binary Serialization: This approach involves converting objects into binary format, which is more efficient but not human-readable.

```C#
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

[Serializable]
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        Person person = new Person { Name = "John", Age = 30 };

        BinaryFormatter formatter = new BinaryFormatter();
        using (Stream stream = new FileStream("person.bin", FileMode.Create, FileAccess.Write, FileShare.None))
        {
            formatter.Serialize(stream, person);
        }

        // Deserialization
        Person deserializedPerson;
        using (Stream stream = new FileStream("person.bin", FileMode.Open, FileAccess.Read, FileShare.None))
        {
            deserializedPerson = (Person)formatter.Deserialize(stream);
        }

        Console.WriteLine($"Name: {deserializedPerson.Name}, Age: {deserializedPerson.Age}");
    }
}
```

JSON Serialization: This approach involves converting objects into JSON format, which is commonly used for web APIs and data exchange between systems.

```C#
using System;
using System.IO;
using System.Text.Json;

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        Person person = new Person { Name = "John", Age = 30 };

        string jsonString = JsonSerializer.Serialize(person);
        File.WriteAllText("person.json", jsonString);

        // Deserialization
        string jsonStringRead = File.ReadAllText("person.json");
        Person deserializedPerson = JsonSerializer.Deserialize<Person>(jsonStringRead);

        Console.WriteLine($"Name: {deserializedPerson.Name}, Age: {deserializedPerson.Age}");
    }
}
```
These examples demonstrate the basic usage of serialization in C#. Depending on your requirements and the nature of your application, you can choose the appropriate serialization method. Each method has its advantages and considerations, such as performance, interoperability, and human-readability.