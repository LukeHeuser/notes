# Java fundamentals & Basics


# Expressions
An `expression` is a coding contruct made up of `variables`, `operators`, & `method invocations` that equate to a single value. The expression is the code segment found on the right side of the equals sign in an assignment or decleration statement.

A `literal` is the SIMPLIST form of an expression. It can not be changed like a variable. 

# Statements
What is a statement? Java statements are fundamental building blocks in Java. A `statement` in Java is an instruction; a command for the programming language to execute. Statements can be simple or compound. There are three types of statements in Java.

A statement can be on multiple lines. Many statements may also share the same line.

> Statements are stand alone units of work

Simply put, a `statement` is any instruction given to the programming language to execute. "carrying out actions."

## Expression Statement
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

## Decleration Statment
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

# Variables
A `Variable` needs a data type & name to be stored in the RAM. An expression is used to assign a single value to the variable. Variables are, as the name suggests, variable. Meaning, their value can change.

Multiple variables can be assigned on the same line as long as the data type is first declared.

Behind the scence: Java has allocated a place in memory to store the information and set up a mechanism to allow access of the location through the given name. 

* A variable needs an expression to initialize a value
* A variable can only be delcared once, but can be initialized many times changing the value
* There are 8 Primitive data types that a variable can be assigned

## Operators
`Operatores` perform an operation on a variable or value.

A basic example is `Addition`, `Subtraction`, `Division`, & `Multiplication`.

### Compound Assignment Operator

Compound assignment operators are shortcuts that do a math operation and assignment in one step. These operators first add, multiply, etc.. the right operand and left operand and then assign the result to left operand.

***+=***   

***-=***

****=***

***/=***

EX. 1
```
int firstInt = 25;
firstInt += 25 - 20; // Result is 30
```
Ex. 2
```
int firstInt = 5;
firstInt *= 25 - 20; // result is 25
```

# Primitive Data Types

There are 8 Primitive Data Types:

Below is a graph showcasing their width, min and max, as well as range.
![Alt Text](https://www.ggorantala.dev/content/images/size/w1000/2023/04/image.png)

Below is a Sketch dividing the primitive and non-primitive data types.
![Alt Text](https://www.ggorantala.dev/content/images/2023/04/data-types-detail.png)

Primitive data types are simply a place holder in memory for a value. For instance, a number or a character. It's important to note that `Primitive Data Types` are ***NOT OBJECTS***. The value stored in primitives are called literals.

## Wrapper Class
`Wrapper Classes` are used to convert `Primitive data types` into an `object` and an `object` back into `primitive data types`. This is a very powerful tool as it allows a way for Primitive data types to be treated as objects. Great examples of this are `Generics`, `Data Structers`, and `Libraries`! Many only work with objects, not primitives.

A Wrapper Class also provides simple operations including basic information about primitive data types which can't be stored on the primitive itself.
EX.
```
int myMinIntValue = Integer.MIN_VALUE; // Assigns the minimum intager value to the variable
```
The wrapper class in this case is the keyword ***Integer***, shown as an expression. To instantiate a wrapper class, you must use the full name of the primitive data type starting with a capital letter followed by the function you wish to use.

# Overflow & Underflow
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

# Casting 
Casting means to treat or convert a number from one type to another.
```
Byte myMinByte = Byte.MIN_VALUE;
byte myFirstByte = (myMinByte / 2);
```
The code above will give an Error: *incompatible types: int cannot be converted to java.lang.Byte*

This is because the default data type in Java is an Integer. The Java compiler does not attempt to evalute the value in the expression to make sure the value fits in the allowable range of a `Byte`. However, if the expression were to use literals. the `Java Compiler` would be able to evalue the value at compile time and figure out whether or not it fits into the `variable`. 

## There is a solution; casting:
```
Byte myMinByte = Byte.MIN_VALUE;
byte myFirstByte = (byte) (myMinByte / 2);
```
The output above will be -64. The statement works because we have told the compiler what data type we are using through casting. To do this, we simply state the data type prior to the expression we wish to utilize. This is common practice and not special to Java.

# Floating-Point Number Data Type
There are two floating point/ real world number data types; `Float`, and the more successful older brother, `Double`.


The `Float` is a 32-bit data type, the least precise of the two. The `Double` is a 64-bit data type. The most precise of the two as well as javas default floating point data type. This is for many reasons:

* The double is faster to process on modern computers
* Many java libraries have Double only math functions that will not process with a float
* Modern computers have copious amounts of RAM where the extra space for a double isn't an issue

`Precision` refers to the format and amount of space occupied by the relevant type.

To assign a `Float` to a declared float variable, the literal must be followed by a lowercase or uppercase `F` suffix. This is required in java. The same however, is not true with a `Double`, it is optional to follow a literal with a 'D'. With this and the above in mind. It is typically not wise to use flaot types java. It is far more common to use Double than Float.

**However** there is a class to use when absolute accuracy is required. `Big Decimal Class`. This class overcomes the limitations with how floating point numbers are stored. This is not a java problem specifically.

## Char Primitive Data Type
The `Char` primitive Data type is different than that of a string. The Char data type can only store one `'character'`. There are three different ways to call a `Char`.

* Literal Character = ***char myChar = 'D';***
* Unicode Value = ***char myChar = '\u0044'; = 'D'*** 
* Integer Value = ***char myChar = 68; = 'D'***

The Char occupies two bytes/ or 16 bits. Thus, has a width of 16. This is because each char value has a unicode value that it is assigned to. Java takes a lot of the tedious work when assigning a literal value. 

Adding two chars gives the reslt of the `deciaml values` found in the Unicode.
```
char myFirstChar = 'A'; // Decimal value of 65
char mySecondChar = 'B'; // Decimal value of 66

char myTotalChar = (char) (myFirstChar + mySecondChar) // equals 131
```

To concatenat a char, the expression must first `+` a `""` *(blank space). This will initialize a string and the letters being added to this blank string.

## Boolean Primitive Data Types
The `boolea`n pimitive type holds two values, True or False. Developers often use the word "is" as a prefix for the booolean variable name. This makes a name that seems to ask a question more intuitive to read.

Mostly used in conditional logic.

## String
A `String` is an `immutable` class (which is treated as an object in java) that contains a sequence/ or array of 'characters'. Immutable meaning, a string can't be changed after its been created. But (the fun part)! The refernce to the object can be changed. Every time a modifcaftion is made, a new instance of that string is create and the previous value is copied to the new `String` which the change.

The, `String Builder` class is mutable. Meaning it can be changed. However, it does not share the same special features as a String. Such as being able to assign it a string literal or use the '+' operator.

* To initialize, the `String` must start with a capital 'S'
* Concantonation: common practice with strings and occures with the '+' operator when assigning a string variable
* Unicode can be used in a string, simply use the unicode where you wish to place it and it will populate
* Can be used like a 9th primitive type, however it is not a data type but a class

The `+` operator means concatenation for strings.

## Operators , Operands, and Expressions

`Operators` are the special symbols that perform operations on one, two, or three operands and return a result. 
`Operands` is the term used to describe any object that is manipulated by an operator.
An `Expression` is formed by combining literals, method return values, and operators.

### Abbreviating Operators

The `Post-Fix Increment Operator` is a stand along statement & does not require an assignment. The `Compound Assignment Operator` is a stand alone statement that includes the assignment. This allows for a further tweaking to change how much the increment or decrement is.

Post-Fix Increment operator:
*`result ++;`*
Compound Assignment operator with `+` sign:
*`result += 1`*

Post-Fix Decrement operator:
*`result --;`*
Compound Assignment operator with `-` sign:
*`result -= 1`*

It is important to note the below when **understanding** `Compound Assignment Operators`.

```
x -= y; // how a compound assignment operator appears
x = (data type of x) (x-y) // what is really happening
```
There is this *implicit cast* happening with the data type of X to y. For example, if 'X' is an int and 'Y' was a fractional double. the result will omit all decimals givng an incorrect increment or decrement.

### Modulo
The `Modulo`, also known as the remainder operator; `%`

The modulo returns the remainder of a number through division. For example, it is very useful for creating an odd or even funciton.
```
10 % 2 = 0
11 % 2 = 1
25 % 3 = 1
76 % 18 = 4
```

## Proper Capitalization

The proper `Pascal Case` or `Cammel Case` is below:\

Upper Camel Case
* *Project Name*
* *Class Name*

Lower Camel Case
* *Mathod Name*
* *Variable Name*

## Access Modifiers

An Access modified allows us to define which parts of our code, or another persons code, can access a particular element.

### Public
The Public java keyword means the class, attribute, method or constructor is available to access from any class

### Private
The Private java keyword means it can only be accessed in 

## What is a Method
A method is a collection of one or more statemnts, that perform an action.

* `Void` means that the method will not return any information

The `Main Method` of a program is the entry point of a java program. A java program will search for the main method to begin executing.

The `Method Decleration` is a way to pass information to a method.

Below is a rough brake down of the class relationship with the method relation ship through our favorite program.

```
Class FirstClass                             // This is the Class 
{                                            // All the code inside these braces are defined as the class code block, or class body
  public static void main(String[] args)     // This is the main method of the Hello World program. The code inside the parenthases is also
                                             // known as the method decleration
  {                                          // All the code inside these braces are defined as the, 'Method Body'
  System.out.println("Hello World!");        // This is a statement that prints to the console, "Hello World!"
  }
}
```

# If-then Statement

The `if-then` statement is the most basic of control flow statements. It tells the program to execute a certain seciton of code only if the test evaluates to true, AKA `Conditional Logic`.

Conditional logic uses specific statments in java to allow us to check a condition. Based on the condition (the expression), execute certain code if it is true or false.

### Conditional Logic Operators

* Equality Operator: `==`
* Not Equal to: `!=` 
* Logical And Operator: `&&`
* Logical Or Operator: `||`

### The Not Operator and Its Counter Part
The `!` mark is the Not operator, also knows as the `logical complement operator`! The not operator can be used with any boolean variable to test for the inverse value. It does this by literally inversing the value of the given boolean.

```
boolean isCar = false;
if(!isCar) {
  System.out.println("The isCar variable is false");
} else {
  System.out.println("The isCar variable is true");
}
```
The code above is testing the boolean value for a false value. Since this statemnt is true, the system will print, "The isCar variable is false". The '!' operator inverses our boolean of **isCar**. This makes the value true whill will execeute our print line saying the value is false.

```
boolean isCar = false;
if(isCar) {
  System.out.println("The isCar variable is true");
} else {
  System.out.println("The isCar variable is false");
}
```
The code above is testing if the value in 'isCar' is true. The previous line is set to false so the if statement code block will not execute. As such, the else statement will then execute.

It is generally recommended to use the abreviated forms for the code is more concise and readable. Additionally, this can help prevent errors by accidentally using an assignment operator when testing booleans for true or false.

# Ternary Operator
The `Ternary Operator` has three operands. The only operator currently in java that deos have three. Java officially calls it the `conditional operator`. It is a shortcut to assigning one of two values to a variable, depending on a given condition. It is quite literally the `if-then-else` statement in shorthand.

Example One:

```
String makeOfMotorcycle = "Ducati";
boolean isDomestic = makeOfMotorcycle == "Ducati" ? false : true;
String s = (isDomestic) ? "This bike is domestic": "This bike is not domestic";
System.out.println(s);
```

The `Ternary Operator` is a way to replace an `if statement` if you want a value back based on a condition.

# The Method

Javas description of the method:

> A method decalres executable code that can be invoked, passing a fixed number of values as argumets.

* `Methods` is a way of reducing code duplication.

A method can be executed many times with potentially different results. By passing data to the method in the form of arguments/ parameters. Developers use the word arguments and parameters interchangably. **But** Technically, a parameter is the defination as shown in the method decleration, and the argiment will be the value that's passed to the method when we call it.
To execute a `method`, we can write a statemnt in code, which we is calling or invoking the method.

EX: 1
```
calculateScore(true, 800, levelCompleted, bonus ); // This is calling a method called calculateScore and passing the required information, in the required order
```

To execute a method that's defined with parameters, you have to pass variables, values, or expressions that match the type, order, and number of the parameters decalred in the method. A method that returns a value can be used as an expression or as part of any expression. Any method can be executed as a statement. 

`static` keyword means the method can be directly called using the calss name

A few declerations are required to create a `Method`. The order is as listed: (Declareing Modifiers), (Declaring Return Type), (Declaring the Method Name), & (Method Parameters).

## **Declaring Modifiers**

* `public`: The code is accessible for all classes
* `private`: The code is only accessible within the delcared class
* *`default`* The code is only accessible within the declared class. Used when a modifier isn't specified
* `protected`: The code is accessible in the same package and subclasses

## **Declaring Return Type**

`Void` = no value is returned

A `Primitive Data Type` can be used to return a value. However, the return statement is required for a value to be given. Otherwise, an error will occur. The `Return` statement can be used in clever ways, so think about reducing the code as much as possible for readability and compile time.

### **Declaring the Method Name**

The method name is what's used to call the method and should be lower camel case.

### **Method Parameters** 

The method parameters must be invoked in the same order and list as it comes with the same data type.

Some programming languages call a mehtod that returns a value, a `Function`! And, a method that doesnt return a value, a `Procedure`. Rarely used for Java but can occur. 

## Method Overloading

`Method Overloading` occurs when a **class** has multiple methods with the *same name*, BUT the methods are delcared with different **parameters**.

This allows multiple methods to have the 'same' name, but called with different *arguments*.

jave is able to resolve which method it needs to excecute based on the arguments being passed when the method is invoked!

### Valid overloaded methods

* The type, and number of parameters, in conjuction with the name, make a `Method Signature` unique.

* A unique method signature is the key for the `Java Compiler`, to determine if a method is overloaded correctly.

* The name of the parameter(s) is not part of this `unique signature`, and therefore it doesnt matter what they are called from java's point-of-view.

* `Return types` are also *NOT* used in determining if a method signature is unique.

### More on Method Signatures

A `Method Signature` consists of the name of the method, and the uniqueness of the declartion of its paramters.

A signature is unique, not just by the `method name`, but in combination with the `number of Parameters`, their `Data Types`, and the `order` in which they are declared.

* A methods retun type is not part of the signature.

* A parameter name is not part of the signature.

# Switch Statement

A `Switch Statement` is similar to an If-else-then statement. A switch statement will check a value and test it against a `case`. If the `case` is true, then it will execute the code block within and the `break` will terminate the switch statement. A `default` in a switch statement is executed if none of the cases are true. 

Example:

```
int switchValue = 3;

switch (switchValue) {
  case 1:
      System.out.println("Value was 1");
      break;
  case 2:
      System.out.println("Value was 2");
      break;
  case 3: case 4: case 5:
      System.out.println("Was a 3, a 4, or a 5");
      System.out.println("Actually it was a " + switchValue);
      break;
  default:
      System.out.println("Value was neither 1, 2, 3, 4 , or 5");
      break;
}
```

The code above highlights the basics of a switch statement and it's use. It is particurly useful when testing a fixed variable when there are many possible outcomes.

### Switch Case Value Data Types

The following are allowed Data Types (including their wrapper classes):

* byte
* short
* int
* char
* string
* enum

Not Allowed Data Types (including their wrapper classes):

* long
* double
* boolean

### Fall Through Switch Statment

A fall-through occurs when a case matches true, but there is no present break in that case. No more cases are checked after there is a match. As such, all code below the matched case will be executed until the switch statement is finished or until a break is encountered.

## Enhanced Switch Statement

The `enhanced switch statement` is the updated version of switch statements in the JDK environemnt. The enhanced switch statment is more versital and easier to read. However, when working with environmetns before java 14, a traditional switch statment must be used.

The `switch expression arrow` replaces the colon used in the older version of switch statments. The arrow token is also used in lambda expressions.

The `enhanced switch statment` does not require any breaks as fall-through can not occur.

See the example below:

```
  int switchValue = 3;

  switch (switchValue) {
      case 1 -> System.out.println("Value was 1");
      case 2 -> System.out.println("Value was 2");
      case 3, 4, 5 -> {
          System.out.println("Was a 3, a 4, or a 5");
          System.out.println("Actually it was a " + switchValue);
      }
      default -> System.out.println("Value was neither 1, 2, 3, 4 , or 5");
  }
```

### Yield in A Switch Statement

The key word `yield` was created specifically for enhanced switch statments because the term return does not work. 

**When to use a yield**

* The switch statement is being used as a switc hexpression returning a value

* The case label uses a code block with opening and closing curly braces.

See the example below showing the yield in a switch statement
```
public static String getQuarter(String month) {

    return switch (month) {
        case "January", "February", "March" -> { yield "1st"; }
        case "April", "May", "June" -> "2nd";
        case "July", "August", "September" -> "3rd";
        case "October", "Novemeber", "December" -> "4th";
        default -> {
            String badResponse = month + " is bad";
            yield badResponse;
        }
    };
}
```

# Looping

Looping allows us to execute the code a multiple number of times.

## Looping Tips

* `Continue` is a keyword to start a new iteration in a loop, it will jump to the expression of the loop and continue from there. 

* `Break` is a keyword that terminates the code block and steps outside the loop statement.

## For Statment (For Loop)

The `For Loop` is more complex to set up, but is commonly used when iterarting over a set of values. The For Loop continuely loops something until a condition is satisfied.

### Three Parts to the Basic `For Statement` Declaeration (All Parts are Optional)

The `Initialization`, `Expression`, and `Increment` 
```
// for (init; expression; increment) {
//    code block;
// }
```

* The `Initialization Section` declares or sets state, usually declaring and initializing a loop variable, before the loop begins processing.
* The `Expression Section`, once it becomes false, will end the loop processing.
* The `Increment Section` is executed after the expression is tested, and is generally the place where the loop variable is incremented.

```
  for (double rate = 2.0; rate <= 5.0; rate++) {
      double interestAmount = calculateInterest(10000,rate);
      System.out.println("$10,000.00 at "+ rate + "% interest = " + interestAmount);
  }
```

To use a `For statement` without any of the parts, there must be a `;` seperating the parts. 

IE:
```
      for (;i <= number;) {
        // code block
      }
      for (i = 5;;) {
        // code block
      }
      for (;;i++) {
        // code block
      }  
```

A break statment transfers control out of an enclosing statement, usually used in an `if-statement`
```
  for (double i = 7.5; i <= 10; i += .25) {
      double interestAmount = calculateInterest(100,i);
      if (interestAmount > 8.5){
          break;
      }
      System.out.println("$100.00 at "+ i + "% interest = " + interestAmount);
  }
```

## While Statement

The `While Loop` executes until a specified condition becomes false.

below is a `while loop`
```
while (expression) {
// code block
}
```

## Do While Statment

The `Do While Loop` always executes the code block once, regardless if the loop condition is true or false. Then, continues looping until the expression is false.

A useful example of a do while loop is asking for a users name & password. The code must execute fist, to see if it's true.

Below is a `do while loop`
```
do {
// code block
} while (expression);
```

# Java Debugger

[Debugger Info](https://www.jetbrains.com/help/idea/debugging-code.html)

# Local Variables and Scope

A local variable is called local because it is avaialble for use by the code block in which it was declared. It is also available to code blocks that are contained by a declaring block
```
{ // method code block
  int firstVariable = 5;

  if (firstVariable > 0) { // Flow statement block starts inner block
    // Inner block has access to outer blocks variables
    System.out.println(firstVarable);
  }
}
```

## Scope describes the accessibility of a variable.

`In scope` means the variable can be used by an executing block or any nested blocks. 

`Out of Scope` means the variable is not available and cannot be used.

Local variables are always out of scope for outer blokcs or the containing block they are declared in.

### Scope Best Practice

* To declare and initialize varaibles in the same place, if possible. And in a single statement
* To declare variables in the narrowest scope possible

# Objects 

An object is called an instance of a particular class. "Insance" can be used interchangably with "object".

An `Object` is created by instantiating a class and there are many ways to do this. The most common way to create an object is to use the *new* keyword.

The `new` keyword creates an instance of a class, and you can optionally pass data when creating that instance to set up data on that Object

Looking at the examples Below; String is a special non-primitive data type that is actually a Class, but holds a special place in the java language because we can create a String using a literal.
```
String s = "Hello!";

String s = new String("Hello!");
```

## Class is a template

The class is a template for creating objects! A class can be described as:

* A custome data type
* A special codeblock that contains methods

A class is like an emplty form, it describes information/ place holders for data that will be filled in when the form is given to an `object`.

Instantiating a class creates an object/ instance

The `Class` is the template for the data to be **collected**. This data that is collected each time is determined by the class.

## Static and Instance Fields

### Static Field

The `Static Field` requires the `Static` keyword when declared on the class. This means the value of that field always stays with that class. It's stored in a special memory location for values that aren't constantly changing. Unlike local variables & Objects.

In the *form analogy*, this would be a firld that is pre-populated on the form and would not change for any of the copied forms (objects). But unlike the form, this type of field in a class doesn't really get copied down to the object. It maintains its single value on the *master copy*, the class. This informaiton can be accessed by "Classname.fieldname"

EX:
```
Integer.MAX_VALUE 
```

### Instance Field

When the static keyword isn't used, it's called an `Instance Field`.

Until the class is instantiated and an object created, the instance field has no place in memory. The instance field can have different values for every instance/ object created.

This value is accessed using the variable name for the object and the dot notation used with the field name

Example:
```
myObject.myFieldName
// myObject is our variable name for an object we create
// and myFieldName is an attribute on the class
```

## Static and Instance Methods
The `Static` keyword is used to differentiate between these two types of methods

### Static Method

A `Static Method` can be called directing using the class name & dot notation. This type of method does not require an instance/ object to use this method. 

`ClassName.methodName`

Example:
```
Integer.parseInt("123");
```
A method called *parseInt* is called directly from the class, *Integer*.

### Instance Method

An `Instance Method` requires an instance to exist first & the method to be called on that instance. To use an instance method, an instance or object MUST be created first.

`ObjectValue.methodName`

Example:
```
"hello".toUpperCase();
```

A method called *toUpperCase* is called on the instance of a string with value *"hello"*. *"hello"* is really an `object` with type string.



# Parsing Data to Numberic Values

The below `Wrapper` and `Wrapper Methods` are the most commonly used.
 
* Integer | parseInt(String)
* Double  | parseDouble(String)


```
  String usersDateOfBirth = "1999";

  // static method called on the class Integer.
  int dateOfBirth = Integer.parseInt(usersDateOfBirth);
```
Integer is a class, not an object. On this class, there is a 'static' method called parseInt and it is being called on its class. This is only for a static Method. An Instance Method would require an object.


## Reading Data from the Console:

### System.in

Simialr to System.out, Java provides System.in which can read input from the console or terminal.

### System.console()

This is Java's solution for easier support for reading a single line and prompting the user for information. While easy to use, it does not work with IDE's because the environments disable the console.

### Command Line Arguments

This is calling the Java program and specifying data in the call. This is very commonly used but doesn't allow the creation of an interactive application in a loop in Java

### Scarnner

The Scanner class was built to be a common way to read input, either using System.in or a file. 

# New Key word

The new keyword is used in what Java calls a `Class Instance Creation Expression`.
```
ClassName variableName = new ClassName();
```
Can optionally pass arguments in the parentheses, similar to methods
```
ClassName variableName = new ClassName(argument1, argument2);
```

# The Scanner Class

The `Scanner` class is described as a simple text scanner, which can parse primitive types and strings. 

* To use the scanner class we have to create an *instance* of Scanner. This means to create an object of type `Scanner`.

### ClassName variableName = new ClassName(); 
IE.
```
Scanner scanner = new Scanner(System.in);
```

# Instantiating Scanner

For reading input from the console or terminal, we instatiate a scanner object using `new`, followed be the Scanner class name, and passing System.in, as an argument in the parentheses.

```
Scanner sc = new Scanner(System.in);
```

For reading input from a file, we instatiate a `Scanner` object using *new*, again with the Scanner class name, but pass a *file object*, as an argument in the parentheses.

```
Scanner sc = new Scanner(new File("nameOfFileOnFileSystem"));
```

It is Common practice to use a variable name which has the same name as the class
```
Scanner scanner = new Scanner(System.in);
```
The above statement creates a local Variable named scanner that can be used to execute instance methods on.
E.G
```
String name = scanner.nextLine();
```
The `nextLine` method is an `instance method` on scanner.




















