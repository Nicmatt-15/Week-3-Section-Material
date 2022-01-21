# String Traversal

## Table of Content

- [What is String Traversal?](#what-is-string-traversal)
- [What are the key components of String traversal?](#what-are-the-key-components-of-string-traversal)
- [Relevant Context of String Traversal](#relevant-context-of-string-traversal)

## What is String Traversal?

---

String traversal is the act of looking through every letter in a String (_in order_) one by one.

Generally, String traversal is used for the following goal:

> Taking each letter in the String one by one, _either from the start of the String to the end or vice versa_, to be printed or processed even further.

---

## What are the key components of String traversal?

---

String traversal consists of 3 unchangable elements:

1. A for-loop
2. String method `.length()`
3. String method `.charAt(...)`

All of the three elements above form **_an efficient way_** for us to access every individual letter of a String, as the following:

```java
String someRandomText = "drosera";
for (int index = 0; index < someRandomText.length(); index++) {
    char currentLetter = someRandomText.charAt(index);
}
```

**Here are some key details:**

1. Notice that the for-loop counter variable (_in this case it is called `int index`_) starts at 0.

   The reason why it is important to start at 0 is because **the first letter of any String is located at index 0**, meaning you need `.charAt(0)` to access it. Since the for-loop counter variable starts at 0, the first iteration would always result in `.charAt(0)`.

2. Notice that the bound for the for-loop is the `.length()` of the String.

   The reasoning behind the use of `.length()` is to let the for-loop traverse through each letter **until the very last letter of the String**.

3. Notice the use of the _less than_ operator (`<`) instead of the _less than or equal to_ operator (`<=`).

   Look at the following example:

   ```java
   String myText = "drosera";
   ```

   If we run the following code:

   ```java
   System.out.println(myText.length());
   ```

   We will get an output of 7! Why? because the String `"drosera"` has 7 letters.

   Now take a look at the picture below:

   ![String-Index.png](https://i.postimg.cc/yYgNQWts/String-Index.png)

   > If the image above does not load, please use the following link: https://postimg.cc/vcyMD8GN

   Notice that because the index of a String **always** starts at 0, the last index is always 1 less than the length of the String. For this reason, we always want our for-loop to stop one number earlier than the length of the String by using `<` instead of `<=`.

   _Alternatively, you can use the `<=` sign like the example below:_

   ```java
   String someRandomText = "drosera";
   for (int index = 0; index <= someRandomText.length() - 1; index++) {
       char currentLetter = someRandomText.charAt(index);
   }
   ```

   Notice that because we are using `<=`, we are compensating by setting the loop bound to `someRandomText.length() - 1`. The goal of the `-1` in the equation is to, once again, stop one number earlier than the length of the String.

---

## Relevant Context of String Traversal

---

String traversal will be used for 2 main things in this week's work

- Printing the letter backwards
- Encrypting a word

---

**Printing the letter backwards (Checkpoint 3)**

---

> To achieve this, you will need to use a for-loop that counts from `.length() - 1` backwards to 0. In other words, you need a for-loop that access each letter of the String from the end of the String (index `.length() - 1`) to the front of the String (index 0)

An example of how we would print a String backwards using String traversal:

```java
String input = "hello";
for (int index = input.length() - 1; index >= 0; index--) {
   System.out.print(input.charAt(index));
}
```

**Key pointers:**

- We start iterating from `.length() - 1` instead of `.length()`. Remember that the last index is always one less than the length of the String itself.
- We use `index--` because we want the index value to count backwards until it hits 0.
- We use `index >= 0` because we want to keep iterating _as long as_ the value of index is bigger than zero or until it hits zero before stopping. In other words, we want to keep looping until we have accessed the first letter of the String.

---

**Encrypting a String by changing each individual letter.**

---

> Encrypting a String is done by traversing through one letter at a time (generally from front to back of the String) and encrpyting each letter using a specified method. Take a look at the pseudocode below:

```java
String input = "hello";
for (int index = 0; index < input.length(); index++) {
   char currentChar = input.charAt(index);
   // Encrypt the letter here

   // Print out the encrypted letter here
}
```
