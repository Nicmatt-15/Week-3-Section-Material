# String Methods

## Table of Content

- [What are String methods?](#what-are-string-methods)
- [How is a String method used?](#how-is-a-string-method-used)
- [`.length()` String method](#length-string-method)
- [`.charAt(...)` String method](#charat-string-method)
- [`.indexOf(...)` String method](#indexof-string-method)
- [String Method Common Error](#string-method-common-error)

---

## What are String methods?

---

String methods are tools that you can use to extract some information from a String. The information can be:

- The string length
- A character in from a specific index in a String
- The index / position of a character in a String.

---

## How is a String method used?

---

Here are a few steps that to use String methods:

1. Generally, you would need a String variable with a String value. For example:
   ```java
   String input = "drosera";
   ```
2. Use the String method you need using the following template:

   > _stringVariableName_.**stringMethodName**();

   For example, if we have the String variable named `input` like in step 1:

   > input.length();

3. Save the result of your String method to the appropriate variable type. For example, using `.length()` will return an integer. Saving the result to a variable will look like the following:

   > int lengthOfWord = input.length();

---

## `.length()` String method

---

The `.length()` returns how many characters / letters are in your String.

_Example:_

```java
String input = "drosera";
int letterCount = input.length();
System.out.println(letterCount);
```

_Output:_

```
7
```

---

## `.charAt(...)` String method

---

The .`charAt(...)` returns the character at the index that is specified.

_Example:_

```java
String input = "drosera";
char result = input.charAt(4);
System.out.println(result);
```

_Output:_

```
e
```

---

## `.indexOf(...)` String method

---

The `indexOf(...)` returns the index / position where the specified letter exists in the String.

1. If the specified letter does not exists in the String, `indexOf()` will return -1.
2. If the specified letter exists more than once in the String, `indexOf()` will return the smallest index number / the earliest occurence of the letter.

_Example:_

```java
String input = "drosera";
int position = input.indexOf("r");
System.out.println(position);
```

_Output:_

```
1
```

---

## String Method Common Error

---

> One of the most common error when you are using String method is an error called `StringIndexOutOfBoundsException`. This is usually caused when you are trying to access index of a String smaller than 0 or bigger than `.length() - 1`.
