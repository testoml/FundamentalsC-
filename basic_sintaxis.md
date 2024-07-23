
# Variables and its declaration
In C#, variables are used to store data that can be manipulated within a program. They have a type, a name, and a scope. Here are the key concepts related to variables in C#:

## 1. Variable Declaration and Initialization
You declare a variable by specifying its type and name. You can also initialize it with a value.

```c#
// Declaration
int age;
// Initialization
age = 25;
// Declaration and initialization
int number = 10;
```
## 2. Data Types
C# is a strongly typed language, meaning each variable must be declared with a specific data type. Common data types include:

- Integral Types: `int`, `long`, `short`, `byte`
- Floating-Point Types: `float`, `double`
- Decimal Type: `decimal`
- Boolean Type: `bool`
- Character Type: `char`
- String Type: `string`
- Object Type: `object`
```c#
int integerNumber = 42;
long longNumber = 1234567890L;
short shortNumber = 30000;
byte byteNumber = 255;

float floatNumber = 3.14f;
double doubleNumber = 3.14159265358979;
decimal decimalNumber = 19.99m;

bool isTrue = true;
char character = 'A';
string text = "Hello, World!";
object anyObject = "This could be any type";
```
## 3. Type Inference with var
The var keyword allows the compiler to infer the type of a variable based on the assigned value.

```c#
var number = 10;       // int
var text = "Hello";    // string
var isTrue = true;     // bool
```

## 4. Constants
Constants are immutable values which are known at compile time and do not change for the life of the program. They are declared using the const keyword.
```c#
const int daysInWeek = 7;
const double pi = 3.14159;
```

## 5. Read-Only Variables
Read-only variables can be assigned a value only during declaration or in a constructor in the case of instance fields.

```c#
public class MyClass
{
    public readonly int readOnlyValue = 10;

    public MyClass(int value)
    {
        readOnlyValue = value;
    }
}
```
## 6. Static Variables
Static variables are shared among all instances of a class. They are declared using the static keyword.

```c#
public class MyClass
{
    public static int staticValue = 100;
}
```
## 7. Local Variables
Local variables are declared inside a method or block and are accessible only within that scope.
```c#
public void MyMethod()
{
    int localVar = 20;
    Console.WriteLine(localVar);
}
```
## 8. Instance Variables
Instance variables (fields) are declared inside a class but outside any method. They are accessible by all methods of the class.
```c#
public class MyClass
{
    private int instanceVar;

    public void SetVar(int value)
    {
        instanceVar = value;
    }

    public void DisplayVar()
    {
        Console.WriteLine(instanceVar);
    }
}
```
## 9. Array Variables
Arrays store multiple values of the same type.
```c#
int[] numbers = { 1, 2, 3, 4, 5 };
string[] names = new string[3];
names[0] = "Alice";
names[1] = "Bob";
names[2] = "Charlie";
```
## Summary
- Variable Declaration: Specify the type and name.
- Data Types: C# has various data types including integral, floating-point, decimal, boolean, character, string, and object types.
- Type Inference: var allows the compiler to infer the variable type.
- Constants: Use const for immutable values.
- Read-Only Variables: Use readonly for variables that can be assigned only once.
- Static Variables: Use static for variables shared across all instances of a class.
- Local Variables: Declared within methods or blocks and accessible only within that scope.
- Instance Variables: Fields declared in a class and accessible by all class methods.
- Array Variables: Used to store multiple values of the same type.


# Paramenters

In C#, parameters are used to pass values or references to methods and functions. C# supports different types of parameters to provide flexibility in how methods are called and how data is passed. Here are the main types of parameters in C#:

### 1. Value Parameters (Default)
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
### 2. Reference Parameters (ref)
When you pass a parameter by reference using the ref keyword, the called method can modify the variable's value, and the changes will be reflected outside the method.

```c#
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
### 3. Output Parameters (out)
The `out` keyword allows a method to return multiple values. It is similar to ref, but `out` parameters do not require initial values before being passed to the method.

```c#
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
```
### 4. Parameter Arrays (params)
The  `params` keyword allows you to pass a variable number of arguments to a method. It must be the last parameter in the method signature.

```c#
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
### 5. Optional Parameters
C# allows you to define methods with optional parameters, which means you can call the method without providing arguments for those parameters.

```c#
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
### 6. Named Parameters
Named parameters allow you to specify arguments by the parameter name. This can improve code readability and allows you to provide arguments in any order.

```c#
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

### Summary
- Value Parameters: Pass by value, default behavior.
- Reference Parameters (ref): Pass by reference, the caller's variable can be modified.
- Output Parameters (out): Similar to ref, but used to return multiple values.
- Parameter Arrays (params): Allows a variable number of arguments.
- Optional Parameters: Allows some parameters to be optional with default values.
