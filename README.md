# Fundamentals of C#

## 🛠 Formatting string literals in C#
Here's what you've learned about formatting string literals so far:
- Use character escape sequences when you need to insert a special character into a string literal, such as a tab `\t`, newline `\n`, or double quote `\"`.
- Use an escape character for the backslash `\\` when you need to use a backslash in all other scenarios.
- Use the directive  `@` to create a verbatim string literal to preserve all whitespace formatting and all backslash characters in a string.
- Use `\uin` conjunction with a four-character code to represent Unicode (UTF-16) characters in a string.
- Unicode characters may not print correctly, depending on the application.
 ```c#
//Formatting Output Using Character Escape Sequences
Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ... \n"); // \n the sequence \nwill add a new line and the sequence
Console.WriteLine("Invoice: 1021\t\tComplete!"); // \t  will add a tab.
Console.WriteLine("Invoice: 1022\t\tComplete!");
Console.WriteLine("\nOutput Directory:\t"); 
Console.WriteLine("Hello \"World\"!"); // \" if you need to insert a double quote into a string literal

//Text string literals
Console.WriteLine(@"    c:\source\repos    
(this is where your code goes)");

//Unicode scape characters - we are using UTF-16 some chars required UTF-32 and need a scape secuence 
 Console.WriteLine("\u3053\u3093\u306B\u3061\u306F World!");

//Formatting output using Unicode escape characters
// To generate Japanese invoices:
// Nihon no seikyū-sho o seisei suru ni wa:
Console.Write("\n\n\u65e5\u672c\u306e\u8acb\u6c42\u66f8\u3092\u751f\u6210\u3059\u308b\u306b\u306f\uff1a\n\t");
// User command to run an application
Console.WriteLine(@"c:\invoices\app.exe -j");
 ```
## Combining Strings Using String Concatenation `+`
- String concatenation allows you to combine string literals and smaller variables into a single string.
- Avoid creating intermediate variables if adding them does not improve readability.

```c#
string firstName = "Bob";
string greeting = "Hello";
Console.WriteLine(greeting + " " + firstName + "!");
```

### Interpolation `{}`
- String interpolation provides an improvement over string concatenation by reducing the number of characters required in some situations.
- You can combine string interpolation and textual literals by combining the symbols for each and using the result as a prefix for the string template.
```c#
int version = 11;
string updateText = "Update to Windows";
string message = $"{updateText} {version}";
Console.WriteLine(message);
```

#### Combining textual literals and string interpolation
```c#
string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");
```

👩‍💻| **Example code combined all**
```c#
string projectName = "ACME";
string russianMessage = "\u041f\u043e\u0441\u043c\u043e\u0442\u0440\u0435\u0442\u044c \u0440\u0443\u0441\u0441\u043a\u0438\u0439 \u0432\u044b\u0432\u043e\u0434";       
Console.WriteLine("View English output:\n \t" + $@"c:\Exercise\{projectName}\data.txt"); 
Console.WriteLine($@"{russianMessage}:" + "\n \t" + $@"c:\Exercise\{projectName}\ru-RU\data.txt"); 
```
or 
```c#
string projectName = "ACME";
string englishLocation = $@"c:\Exercise\{projectName}\data.txt";
Console.WriteLine($"View English output:\n\t\t{englishLocation}\n");

string russianMessage = "\u041f\u043e\u0441\u043c\u043e\u0442\u0440\u0435\u0442\u044c \u0440\u0443\u0441\u0441\u043a\u0438\u0439 \u0432\u044b\u0432\u043e\u0434";
string russianLocation = $@"c:\Exercise\{projectName}\ru-RU\data.txt";
Console.WriteLine($"{russianMessage}:\n\t\t{russianLocation}\n");
```

`output`
```c#
View English output:
  c:\Exercise\ACME\data.txt

Посмотреть русский вывод:
  c:\Exercise\ACME\ru-RU\data.txt
```

## 🛠 Additions with implicit data conversion
- You can perform mathematical operations such as adding numbers.
- String concatenation and addition use the plus symbol `+`. This is called operator overloading. The compiler infers appropriate usage based on the data types it operates on.
- When possible, the C# compiler will implicitly convert an `int` to a `string` if it is obvious that the developer is attempting to concatenate the string representation of a number for presentation purposes.
- You can use parentheses to define the order of operations to explicitly tell the compiler that you want to perform certain operations before others.

```c#
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + (widgetsSold + 7) + " widgets.");
```

`output`
```c#
Bob sold 14 widgets.
```
## 🛠 Performing basic mathematical operations
### Code to perform addition, subtraction, multiplication, and division operations with integers
```c#
int sum = 7 + 5;
int difference = 7 - 5;
int product = 7 * 5;
int quotient = 7 / 5;

Console.WriteLine("Sum: " + sum); // +is the addition operator
Console.WriteLine("Difference: " + difference); // -is the subtraction operator
Console.WriteLine("Product: " + product); // *is the multiplication operator
Console.WriteLine("Quotient: " + quotient); // /is the division operator
```
### Add code to convert integer division results
To convert `int` to `decimal`

```c#
int first = 7;
int second = 5;
decimal quotient = (decimal)first / (decimal)second;
Console.WriteLine(quotient);
```
### Writing code to determine remainder after integer division
The modulus operator `%` tells you the remainder of the division int
```c#
Console.WriteLine($"Modulus of 200 / 5 : {200 % 5}");
Console.WriteLine($"Modulus of 7 / 5 : {7 % 5}");
```

### Order of operations
In mathematics, `PEMDAS` is an acronym that helps students remember the order of operations. The order is:
- P arentheses (what is inside the parentheses comes first)
- E xponents
- M ultiplication and D ivision (from left to right)
- Addition (addition) and Subtraction (subtraction) (from left to right)
```
int value1 = 3 + 4 * 5;
int value2 = (3 + 4) * 5;
Console.WriteLine(value1);
Console.WriteLine(value2);
```
## 🛠  Increment and decrement of values
- Use compound assignment operators such as `+=`, `-=`, `*=`, `++`, and `--` to perform a mathematical operation such as increment or decrement and then assign the result to the original variable.
- The increment and decrement operators work differently if the operator is before or after the operand.

```c#
int value = 1;

value = value + 1;
Console.WriteLine("First increment: " + value);

value += 1;
Console.WriteLine("Second increment: " + value);

value++;
Console.WriteLine("Third increment: " + value);

value = value - 1;
Console.WriteLine("First decrement: " + value);

value -= 1;
Console.WriteLine("Second decrement: " + value);

value--;
Console.WriteLine("Third decrement: " + value);
```

### Placement of increment and decrement operators
- The value is increased.
- The new incremented value of the variable is the retrieved value and is used in the string operation.
```c#
int value = 1;
value++;
Console.WriteLine("First: " + value);
Console.WriteLine($"Second: {value++}");
Console.WriteLine("Third: " + value);
Console.WriteLine("Fourth: " + (++value));
```

