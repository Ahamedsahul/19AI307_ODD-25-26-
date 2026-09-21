# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.

## AIM:
To develop a Java program that uses the Factory Pattern to generate different types of notifications—Email, SMS, and Push—and call the appropriate notifyUser() method based on user input.

## ALGORITHM :
Define a Notification interface with a method notifyUser().
Implement three classes EmailNotification, SMSNotification, and PushNotification, each overriding notifyUser() with specific behavior.
Define a NotificationFactory interface containing a method createNotification().
Create an EmailFactory class implementing NotificationFactory that returns an EmailNotification object.
Create an SMSFactory class implementing NotificationFactory that returns an SMSNotification object.
Create a PushFactory class implementing NotificationFactory that returns a PushNotification object.
In the main() method, read the notification type from the user.
If the type is "email", create an EmailFactory object.
If the type is "sms", create an SMSFactory object.
If the type is "push", create a PushFactory object.
If the input is "exit", terminate the loop.
If the input is invalid, print an error message.
Use the selected factory to create the appropriate Notification object.
If the notification object is valid, call notifyUser().
Continue reading input until "exit" is entered.
Close the Scanner after exiting the loop.



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
