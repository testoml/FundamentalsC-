# Operators in C#
In C#, operators are special symbols or keywords used to perform operations on operands. These operands can be variables, constants, literals, or expressions. Operators in C# can be categorized into several types:

## 1. Arithmetic Operators
Arithmetic operators are used to perform basic mathematical operations.

Operator	| Description	| Example
--------- |------|--------|
`+`|	Addition|	`a + b`
`-`	|Subtraction	|`a - b`
`*`	|Multiplication|	`a * b`
`/`|	Division|	`a / b`
`%`	|Modulus	|`a % b`

```c#
int a = 10;
int b = 3;
Console.WriteLine(a + b);  // 13
Console.WriteLine(a - b);  // 7
Console.WriteLine(a * b);  // 30
Console.WriteLine(a / b);  // 3
Console.WriteLine(a % b);  // 1
```
## 2. Relational Operators
Relational operators are used to compare two values or expressions.

Operator	| Description	| Example
--------- |------|--------|
`==`|	Equal to|	`a == b`
`!=`|	Not equal to|	`a != b`
`>`|	Greater than| `a > b`
`<`|	Less than	| `a < b`
`>=`|	Greater than or equal|	`a >= b`
`<=`|	Less than or equal	|`a <= b`
```c#
int a = 5;
int b = 10;
Console.WriteLine(a == b);  // False
Console.WriteLine(a != b);  // True
Console.WriteLine(a > b);   // False
Console.WriteLine(a < b);   // True
Console.WriteLine(a >= b);  // False
Console.WriteLine(a <= b);  // True
```
## 3. Logical Operators
Logical operators are used to combine or invert boolean expressions.

Operator	| Description	| Example
--------- |------|--------|
`&&`	|Logical AND|`a && b`
`!`|	Logical NOT	|`!a`
```c#
bool a = true;
bool b = false;
Console.WriteLine(a && b);  // False
Console.WriteLine(a || b);  // True
Console.WriteLine(!a);      // False
```

## 4. Assignment Operators
Assignment operators are used to assign values to variables.

Operator	| Description	| Example
--------- |------|--------|
`=`|	Assign|	`a = b`
`+=`|	Add and assign|	`a += b`
`-=`|	Subtract and assign|	`a -= b`
`*=`|	Multiply and assign|	`a *= b`
`/=`|	Divide and assign|	`a /= b`
`%=`|	Modulus and assign|	`a %= b`
`<<=`|	Left shift and assign|	`a <<= b`
`>>=`|	Right shift and assign|	`a >>= b`
`&=`|	Bitwise AND and assign|	a `&= b`
`^=`|	Bitwise XOR and assign|	`a ^= b`
```c#
int a = 10;
a += 5;   // a = a + 5
Console.WriteLine(a);  // 15
a -= 3;   // a = a - 3
Console.WriteLine(a);  // 12
a *= 2;   // a = a * 2
Console.WriteLine(a);  // 24
a /= 4;   // a = a / 4
Console.WriteLine(a);  // 6
a %= 4;   // a = a % 4
Console.WriteLine(a);  // 2
```
## 5. Bitwise Operators
Bitwise operators perform bit-level operations on integer types.

Operator	| Description	| Example
--------- |------|--------|
`&`|	Bitwise AND|	`a & b`
`|	`|	`Bitwise OR`
`^`|	Bitwise XOR|	`a ^ b`
`~`|	Bitwise NOT	|`~a`
`<<`|	Left shift	|`a << b`
`>>`|	Right shift	|`a >> b`
```C#
int a = 5;  // 0101 in binary
int b = 3;  // 0011 in binary
Console.WriteLine(a & b);  // 1  (0001 in binary)
Console.WriteLine(a | b);  // 7  (0111 in binary)
Console.WriteLine(a ^ b);  // 6  (0110 in binary)
Console.WriteLine(~a);     // -6 (inverse of 0101 is 1010)
Console.WriteLine(a << 1); // 10 (1010 in binary)
Console.WriteLine(a >> 1); // 2  (0010 in binary)
```
## 6. Unary Operators
Unary operators operate on a single operand.

Operator	| Description	| Example
--------- |------|--------|
`+`	|Unary plus|	`+a`
`-`|	Unary minus|	`-a`
`++`|	Increment|	`a++ or ++a`
`--`|Decrement|	`a-- or --a`
`!`|	Logical NOT|	`!a`
`~`	|Bitwise NOT|	`~a`
```c#
int a = 5;
Console.WriteLine(+a);  // 5
Console.WriteLine(-a);  // -5

int b = 3;
Console.WriteLine(b++);  // 3 (post-increment: prints then increments)
Console.WriteLine(b);    // 4
Console.WriteLine(++b);  // 5 (pre-increment: increments then prints)
Console.WriteLine(b--);  // 5 (post-decrement: prints then decrements)
Console.WriteLine(b);    // 4
Console.WriteLine(--b);  // 3 (pre-decrement: decrements then prints)
```
## 7. Ternary (Conditional) Operator
The ternary operator is a shorthand for an if-else statement and it takes three operands.

Operator	| Description	| Example
--------- |------|--------|
`? :`|	Conditional (ternary)|	`condition ? valueIfTrue : valueIfFalse`
```c#
int a = 10;
int b = 20;
int max = (a > b) ? a : b;
Console.WriteLine(max);  // 20
```
## 8. Null-Coalescing Operator
The null-coalescing operator returns the left-hand operand if it is not null; otherwise, it returns the right-hand operand.

Operator	| Description	| Example
--------- |------|--------|
`?`|	Null-coalescing|	`a ?? b`
```c#
string s = null;
string result = s ?? "Default Value";
Console.WriteLine(result);  // "Default Value"
```
## 9. Null-Conditional Operator
The null-conditional operator is used to perform member or element access operations only if the operand is non-null.

Operator	| Description	| Example
--------- |------|--------|
`?.`|	Null-conditional	|`a?.b`
`?[ ]`|	Null-conditional index|	`a?[i]`
```c#
string s = null;
int? length = s?.Length;
Console.WriteLine(length);  // null
```
## 10. Type Testing and Conversion Operators
These operators are used for checking types and converting types.

Operator	| Description	| Example
--------- |------|--------|
`is`|	Type checking|	`a is int`
`as`|	Type conversion|	`a as string`
`typeof`|	Obtain type information|	`typeof(int)`
`sizeof`|	Get size of value type|	`sizeof(int)`
`checked`	|Enable overflow checking|	`checked(a + b)`
`unchecked`|	Disable overflow checking|	`unchecked(a + b)`
```c#
object obj = 42;
if (obj is int)
{
    int num = (int)obj;
    Console.WriteLine(num);  // 42
}

object obj2 = "hello";
string str = obj2 as string;
if (str != null)
{
    Console.WriteLine(str);  // "hello"
}

Console.WriteLine(typeof(int));  // System.Int32
Console.WriteLine(sizeof(int));  // 4
```
## Summary
- Arithmetic Operators: Perform basic mathematical operations.
- Relational Operators: Compare values.
- Logical Operators: Combine or invert boolean expressions.
- Assignment Operators: Assign values to variables.
- Bitwise Operators: Perform bit-level operations.
- Unary Operators: Operate on a single operand.
- Ternary Operator: Shorthand for if-else statements.
- Null-Coalescing Operator: Provides a default value for null references.
- Null-Conditional Operator: Safe member or element access.
- Type Testing and Conversion Operators: Check and convert types.
These operators allow for a wide range of operations, making C# a powerful and flexible programming language.
