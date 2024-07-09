# Java fundamentals & Basics


## Expressions
An `expression` is a coding contruct made up of `variables`, `operators`, & `method invocations` that equate to a single value. The expression is the code segment found on the right side of the equals sign in an assignment or decleration statement.

A `literal` is the SIMPLIST form of an expression. It can not be changed like a variable. 

## Statements
What is a statement? Java statements are fundamental building blocks in Java. A `statement` in Java is an instruction; a command for the programming language to execute. Statements can be simple or compound. There are three types of statements in Java.

Simply put, a `statement` is any instruction given to the programming language to execute. "carrying out actions."

### Expression Statement
An `expression statement` is a statement that includes one or more expressions. They can change values of `variables`, `call methods`, and `create objects`.

While all expression statements are statements; not all statements can be an expression. This is because expressions can be assigned and used as operands, while statements can only be declared.

EX.
~~~
int myFirstNumber = ((10 + 5) * (2 + 4))
~~~
This line of code has three expressions:
1. (10 + 5)
2. (2 + 4)
3. (15 * 8) What is assigned to myFirstNumber

### Decleration Statment
A Decleration Statment is used to declare/ define a variable by indicating the `Data Type` & `Name`. Optionally to set to a specific value.

EX.
~~~
int myFirstNumber;
// OR
int myFirstNumber = 25;
~~~
The data type is delcared and a name is given to the variable so it may be accessed later in memory and a value has been set.  However, it is not required to set a value.

FOR REFERENCE: the value of `25` in the code above is an expression. 

### Control-Flow Statements
`Control Flow Statements` determine the order that statements are executed. A great example of a `Contorl Flow Statement` is an if/else statement. 

## Variables
A `Variable` needs a data type & name to be stored in the RAM. An expression is used to assign a single value to the variable. Variables are, as the name suggests, variable. Meaning, their value can change.

Multiple variables can be assigned on the same line as long as the data type is first declared.

Behind the scence: Java has allocated a place in memory to store the information and set up a mechanism to allow access of the location through the given name. 

* A variable needs an expression to initialize a value
* A variable can only be delcared once, but can be initialized many times changing the value
* There are 8 Primitive data types that a variable can be assigned

## Operators
`Operatores` perform an operation on a variable or value.

An Example is addition, subtraction, division, & multiplication.

## Primitive Data Types

There are 8 Primitive Data Types:

Below is a graph showcasing their width, min and max, as well as range.
![Alt Text](https://www.ggorantala.dev/content/images/size/w1000/2023/04/image.png)

Below is a Sketch dividing the primitive and non-primitive data types.
![Alt Text](https://www.ggorantala.dev/content/images/2023/04/data-types-detail.png)

Primitive data types are simply a place holder in memory for a value. For instance, a number or a character. It's important to note that `Primitive Data Types` are ***NOT OBJECTS***. The value stored in primitives are called literals.

### Wrapper Class
`Wrapper Classes` are used to convert `Primitive data types` into an `object` and an `object` back into `primitive data types`. This is a very powerful tool as it allows a way for Primitive data types to be treated as objects. Great examples of this are `Generics`, `Data Structers`, and `Libraries`! Many only work with objects, not primitives.

A Wrapper Class also provides simple operations including basic information about primitive data types which can't be stored on the primitive itself.
EX.
```
int myMinIntValue = Integer.MIN_VALUE;
```
The wrapper class in this case is the keyword ***Integer***, shown as an expression. To isntatiate a wrapper class, you must use the full name of the primitive data type starting with a capital letter followed by the function you wish to use.

## Overflow & Underflow
`Overflow` & `Underflow`; AKA `Wrap Arrounds`. Happens when the data type exceds it's bit-size (maximum or minimum value, AKA width) through an expression. Integer 'wrap around' events does not give an error because when using an expression that `overflows` or `underflows`; the java compilier doesn't attempt to evaluate the expression to determine its value. This causes the value to `Wrap Around` to a negative or positive value. However, when using a literal to assign an integer a larger or smaller allowed value, an error will be thrown.

### Example 1
```
int willThisCompile = (Integer.MAX_VALUE + 1);
int willThisCompile = (2147483647 + 1);
```
Both will overflow to a negative number.
```
int willThisCompile ==> -2147483648 
```
This is the minumum value of an integer
### Example 3
```
int willThisCompile = 2147483648;
```
An Error is thrown; 
```
Error:
interger number too large
```

## Casting 
Casting means to treat or convert a number from one type to another.
```
Byte myMinByte = Byte.MIN_VALUE;
byte myFirstByte = (myMinByte / 2);
```
The code above will give an Error: *incompatible types: int cannot be converted to java.lang.Byte*

This is because the default data type in Java is an Integer. The Java compiler does not attempt to evalute the value in the expression to make sure the value fits in the allowable range of a `Byte`. However, if the expression were to use literals. the `Java Compiler` would be able to evalue the value at compile time and figure out whether or not it fits into the `variable`. 

###There is a solution; casting:
```
Byte myMinByte = Byte.MIN_VALUE;
byte myFirstByte = (byte) (myMinByte / 2);
```
The output above will be -64. The statement works because we have told the compiler what data type we are using through casting. To do this, we simply state the data type prior to the expression we wish to utilize. This is common practice and not special to Java.
