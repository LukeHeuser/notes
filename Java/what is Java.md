# What is Java?
* Java is a simple and secure, `OOP` programming language.
* Because of it's `Archetecturally Neutral` behavaior, it has no implemntation dependent features. In other words, the programme doesn't compile into machine code native to the OS.
* Robust and Secure:
    * Everything is `Sandboxed`

## Java Compiler
`Compile Time Checking`: `Source Code` is taken and turned into `Bytecode` that the `Java Virtual Machine (JVM)` can understand.

The Compiler parses the entire source code. First, searching for syntax and other errors. If found, errors will be displayed. If no errors are found, this `Source Code` will be converted into the `Machine Code` that will be executed.

* The Compiler bgins by searching for syntax errors
* This also serves as Javas error detection system
* This is what allows Java to be executed on any OS

## Java Interpreter
The `java Interpreter` examines and executes the `Source Code` line-by-line rather than first parsing like the `Java Compiler`. If an error is found, it is highlighted and the code is halted until it is fixed. Once fixed, the interpreter continues to execute.

The **main difference** between the `Java Compiler` and `Java Interpreter` is the interpreter analyzes and executes code line-by-line. Where as the compiler will analyze the entire source code and then list all errors until they are fixed.

For this reason, the `Interpreter` is **quicker** to analyze `source code`, `debug errors`, and the execution is line-by-line.

## Java API

