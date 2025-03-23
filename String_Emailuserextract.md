

###  String Operations in Java
Strings in Java are objects that represent sequences of characters. Java provides many built-in methods to manipulate strings.

```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        String name="   Jyoti Singh ";
        int length = name.length();
        char letter = name.charAt(7);
        int index = name.indexOf(" ");
        int lastIndex = name.lastIndexOf("o");

        name = name.trim();  // Removes leading and trailing spaces
        name = name.replace("o", "a");  // Replaces 'o' with 'a'

        System.out.println("Length: " + length);
        System.out.println("Character at index 7: " + letter);
        System.out.println("First space index: " + index);
        System.out.println("Last occurrence of 'o': " + lastIndex);
        System.out.println("Modified name: " + name);
    }
}
```
**Output:**
```
Length: 15
Character at index 7: i
First space index: 0
Last occurrence of 'o': 5
Modified name: Jyati Singh
```

###  Extracting Email Username and Domain
Extracting the username and domain from an email string using `substring()`.

```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String email, username, domain;
        System.out.print("Enter your Email: ");
        email = scanner.nextLine();
        if(email.contains("@")) {
            username = email.substring(0, email.indexOf("@"));
            domain = email.substring(email.indexOf("@") + 1);
            System.out.println("Username: " + username);
            System.out.println("Domain: " + domain);
        } else {
            System.out.println("Invalid Email: Must contain '@'");
        }
        scanner.close();
    }
}
```
**Output:**
```
Enter your Email: jyotisingh@gmail.com
Username: jyotisingh
Domain: gmail.com
```
