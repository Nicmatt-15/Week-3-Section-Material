# Parameter

## Table of Content

---

- [Basic of Parameter](#basic-of-parameter)
- [Parameter - Value vs Variable](#parameter---value-vs-variable)
- [Multiple Parameters](#multiple-parameters)

---

## Basic of Parameter

---

Take a look at the code below:

```java
public class Demo {
    public static void main(String[] args) {
        int myNumber = 4;
        printNumber();
    }

    public static void printNumber() {
        System.out.println(myNumber);
    }
}
```

If we run the code above, we will get the following error:

```
Demo.java:8: error: cannot find symbol
        System.out.println(myNumber);

  symbol:   variable myNumber
  location: class Demo
error
```

**Why are we getting a `Cannot find symbol` error?**

The reason is because the `printNumber()` method does not have access to the variable `myNumber` declared in the main method.

The variable `myNumber` is declared as a direct child of the main method. As a result, the scope of the `myNumber` variable is only in the main method. In other words, the `myNumber` variable only exists in the main method.

---

Parameter can help resolve the issue above by sending **the value** of `myNumber` (_not the variable itself_) to the `printNumber()` method.

Using parameter involves two steps:

1. Sending the value when you call the method.

   To do this, we can modify the method call to `printNumber()` as follow:

   ```java
   printNumber(myNumber);
   ```

   > Since parameter does not send the variable, but rather the variable's value, the above method call will be evaluated to `printNumber(4)` when Java runs the code.

2. Receiving the value when the corresponding method is called. In order for the `printNumber` method to recieve the value sent, the method header has to be altered to:

```java
public static void printNumber(int myNumber) {
```

> Notice the addition of `int myNumber` inside the parenthesis. This parameter acts like a normal variable and it is going to catch the value sent when the `printNumber` method is called.

Here are a few key details:

1. If your parameter type is an `int`, then you can only pass in a whole number to the corresponding parameter.
2. The parameter / variable name `int myNumber` in the method header of `printNumber` method is optional. You can change it to any variable name you want (it does not affect the behavior of the code) as long as you are also adjusting the variable name inside the method itself. _For example:_

   ```java
   public static void printNumber(int cheeseCake) {
       System.out.println(cheeseCake);
   }
   ```

   Notice that when I changed the parameter name into `int cheeseCake`, I have to use the name `cheeseCake` inside the method too.

---

## Parameter - Value vs Variable

---

Remember that when you call a method and you "pass in" a variable, Java is **not** going to actually send the variable. Java is only going to send the value of the variable.

This means that if the value sent through the parameter is changed in the receiving method, the change won't affect the value from the sender variable.

Take a look at the code below:

```java
public class Demo {
    public static void main(String[] args) {
        int myNumber = 4;
        printNumber(myNumber);
        System.out.println("Inside main, myNumber is: " + myNumber);
    }

    public static void printNumber(int myNumber) {
        myNumber = 9;
        System.out.println("Inside the method, myNumber is: " + myNumber);
    }
}
```

The output of the above code is:

```
Inside the method, myNumber is: 9
Inside main, myNumber is: 4
```

> Notice that even though the value of `myNumber` in the `printNumber()` method is changed, the value of `myNumber` in the main method remains the same. **These are two completely different variables even though they are under the same name**.

---

## Multiple Parameters

---

You can send it multiple values of different kinds using parameter. You only need to make sure that they are sent and recieved properly.

Take a look at the example code below:

```java
public class Demo {
    public static void main(String[] args) {
        int myNumber = 4;
        printNumber(myNumber, "Hello!", 3.9);
    }

    public static void printNumber(int myNumber, String myText, double myDecimal) {
        System.out.println(myText);
        System.out.println("My favorite number is " + myNumber);
        System.out.println("It is bigger than " + myDecimal);
    }
}
```

Output:

```
Hello!
My favorite number is 4
It is bigger than 3.9
```

**Key details:**

1. The order of the recieving variables / parameters matter. Notice that I am sending in an `int` first, followed by a `String`, followed by a `double`. I have to declare my parameters on the same exact order.

2. The variable / parameter name of both the sender and the reciever does not matter.

3. Even if all the parameters has the same type, the order of the parameter still matters! If you switch up the order of the parameters / variables in the method header, each of the variable / parameters will catch a different value.
