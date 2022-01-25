# Additional Style Guide (Parameter & Scanner)

## Table of Content

- [Unused Parameter](#unused-parameter)
- [Redundant Parameter](#redundant-parameter)
- [Declaration of Scanner](#declaration-of-scanner)
- [Parameter Comment](#parameter-comment)

---

## Unused Parameter

---

You should not declare a parameter if the value won't be used in the method

Take a look at the code below:

```java
public class Demo {
    public static void main(String[] args) {
        printNumber(1, 2, 3);
    }

    public static void printNumber(int firstNumber, int secondNumber, int randomNumber) {
        System.out.println(firstNumber);
        System.out.println(secondNumber);
    }
}
```

Notice how the value of randomNumber is not used in the printNumber method. The randomNumber parameter is considered unnecessary and should be removed.

---

## Redundant Parameter

---

Any parameter which value can be derived from another parameter, is considered unnecessary.

Take a look at the example below:

```java
public class Demo {
    public static void main(String[] args) {
        printTotal(1, 2, 3);
    }

    public static void printTotal(int firstNumber, int secondNumber, int total) {
        System.out.println(firstNumber);
        System.out.println(secondNumber);
        System.out.println(total);
    }
}
```

_Notice how the value of the parameter `int total` can be derived by adding the first parameter and the second parameter._

You do not need to send the value of `int total` from main, because you can do the following:

```java
public static void printTotal(int firstNumber, int secondNumber) {
        System.out.println(firstNumber);
        System.out.println(secondNumber);
        System.out.println(firstNumber + secondNumber);
    }
```

> In conclusion, you should strive to use as little amount of parameter as possible without compromising your program behavior and readability.

---

## Declaration of Scanner

---

You should declare your Scanner object **once in the main method**. If any method needs a Scanner, you should pass your Scanner from main to the corresponding method using parameters.

> You **SHOULD NOT** declare your Scanner in a method to avoid Java re-creating your Scanner over and over again each time your method is called because creating a Scanner is a costly operation (memory wise) in Java.

Here is a good example:

```java
import java.util.*;

public class Demo {
    public static void main(String[] args) {
        Scanner fromConsole = new Scanner(System.in);
        getUserInput(fromConsole);
    }

    public static void getUserInput(Scanner fromConsole) {
        System.out.print("Enter your name!");
        String name = fromConsole.nextLine();
        System.out.println("Your name is " + name);
    }
}
```

Here is an incorrect example:

```java
import java.util.*;

public class Demo {
    public static void main(String[] args) {
        getUserInput(fromConsole);
    }

    public static void getUserInput() {
        Scanner fromConsole = new Scanner(System.in);
        System.out.print("Enter your name!");
        String name = fromConsole.nextLine();
        System.out.println("Your name is " + name);
    }
}
```

Notice that the incorrect version creates the Scanner object outside of the main method instead of creating it inside the main method and passing it as a parameter.

---

## Parameter Comment

---

Parameter comment consists of two elements:

1. Mentioning each of your parameter name
2. Describing each of your parameter

> Parameter comment is only required for any method that uses at least 1 parameter.

**Example:**

```java
    // Prints a sequence of text multiple times
    // Parameters:
    // int number - pass the amount of times the text will be printed
    // String text - pass the text to be printed multiple times
    public static void printSomething(int number, String text) {
        for (int i = 1; i <= 4; i++) {
            System.out.println("hello");
        }
    }
```

**If you are using _Javadoc_ notation:**

```java
    /**
     * Prints a sequence of text multiple times
     *
     * @param number - pass the amount of times the text will be printed
     * @param text   - pass the text to be printed multiple times
     */
    public static void printSomething(int number, String text) {
        for (int i = 1; i <= 4; i++) {
            System.out.println("hello");
        }
    }
```
