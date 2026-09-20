# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
You wrote a program that stores some input strings into a String array and prints each string in uppercase.
However, you're getting a NullPointerException.
What should you check in your array before calling .toUpperCase() on a element?



## AIM:
To write a Java program that demonstrates a NullPointerException when calling .toUpperCase() on a null string, and to show how to handle it safely.

## ALGORITHM :
1. Read a string input from the user.

2. If the user types "null" (case-insensitive), assign the variable str to null; otherwise assign the input string.

3. Use a try block to call str.toUpperCase().

4. If str is null, a NullPointerException will occur and be caught in the catch block.

5. Print "Null element" when the exception is caught.

6. Close the scanner.



## PROGRAM:
 ```
/*
Program to implement a Exception Handling using Java
Developed by: Ahamed Sahul Hameed M
RegisterNumber: 212224040016
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

public class NullPointerArrayExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String input = sc.nextLine();
        String str = input.equalsIgnoreCase("null") ? null : input;

        try {
            System.out.println(str.toUpperCase());
        } catch (NullPointerException e) {
            System.out.println("Null element");
        }

        sc.close();
    }
}
```


## OUTPUT:

<img width="624" height="359" alt="image" src="https://github.com/user-attachments/assets/8c3a3da5-a663-4aa0-8433-b5ca5dbd4108" />

## RESULT:

Therefore the program successfully demonstrates how a NullPointerException occurs when calling .toUpperCase() on a null value.
