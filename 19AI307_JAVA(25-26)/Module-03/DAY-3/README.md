# Ex.No:3(C) ABSTRACTION

## QUESTION:
In a secret intelligence facility, encrypted messages are stored as arrays of characters. Each type of agent has a different way to decode these messages. Define an abstract class Decoder with a method decodeMessage(String[] fragments).
There are two types of agents:

   AlphaAgent: Extracts a meaningful string by rearranging the fragments based on even indices first, then odd indices, and then reversing the final result.

   BetaAgent: Picks all fragments that start and end with the same letter, joins them with -, and removes all vowels from the resulting string.


## AIM:
To create an abstract class Decoder with an abstract method decodeMessage(), and implement two subclasses, AlphaAgent and BetaAgent, each with a unique decoding technique for encrypted message fragments.

## ALGORITHM :
1. Create an abstract class Decoder containing an abstract method decodeMessage(String[] fragments).

2. Create subclass AlphaAgent implementing decodeMessage() by collecting fragments at even indices,then collecting fragments at odd indices,reversing the combined list.

3. Joining all fragments into one decoded string.

4. Create subclass BetaAgent implementing decodeMessage() by selecting fragments whose first and last characters match (case-insensitive).

5. Joining selected fragments using -.

6. Removing all vowels from the final combined string.

7. Read number of fragments and store them in a string array.

8. Read agent type (1 = AlphaAgent, 2 = BetaAgent).

9. Create the corresponding agent object.

10. Call decodeMessage() and print the decoded output.





## PROGRAM:
 ```
/*
Program to implement a Abstraction using Java
Developed by: Ahamed Sahul Hameed M
RegisterNumber: 212224040016
*/
```

## SOURCE CODE:

```
import java.util.*;

abstract class Decoder {
    abstract String decodeMessage(String[] fragments);
}


class AlphaAgent extends Decoder {
    @Override
    String decodeMessage(String[] fragments) {
        List<String> ordered = new ArrayList<>();
        
        for (int i = 0; i < fragments.length; i += 2) {
            ordered.add(fragments[i]);
        }
       
        for (int i = 1; i < fragments.length; i += 2) {
            ordered.add(fragments[i]);
        }
       
        Collections.reverse(ordered);
        
        StringBuilder result = new StringBuilder();
        for (String s : ordered) {
            result.append(s);
        }
        return result.toString();
    }
}


class BetaAgent extends Decoder {
    @Override
    String decodeMessage(String[] fragments) {
        List<String> selected = new ArrayList<>();
        for (String f : fragments) {
            if (!f.isEmpty()) {
                char first = Character.toLowerCase(f.charAt(0));
                char last = Character.toLowerCase(f.charAt(f.length() - 1));
                if (first == last) {
                    selected.add(f);
                }
            }
        }

        String joined = String.join("-", selected);
        return joined.replaceAll("[AEIOUaeiou]", "");
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = Integer.parseInt(sc.nextLine().trim());
        String[] fragments = new String[n];
        for (int i = 0; i < n; i++) {
            fragments[i] = sc.nextLine().trim();
        }
        int type = Integer.parseInt(sc.nextLine().trim());

        Decoder agent;
        if (type == 1)
            agent = new AlphaAgent();
        else
            agent = new BetaAgent();

        System.out.println(agent.decodeMessage(fragments));
        sc.close();
    }
}
```





## OUTPUT:
<img width="791" height="586" alt="image" src="https://github.com/user-attachments/assets/8e5ac67e-a125-4db4-b804-52e16025fa7e" />



## RESULT:
Therefore the program successfully decodes messages using the rules defined for AlphaAgent and BetaAgent.




