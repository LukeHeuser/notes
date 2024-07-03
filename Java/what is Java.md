# What is Java?
* Java is a simple and secure, `OOP` programming language.
* Because of it's `Archetecturally Neutral` behavaior, it has no implemntation dependent features. In other words, the program doesn't compile into machine code native to the OS.
* Robust and Secure:
    * Everything is `Sandboxed`

## Java Compiler
`Compile Time Checking`: `Source Code` is taken and turned into `Bytecode` that the `Java Virtual Machine (JVM)` can understand.

The Compiler parses the entire source code. First, searching for syntax and other errors. If found, errors will be displayed. If no errors are found, this `Source Code` will be converted into the `Machine Code` that will be executed.

* The Compiler bgins by searching for syntax errors
* This also serves as Javas error detection system
* This is what allows Java to be executed on any OS

### Just-In-Time (JIT) Compiler
The JIT compiler compiles bytecode into native machine code can be executed directly by the CPU.

## Java Interpreter
The `java Interpreter` examines and executes the `Source Code` line-by-line rather than first parsing like the `Java Compiler`. If an error is found, it is highlighted and the code is halted until it is fixed. Once fixed, the interpreter continues to execute.

The **main difference** between the `Java Compiler` and `Java Interpreter` is the interpreter analyzes and executes code line-by-line. Where as the compiler will analyze the entire source code and then list all errors until they are fixed. Once fixed, the source code will be compiled into bytecode and interpreted by the JVM into Machine Code. Which gets ran by the hardware/ OS. 

For this reason, the `Interpreter` is **quicker** to analyze `source code`, `debug errors`, and the execution happens line-by-line. However, it is slower to run a program comparatively.

## Java Virtual Machine

the `Java Virtual Machine (JVM)` is what allows Java to run on any plateform and secures complete independence. As stated above, The JVM takes bytecode and interprets it into Machine Code which in turn gets executed by the hardware/ OS. 

### JVM Advantages
* Plateform-Indepence for executing Java code
* Performs bytecode verfication ensuring safety and security of Java programs
* Enables automatic memory management through the use of a garbage collector
* Supports dynamic class loading, allowing new classes to be loaded at runtime

## Java API
The `Java Application Programming Interface (API)` is integrated in the JDK and offers a connection interface between different Java classes and user interfaces. The java API explains the function of each class or interface. 

Developers are the primary users of Java API's. 

**Five types of Java API's**
* "Open' Java API
* Private Java API
* Partner Java API
* Composite Java API
* Web Java API

## Java Runtime Environemnt (JRE)

The `JRE` is a software environemnt in which te Java program is executed. Below is a digram referencing the above and how it fits in the execution.

![Alt Text](https://www.scientecheasy.com/wp-content/uploads/2021/03/java-runtime-environment-1.png "A title")
