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

## More on the String

The String has over 60 methods

The String methods can be split into three basic categories

* `String Inspection Methods` (like length, etc.)
* `Methods for Comparing String Values` (usually return a boolean value)
* `String Manipulation Methods`

### String Inspection Methods

`Length` = Returns the length, in number of characters, of a specified string. The length is returned excluding any trailing blank characters.

`charAt` = Returns the char value at the specified index.

`indexOf` = Returns the index within this string of the first occurrence of the specified character.

`lastIndexOf` = Returns the index within this string of the last occurrence of the specified character.

`isEmpty` = Returns true if, and only if, length() is 0.

`isBlank` = Returns true if the string is empty or contains only white space codepoints, otherwise false.

### String Methods for comparing Values 

`contentEquals` = Compares this string to the specified CharSequence.

`equals` = Compares this string to the specified object.

`eaualsIgnoreCase` = Compares this String to another String, ignoring case considerations.

`contains` = Returns true if and only if this string contains the specified sequence of char values.

`endsWith` = Tests if this string ends with the specified suffix.

`starts with` = Tests if this string starts with the specified prefix.

`regionMatchs` = Tests if two string regions are equal.

### String Methods for Manipulation

This first set of methods don't actually change the underlying meaning of the text value, but perform some kind of clean up.

`indent` = Adjusts the indentation of each line of this string based on the value of n, and normalizes line termination characters.

`strip` = Returns a string whose value is this string, with all leading and trailing white space removed

`stripLeading` = Returns a string whose value is this string, with all leading white space removed

`stripTrailing` = Returns a string whose value is this string, with all trailing white space removed

`trim` = Returns a string whose value is this string, with all leading and trailing space removed, where space is defined as any character whose codepoint is less than or equal to 'U+0020' (the space character)

`toLowerCase` = Converts all of the characters in this String to lower case using the rules of the default locale

`toUpperCase` = Converts all of the characters in this String to upper case using the rules of the default locale

This second set of `String Manipulation` methods transforms the string value and returns a string with a different meaning than the original String.

`concat` = Concatenates the specified string to the end of this string

`join` = Returns a new String composed of copies of the CharSequence elements joined together with a copy of the specified delimiter

```
join(CharSequence delimiter, CharSequence... elements)
```

`repeat` = Returns a string whose value is the concatenation of this string repeated count times

`replace` = Replaces each substring of this string that matches the literal target sequence with the specified literal replacement sequence

`replaceAll` = Replaces each substring of this string that matches the given regular expression with the given replacement.

`replaceFirst` = Replaces the first substring of this string that matches the given regular expression with the given replacement*

`subString` = Returns a string that is a substring of this string

```
substring(int beginIndex, int endIndex)
```

`subSequence` = Returns a character sequence that is a subsequence of this sequence

```
subSequence(int beginIndex, int endIndex)
```

## Escape Sequences

`\t` = Insert a tab character

`\n` = omsert a new line character

`\"` = Insert a double quote character

`\/` = Inset a backslash character

`%d` = used for a decimal interger value 

`%f` = used for a decimal number 

## String vs String Builder

Because String is *immutable*, each method call returns a new instance of a string. Java provides a mutable calss that lets us change its text value, the String Builder Class!!!

```
StringBuilder emptyStart = new StringBuilder();
emptyStart.append("a".repeat(57));
StringBuilder emptyStart32 = new StringBuilder(32);
emptyStart32.append("a".repeat(17));
```

The `string builder` has 4 overloaded constructors:

* pass a String
* pass no arguments at all
* pass an integer value (this is the capacity value)
* pass some other type of character sequence (like string builder

String methods create a new object in `memory` and return a reference to this new object. `StringBuilder` methods return a StringBuilder reference, but it's really a self-reference.

A StringBuilder is `mutable`, which means it can grow or shrink in size. By default, an empty StringBuilder starts out with a capacity of 16. Meaning, it can contain up to 16 characters before it needs to *request more memory*.

Evertime a SttringBuilder needs to increase capacity, the data stored in the *original storage* needs to get copied over to the *larger storage* area. The new allocation size is determined by the JVM.

If a lot of text is **intended** for a StringBuilder object, it's recommended to start with a larger capacity.

The `StringBuilder` has many similar methods to Strings, but it also has methods to btoh *remove* and *insert* Characters or Strings. In addation, you can truncate the StringBuilder's size.

`delete` = Removes the characters in a substring of this sequence

```
delete(int start, int end)
```

`deleteCharAt` = Removes the char at the specified position in this sequence

`insert` = Inserts the string into this character sequence

`reverse` = Causes this character sequence to be replaced by the reverse of the sequence

`setLength` = Sets the length of the character sequence

## Format Specifiers

Format specifiers take the form shown here
```
%[argument_index$][flags][width][.precision]conversion
```

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

### Scanner

The `Scanner Class` was built to be a common way to read input, either using System.in or a file. 

# Using Import Statement

The Import Statement allows us to use classes from other peoples code

Java provides a library of code, which includes the `Scanner` class in a library called java.util.
```
import java.util.Scanner;
```

# New Key Word

The new keyword is used in what Java calls a `Class Instance Creation Expression`. The New keyword is used to create a new instance of a class! When we use new, it allocates a memory for a new object in the heap and returns a reference to that memory. This is essential for the managment of dynamic memory in Java.
```
ClassName variableName = new ClassName();
```
Can optionally pass arguments in the parentheses, similar to methods.
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

It is Common practice to use a variable name which has the same name as the class.
```
Scanner scanner = new Scanner(System.in);
```
The above statement creates a local Variable named scanner that can be used to execute instance methods on.
E.G
```
String name = scanner.nextLine();
```
The `nextLine` method is an `instance method` on scanner.

# What's an Exceptionn?

An exception is an error that happens in code. Some types of errors can be predicted and named. An exception is caught first by creating a code block around the code that gets the error. This is done with the `Try Statement` code block.

### The Try Statement

The Try Statement has two code blocks.

```
try {
  // statements that might get errors
} catch (Exception e) {
  // code to react or handle the error
}
```
The catch keyword includes the decleration of variables in parentheses, and then has it's own code block.

The `Decleration` includes the type of the exception and a variable name.

# Object Oriented Programming

## What is OOP?

Object-Oriented Programming is a way to model real-world objects as software objects which contain both data and code. Sometimes OOP is called class-based programming

### Class-Based programming

Class-based programming starts with classes which become the blueprints for objects. But what even is an `Object`?

Real world objects have two major compnents: ***State*** & ***Behavior***. Below are a few examples highlighting these.

State in terms of a Computer object:
-
* Amount of RAM
* Operating System
* HDD or SSD size
* Size of the monitor

These are characteristics about the item that can describe it.

State for a person (animate objects)
-
* The age
* The number of fingers
* The conscious state
* Wheather they are awake or sleeping

In addition to state, objects may also have behavior or actions that can be *performed* by the object, or upon the object.

Behavior for a computer:
-
* Booting up
* Shutting down
* Outputting a sound
* Drawing something on screen

All can be described as behaviors for a computer.

Behavior for a person:
-
* Eating
* Talking
* Fighting
* Walking

## State & Behaviour

Modelling real-world objects as software objects is a fundamental part of `OOP`.

A software object stores its state in `Fields`, which can also be called `Attributes` (or variables). Objects expose their `Behavior` with methods. Then, the `Class` fits in as a template or a blueprint for creating `Objects`.

## The Class as A Blueprint

The class describes the data *(AKA fields)*, and the behavior *(AKA methods)*, that are relevant to the real-world object we want to describe.

These are called `Class Members`!

A `Class Member` can be a field or a method, or some other type of dependent element. 

If a field is `Static`, there is only one copy in memory, and the value is associated with the class or template itself. In 

If a field is not static, its called an `Instance Field`, and each object may have a different value stored for this field.

A `Static Method` **CAN'T** be *dependent* on any one `Objects` state, so it **CAN'T** reference **ANY** `Instance Members`.

In other words-
-
Any method that operates on `Instance Fields` needs to be non-static. The `Class` or `Member Fields` must be non-static. These class or member fields can be thought of as variables, but are called `Fields` or `Attributes`.

## Organizing Classes

Classes can be organized into logical groupings called packages.

You declare a `Package Name` in the class using the `Package Statement`. if a package is *NOT* declared, the class *implicitly* belongs to the `default package`.

### So what does this mean?

The Bottom line is that `Classes` are grouped into `Packages`. This is necessary to understand in order to understand `Access Modifiers`.

## Access Modifiers for the Class

A `Class` is said to be a `top-level` class if it is defined in the source code file and not enclosed in the code block of another class, type, or method.

A `Top-Level Class` has only two valid access modifiers options: `Public` or `"nothing/ null"`

### Public
Public means any other class in any package can access this class.

### "nothing"
Null: When the modifier is omitted. This has a special meaning, called `Package Access`. This means that the class is accessible *only* to classes in the same `Package`. Java, by default, implicitly allows package-private access. Essentially, this means that classes grouped into the same package can access the class.

## Access Modifiers for Class Members
An access modifier at the member level allows granular control over class members.

The valid access modifiers below are from least restrictive to most restrictive:

### Public
This means there is unrestricted access to the member.

### Protected 
Protected allows classes in the same package, and any subclasses in other packages to access this member

### NULL
When there is no modifier, this means package or package-private by default. So that any class in the same package can access this member.

### Private
Private means that no class/ code can use this field or method. The general rule is to make all fields private. This is because of `Encapsulation`.

## Encapsulation

`Encapsulation` in Object Orientated Programming has two meanings.

* One is the bundling of `Behavior` and `Attributes` on a single object
* The other is the practice of *hiding* fields and some methods from public access

When we make our *attributes* `private`, we can then create methods to access the data. Each with different degrees of access allowed as needed.

The whole reason behind Encapsulation is not allowing people to access fields directly. We force them to go through a controlled way of setting up the data on the object. Using the setter method, we can make sure the data in our objects is valid data.

* Fields are defined in the classes code block/ body of the class and not in a method.

When an `object` is created from a `class`, the values are then assiged to these `private fields` which represent the `state` of the object.

Unlike local variables, class variables should have some type of access modifier declared for it. If one is not declared, java declares the default, `Package Private`, implicitly.

A `protected` access modifier on a super class is conditional encapsulation. It allows all subclasses and any classes in the same package to have access to this internal field.

### Default Values for Fields on Classes

* Fields on classes are assigned default values automatically by Java if they aren't assigned values.

* Boolean = false
* byte, short, int, long, char = 0
* double, float = 0.0
* Any other type will be null


## Getters and Setters

A `getter` is a method on a class that retrieves the value of a *private* field and returns it.

```
private String model;
public String getModel() {
    return model;
}
```

A `setter` is a method on a class that sets the value of a private field. 

```
public void setModel(String model){
  this.model = model;
}
```

* The purpose of theses methods is to control and protect access to private fields

An important aspect is that the `getter` and `setter` method signatures are a part of the `classes interface`, but the *field names* and *types* aren't.

This means we can change things interally like the name or type of a field. As long as we use the same getter and setter method, these changes shouldn't affect external code that uses our class.

Getter
-
A getter method usually just returns the value of a `private` field. There can be getter methods for fields that are not really declared on the class, but that are derived in someway.

Setter
-
A setter method may simply just assign the argument passed to the method, then, to the field. But, it can also contain code to **validate data**, **check additional security requirements**, **ensure immutability of the field value**, or any **other code required to protect and validate an objects state**.

What you can do with a setter method is set up all the rules related to that class, what is valid, and what is not valid. This functionality can be set up within the class itself, so that any rules are in place when *instantiating an Object`

## This

`'this'` is a special keyword in java. What this really refers to is the *instance* that was created when the object was instatiated. So, `'this'` is a special reference name for the object or instance, which it can use to describe itself! We can then use `'this'` to access fields on the class.

EG.
```
private String make;

public void setMake(String make){
  this.make = make; // Tells java it wants to update the field 'private String make'
                    // with the contents of the parameter `make` that was passed to the method
}
```

# Constructer

* A `Constructor` is used in the creation of an objcet! This is a special type of code block that has a specific name and parameters, much like a method.

## Rules of A Constructor 

A `Constructor` has the same name as the *class* itself, and it doesnt return any values but has an access modifier. There is never a return type from a constructor, not even void.

There can, and should be an appropriately specified access modfier that controls who should be able to create new instances of the class, using *this* `constructor`.
```
public Class Account { // Class decleration
  public Account () { // Constructor decleration
    // Constructor code is code to be executed as the object is created
  }
}
```

## What Does A Constructor Do?

Essentially, a constructor sets the values of the fields in an instance of a class. In addition, there can also be other initialization code to be performered in the constructor.

* A constructor is implicitly created in Java

When a new object is initialized using the new keyword, *= new Account();*. This calls that implicit constructor. This is called the default constructor (or no args constructor).

### More on the Constructor

When a new object/ instance is created, this is Javas cue to call the constructor. The purpose of the constructor is to initialize the object that we're creating and do anything else while the object is being instatiated.

* A constructor is only called once at the beginning/ creation of an object
* A Class can have one or many constructors

## Default Constructor

If a class contains no constructor declerations, then a default constructor is implicitly declared. This constructor has no parameters and is often called the no-args constructor.

If a class contains any other constructor declerations, then a default constructor is not declared.

A constructor exists whether on is explicitly decalred or not. This is why creating a new object with the *'new'* keyword and passing no arguments is supported in almost all cases.

## Constructor Overloading

Constructor overloading is declaring multiple constructors with different parameters. The number of parameters can be different between constructors. Or, if the number of parameters is the same between two constructors, their types or order of types must differ.

## Constructor Chaining With this()

`Constructor Chaining` is when one contructor expliciitly ca;;s another overloaded constructor. Constructor Chaining only works within constructors, hence the name! The special statement `this(//arg1, arg2, etc.)` must be used to execute another constructor, passing arguments if required. Additionally `this()` must be the FIRST executable statment if it's used from another constructor.
```
public Customer () {
    this("Person", "person@emailaddress.com");
}
```
## Additional info on Constructors

Generally it's always better to assign the values directly to the field, rather than calling the setting in a constructor. There scenarios where these calls to setter methods for validation code or another functionality, may not work. Such as inheritance and creating subclasses.

* General rule with constructos is don't call any other method other than another constructor with those constructors

# What is a Reference?
A reference is a variable name that points to the memory location of an object!

We can pass references as parameters to constructors and methods.

A referemce points to an object in memory. If there are many references to the same object, changing one changes all.
```
House blueHouse = new House("blue");
house anotherHouse = blueHouse;
```

There's no way to access an object directly, everything is done using that reference. A reference (the variable the object is assigned to) allows ut ohave access to the object.

# More on Static and Instance Variables & Methods

## Static Variables

A static variable is declared by using the keyword static

* Static variables are also known as `static member variables`

Every instance of a class, shares the *SAME* static variable. If changes are made to that variables, all other instances of that calss will see the effect of that change.

It is considered best practice to use the class name and not a reference varaible to access a static variable. This makes it clearer that the variable is assocaited with the class and therefore, not stored with the instance.

An instance isn't required to exist to access the value of a static variable. Static variables aren't used very often, but can sometimes be very useful. \

They can be used for:
* Storing Counters
* Generating unique IDs
* Storing a constant value that doesn't change, like PI
* Creating and controlling access to a shared resource (a log file, database, or a different type of input or output stream).

## Instance Variables

Instance variables don't use the static keyword when defining them. They are also known as Fields or member variables.

Instance variables belong to a specific instance of a class, unlike a static variable.

Every instance has its own copy of an instance variable. Every instance can also have a different value. Instance variables represent the state of a specific instance of a class.

## Static Methods

`Static methods` are declared using a static modifier. Static methods can't access instance methods and instant variables directly. 

They're usually used for operations that don't require any data from an instance of the class (from *this.*). The this keyword is the current instance of a class.

Inside a static method, we can't use the *this* keyword.

Whenever there is a method that doesn't use instance variables, that method should likely be declared as a static method. For example, main is a static method and it's called by the Java Cirtual Machine (JVM), when it starts the Java application.

* Static methods are called as, *ClassName.methodName();* or/ *methodName();* (However, this is only if the static method is in the same class)

## Instance Methods

Instance methods belong to a specific instance of a class. To use an instance method, the class must first be instantiated, usually by using the 'new' keyword.

* `Instance Methods` can access instance methods and instance variables direclty

* Instance methods can *ALSO* access static methods and static variables directly

Directly means we do not have to use the keyword `this` with dot notation to use them. And, we don't have to use the class name with dot notation to access static variables or methods, if the static variable or method is in the same class.

## How to determine if a method should be static?

Does the method use any fields?

* `YES:` It should likely be an instance method.
* `NO:` It should likely be a static method.

# Plain Old Java Object (POJO)

A `Plain Old Java Object (POJO)` is a class that generally only has instance fields. It's used to house data and pass data between functional classes. Usually, it has no other, or very few methods other than geteters and setters for the instance fields.

Many database frameworks use POJO's to read data from, or to write data to data bases, files, or streams.

* A `POJO` may also be called a `bean` or `Java bean`

A `Java Bean` is just a POJO with a few extra rules applied to it. There rules are in place so that `Java framworks` have a standard way to manipulate and manage these objects.

A POJO is somtimes call an `entity` because it mirrors database entities.

Another acronym is `DTO` for `Data Transfer Object`. It's a description of an object that can be modeled as just data.

## Annotation

`Annotations` are a type of `metadata`. Metadata is a way to formally describe additional information about our code. Annotations are more structed with more meaning than comments. This is because they can be used by compiler or other types of pre-processing functions to get information about the code.

* Metadata doesn't affect how the code runs.

## Overridden Method

An overridden method is not the same as an overloaded method.

An overridden method is a special method in java that other classes can implement if they use a specified method signature. Similar to how we create the main method, we have to create the `toString` method a certain way.

* Every object passed to `println` will have the `toString` method implicitly executed if the method has been created on the class.

# The Record Type

The purpose of the `Record type` is to replace boilerplate code of the `POJO` but to be more restrictive. Java calls them, "Plain data carriers." 

* Boilerplate code is the code that is repetative and follows certain rules

The record is a special class that contains data that's not meant to be altered. In other words, it seeks to achieve immutability for the data in its members. It contains only the most fundamental methods, such as `constructors` and `accessors`.

* The devloper doesn't have to write or generate any of this code

## Implicit or Generated Code that Java Provides

```
public record LPAStudent(String id, String name, String dateOfBirth, String classList) {
}
```

The arguments passed to the record above is called the `record header`. The record header consists of record components, a comma-deliminated list of components.

For each component in the header, java generates

* A field with the same name and declared type as the record component
* The field is declared `private` and `final`
* The field is sometimes referred to as a component field

Java generates a `toString` method that prints out each attribute in a formatted string.

EG.
```
public String toString() {
    return "Student{" +
            "id='" + id + '\'' +
            ", name='" + name + '\'' +
            ", dateOfBirth='" + dateOfBirth + '\'' +
            ", classList='" + classList + '\'' +
            '}';
}
```

In addition to *creating* a `private final field` for each component, java generates a `public accessor method` for each component. This method has the same name and type of the component, but it doesn't have any kind of special prefix like *get* or *is*, for example. To call information from a record, simply use dot notation on the object and call the field name.

There's no way to set any information or value in a record other than passing the value in on the record header or through the use of constructors. This is by design because the records goal is to be `immutable`.

### Why have an Immutable Record?

There are more use cases for immutable data transfer objects and keeping them well encapsulated. We want to protect the data from unintended mutations.

## POJO vs Record

If we want to modify data on our class, we won't be using the `record`. 

However, if theres a lot of records from a database or file source and we're simply passing this data around, then the record would be a large improvement over the boilercode found in the POJO.


## Inheritance

What is `Inhertance` and why is it so powerful? Inheritance can be viewed as a form of `code reuse`. It's a way to organize classes into a  parent-child hierchy, which lets the child `inherit` (reuse) fields and methods from it's parent. A parent class can have multiple children classes. A child class can only have *ONE* direct parent in Java. The most generic/ base class starts at the top of the hierchy. Every class below is a `Subclass`.

### Extends

Using the `Extends` keyword specifies the `Superclass` of the class we're declaring. 

* A class can specify one and only one class in it's extends clause

### Super()

`super()` is very similar to `this()`. It's a way to chain a constructor on the `Superclass` directly from the Subclasses constructor. 

Like *this()*, it has to be the first statement of the constructor. Because of this rule, *this()* and *super()* can never be called from the same constructor.

If you don't make a call to *super()*, then Java makes it for you using the Superclasses default constructor. If the superclass DOESN'T have a default constructor, then you must explicitly call *super()* in all of your constructos, passing the right arguments to that constructor.

## A Class Diagram

* A class diagram allows us to design our calsses before we build them. This makes designing `Superclasses` and `Subclasses` much easier.

## Code Reuse

All subclasses can execute methods even though the code is decalred on the parent class. The code doesn't have to be duplicated in each subclass.

We can use code from the parent. Or, we can change that code for the subclass. This is known as overriding a method.

### Overriding a Method 

`Overriding a method` is when you create a method on a subclass which has the SAME *signature* as a method on a superclass. You override a parent class method when you want the *child class* to show a different behavior for that method.

The overridden method can do one of the three things:
* It can implement completely different behavior, overriding the behavior of the parent
* It can simply call the parent classes method (Which is redundent as this is the default)
* Or, the method can call the parent classes method and include other code to run so it can extend the functionality for that behavior

## Polymorphism

Polymorphism simply means "Many Forms".

Some advantages of Polymorphism are:
* It makes code simpler
* It encourages code extensibility

# java.lang.Object

Every class in java extends a special java class names: `Object`. It's located in the java.lang package.

* Class object is the root of the `calss hierarchy`

Every Class has object as a superclass. All objects, inblcuding `Arrays`, implement the methods of this class. A has code is created everytime an instance is created.

# this() vs super()

The keyword `super` is used to access or call the parent class members (both variables and methods)

The jeyword `this` is used to call the current class members (both variables and methods)

`this` is required when we have a parameter with the same name as an instance variable or field

```
public Rectangle(int x, int y) {
this.x = x;
this.y = y;
}
```

Note: We can use either of these two keywords ANYWHERE in a class EXCEPT for static elements such as a static method. Any attempt to do so will lead to compile time errors.

The keyword `this` is commonly used within constructos and setters and is optionally used within getters.

The keyword `super` is commonly used with method overriding when we call a method with the same name from the parent class.

## this() vs super() call

In Java there is the `this()` and `super()` calls.

There are known as calls since they look like regular method calls although we're calling certain constructors.

use `this()` to call a constructor from another overloaded contructor in the same class.

the call to `this()` can only be used in a conTructor, and it must be the FIRST STATEMENT in a constructor. It is used with `constructor chaining`, in other words, when one constructor calls another constructor. This helps to reduce code.

The only way to call a parent constructor is by calling `super()`, which calls the parent constructor and again, this must be the FIRST call.

Constructor chaining makes sure the last constructor has the responsibility to initialize the variables. Ultimately, we end up in the final constructor. The other constructors call eachother. Constructor chaining can, and does avoid code duplication.
```
// Class Worker
public Worker(String name, String birthDate){
    this.name = name;
    this.birthDate = birthDate;
}

// Class Employee
public Employee(String name, String birthDate, String hireDate) {
    super(name, birthDate);
    this.employeeId = Employee.employeeNo++; // Post increment number
    this.hireDate = hireDate;
}

// Class SalariedEmployee
public SalariedEmployee(String name, String birthDate, String hireDate, Double annualSalary) {
    super(name, birthDate, hireDate);
    this.annualSalary = annualSalary;
}

```

# Method Overloading vs Overriding

`Method Overloading` means providing two or more seperate methods in a class with the same name but different parameters.

```
public static crossWalk(int timeOut) {
// method body
}

public static crosswalk(int timeOut, string direction) {
// method body
}
```

### Overloading is very handy, it recued duplicated code, and there is no need to remember multiple method names.

`Static` or `Instance methods`, can be overloaded.

`Method overloading` provides *functionality* to reuse a method name with different parameters. To the code calling an overloaded method, it looks like a single method can be called with different sets of arguments. In actuality, each call that's made with a different set of arguments is calling a seperate method.

Java developers often refer to method overloading as `Compile-Time Polymorphism`. This means the compiler is determining the right method to call, based on the method name and argument list.

Usually, `method overloading` happens within a single class, but methods can also be overloaded by `subclasses`. That's because a subclass *inherits* one version of the method from the parent class and the subclasss can have another overloaded version of that method.

## Method Overriding

`Method Overriding`, means defning a method in a child class that already exists in the parent calss with the SAME *signature*. This means, they share the same **name** and **parameters**.

By extending the parent class, the chald class gets all the methods defined in the parent class. Those methods are also known as `Derived Methods`

Method overriding is also knwon as `Runtime Polymorphism` or `Dynamic method dispatch` because the method that is going to be called is decided at runtime by the `JVM`.

Static methods CAN't be overrided, only instance methods.

In short, `Method overriding` is used to override a behavior which the class has `inherited` from the parent class.

## Method Override Rules

A method will be considered overriden following these rules.
* It must have the same name and arguments
* The return type can be a subclass of the return type in the parent class.
* It can't have a lower access modifier, meaning, it can't have a more restrictive access privilege

**Only** *inherited* methods can be overridden. This means that we can only override a method in a subclass/ child class.

* Constructors and private methods cannot be overridden
* Methods that are final can not be overridden
* A subclass can use `super.methodName()` to call the superclass version of an overridden method

## Covariant Return Type

The return type of an overridden method can be the same type as the parent method'd decleration. But, it can also be a subclass.

In general when cloning an instance, we want to return an object thats the same type as the object that is being cloned.

I.E:

All classes, ultimately have object as a base class, so every class can be said to be a `covvariant` of Object.

# String Comparison methods












