# C# interview questions

## Variables and its declaration
Variables in C# are named storage locations that hold data values, enabling the program to manipulate and access that data dynamically.


## Paramenters

In C#, parameters are used to pass values or references to methods and functions. C# supports different types of parameters to provide flexibility in how methods are called and how data is passed. Here are the main types of parameters in C#:

1. Value Parameters (Default)
These are the default type of parameters in C#. When you pass a value type to a method, a copy of the value is passed. Changes made to the parameter inside the method do not affect the original value.
```c#
using System;

public class Program
{
    public static void Increment(int value)
    {
        value++;
        Console.WriteLine("Inside method: " + value);
    }

    public static void Main()
    {
        int number = 5;
        Increment(number);
        Console.WriteLine("Outside method: " + number);
    }
}
```
2. Reference Parameters (ref)
When you pass a parameter by reference using the ref keyword, the called method can modify the variable's value, and the changes will be reflected outside the method.

```
using System;

public class Program
{
    public static void Increment(ref int value)
    {
        value++;
        Console.WriteLine("Inside method: " + value);
    }

    public static void Main()
    {
        int number = 5;
        Increment(ref number);
        Console.WriteLine("Outside method: " + number);
    }
}
```
3. Output Parameters (out)
The out keyword allows a method to return multiple values. It is similar to ref, but out parameters do not require initial values before being passed to the method.

```
using System;

public class Program
{
    public static void GetValues(out int x, out int y)
    {
        x = 10;
        y = 20;
    }

    public static void Main()
    {
        int a, b;
        GetValues(out a, out b);
        Console.WriteLine("Values: " + a + ", " + b);
    }
}
4. Parameter Arrays (params)
The params keyword allows you to pass a variable number of arguments to a method. It must be the last parameter in the method signature.

```
```
using System;

public class Program
{
    public static void PrintNumbers(params int[] numbers)
    {
        foreach (int number in numbers)
        {
            Console.WriteLine(number);
        }
    }

    public static void Main()
    {
        PrintNumbers(1, 2, 3, 4, 5);
    }
}
```
5. Optional Parameters
C# allows you to define methods with optional parameters, which means you can call the method without providing arguments for those parameters.

```
using System;

public class Program
{
    public static void Greet(string name, string greeting = "Hello")
    {
        Console.WriteLine(greeting + ", " + name);
    }

    public static void Main()
    {
        Greet("Alice");
        Greet("Bob", "Hi");
    }
}

```
6. Named Parameters
Named parameters allow you to specify arguments by the parameter name. This can improve code readability and allows you to provide arguments in any order.

```
using System;

public class Program
{
    public static void DisplayInfo(string name, int age, string city)
    {
        Console.WriteLine($"Name: {name}, Age: {age}, City: {city}");
    }

    public static void Main()
    {
        DisplayInfo(age: 25, name: "Alice", city: "New York");
    }
}
```
Summary
Value Parameters: Pass by value, default behavior.
Reference Parameters (ref): Pass by reference, the caller's variable can be modified.
Output Parameters (out): Similar to ref, but used to return multiple values.
Parameter Arrays (params): Allows a variable number of arguments.
Optional Parameters: Allows some parameters to be optional with default values.
