# Ex.No:3(F) WRAPPER CLASS

## QUESTION:
Write a Java program to check if a number is prime using wrapper classes. 

## AIM:
To write a Java program that checks whether a given number is prime by using the Integer wrapper class for parsing and handling the input.

## ALGORITHM :
1. Read input from the user as a string.

2. Use the Integer.parseInt() method (wrapper class) to convert the input into an integer.

3. If parsing fails, catch NumberFormatException and display an error message.

4. If the number is less than or equal to 1, it is not prime.

5. If any divisor divides the number completely, mark it as not prime.

6. After checking, print whether the number is prime or not.

7. Close the scanner.


## PROGRAM:
 ```
/*
Program to implement a InnerClass using Java
Developed by: Ahamed Sahul Hameed M
RegisterNumber: 212224040016
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

public class PrimeChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        
        String input = scanner.nextLine();

        try {
            Integer number = Integer.parseInt(input); // Using Integer wrapper class

            if (number <= 1) {
                System.out.println(number + " is not a prime number.");
            } else {
                boolean isPrime = true;
                for (int i = 2; i <= Math.sqrt(number); i++) {
                    if (number % i == 0) {
                        isPrime = false;
                        break;
                    }
                }

                if (isPrime) {
                    System.out.println(number + " is a prime number.");
                } else {
                    System.out.println(number + " is not a prime number.");
                }
            }

        } catch (NumberFormatException e) {
            System.out.println("Invalid input. Please enter a valid integer.");
        }

        scanner.close();
    }
}
```


## OUTPUT:

<img width="893" height="258" alt="image" src="https://github.com/user-attachments/assets/2cfce946-0ad1-43c0-a0b9-9f1d4d27a34b" />

## RESULT:

Therefore the program successfully checks if the input number is a prime using the Integer wrapper class.



