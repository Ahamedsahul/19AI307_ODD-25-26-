# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.

## AIM:
To develop a Java program that uses the Factory Pattern to generate different types of notifications—Email, SMS, and Push—and call the appropriate notifyUser() method based on user input.

## ALGORITHM :
1. Define a Notification interface with a method notifyUser().

2. Implement three classes EmailNotification, SMSNotification, and PushNotification, each overriding notifyUser() with specific behavior.

3. Define a NotificationFactory interface with a method createNotification().

4. Create an EmailFactory class implementing NotificationFactory that returns an EmailNotification object.

5. Create an SMSFactory class implementing NotificationFactory that returns an SMSNotification object.

6. Create a PushFactory class implementing NotificationFactory that returns a PushNotification object.

7. Read the notification type from the user in a loop.

8. If the input is "exit", terminate the loop.

9. If the input is "email", create an EmailFactory object.

10. If the input is "sms", create an SMSFactory object.

11. If the input is "push", create a PushFactory object.

12. If the input is invalid, print an error message.

13. Use the selected factory to create the appropriate Notification object.

14. If the Notification object is valid, call notifyUser().

15. Continue reading user input until "exit" is entered.

16. Close the Scanner after exiting the loop.



## PROGRAM:
 ```
/*
Program to implement a Abstract Factory Pattern using Java
Developed by: Ahamed Sahul Hameed M
RegisterNumber: 212224040016
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

// Product Interface
interface Notification {
    void notifyUser();
}

// Concrete Products
class EmailNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class SMSNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class PushNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

// Abstract Factory
interface NotificationFactory {
    Notification createNotification();
}

// Concrete Factories
class EmailFactory implements NotificationFactory {
    public Notification createNotification() {
        return new EmailNotification();
    }
}

class SMSFactory implements NotificationFactory {
    public Notification createNotification() {
        return new SMSNotification();
    }
}

class PushFactory implements NotificationFactory {
    public Notification createNotification() {
        return new PushNotification();
    }
}

// Main Class
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (true) {
            String input = sc.nextLine();

            if (input.equalsIgnoreCase("exit"))
                break;

            NotificationFactory factory = null;

            if (input.equalsIgnoreCase("email"))
                factory = new EmailFactory();
            else if (input.equalsIgnoreCase("sms"))
                factory = new SMSFactory();
            else if (input.equalsIgnoreCase("push"))
                factory = new PushFactory();

            if (factory != null) {
                Notification n = factory.createNotification();
                n.notifyUser();
            } else {
                System.out.println("Invalid notification type: " + input);
            }
        }

        sc.close();
    }
}
```

```


## OUTPUT:

<img width="943" height="423" alt="image" src="https://github.com/user-attachments/assets/4bf885fa-c016-47dd-bfe0-edf37e8a39e5" />


## RESULT:

Therefore the program successfully creates and sends the appropriate notification type using the Factory Pattern.
