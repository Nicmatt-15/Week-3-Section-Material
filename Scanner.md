# Scanner

## Table of Content

---

- [What is a Scanner?](#what-is-a-scanner)
- [How to use a Scanner?](#how-to-use-a-scanner)

---

## What is a Scanner?

---

Scanner is an object / tool in java that allows your program to take in user input from the console.

> The term "console" refers to the place where Java prints the output of your code.

---

## How to use a Scanner?

---

Here are the steps on how to use Scanner in Java:

1. You have to import them, to let Java know that you want to use them. To achieve this, you should write the following line **above your class header**:

   ```java
   import java.util.*;
   ```

2. You have to declare Scanner like any other variable before you can use it. To do that, you should write the following code **in the main method** (_for style purpose_):

   ```java
   Scanner yourScannerNameHere = new Scanner(System.in);
   ```

3. You can use Scanner to take-in user input using the following template:

   ```java
   yourScannerName.methodName();
   ```

   For example:

   ```
   Scanner fromConsole = new Scanner(System.in);
   fromConsole.nexLine();
   ```

   There are several Scanner method that you can use with different purposes. Here are a list of the common ones:

   - > `.next()` is used to take **one word** from a text. If a number is given, it will take the number and treat it as a String.
   - > `.nextLine()` is used to take **one line** from a text. If a number is given, it will take the number and treat it as a String.
   - > `.nextInt()` is used to take a whole number.
   - > `.nextDouble()` is used to take a decimal number.

4. When you take in a user input, make sure to save them into a variable to avoid the user-input being lost. This also allows you to use the user-input for other purposes.

   Take a look at the example below:

   ```java
   Scanner fromConsole = new Scanner(System.in);
   System.out.print("Input your name!");
   String name = fromConsole.nextLine();
   System.out.println("Your name is: " + name);
   ```

   Notice that the user-input that my program takes in using `fromConsole.nextLine()` is saved in a String variable so that it is not lost and the program can use the user input in the following line.
