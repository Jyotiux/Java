### Java Basics and Examples

#### 1. Printing in Java

```java
public class Main {
    public static void main(String[] args) {
        System.out.print("I like pizza!");
    }
}
```
**Output:**
```
I like pizza!
```

Using `println` to add a newline:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("I like pizza!");
        System.out.println("It's really gooood.");
    }
}
```
**Output:**
```
I like pizza!
It's really gooood.
```

Or using `\n`:

```java
public class Main {
    public static void main(String[] args) {
        System.out.print("I like pizza! \n");
        System.out.print("It's really gooood.");
    }
}
```
**Output:**
```
I like pizza!
It's really gooood.
```

#### 2. Variables in Java

**Declaration and Initialization:**

```java
public class Main {
    public static void main(String[] args) {
        int age = 21;
        System.out.println(age);
    }
}
```
**Output:**
```
21
```

Variable types:

```java
public class Main {
    public static void main(String[] args) {
        int age = 21;
        double price = 19.0;
        char grade = 'A';
        boolean isStudent = true;
        
        System.out.println("Age: " + age);
        System.out.println("Price: " + price);
        System.out.println("Grade: " + grade);
        System.out.println("Student: " + isStudent);
    }
}
```
**Output:**
```
Age: 21
Price: 19.0
Grade: A
Student: true
```

#### 3. User Input with Scanner

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter your name: ");
        String name = scanner.nextLine();
        
        System.out.print("Enter your age: ");
        int age = scanner.nextInt();
        
        System.out.println("Hello " + name + ", you are " + age + " years old.");
        
        scanner.close();
    }
}
```
**Output:**
```
Enter your name: Jyoti
Enter your age: 20
Hello Jyoti, you are 20 years old.
```

#### 4. Random Numbers

Generate a random integer:

```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        int number = random.nextInt(1, 6);
        System.out.println(number);
    }
}
```
**Output:** (Random value between 1 and 5)
```
3
```

#### 5. Math Functions

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.PI);
        System.out.println(Math.sqrt(9));
        System.out.println(Math.max(10, 14));
    }
}
```
**Output:**
```
3.141592653589793
3.0
14
```

#### 6. String Operations

```java
public class Main {
    public static void main(String[] args) {
        String name = "   Jyoti Singh ";
        name = name.trim().toUpperCase();
        
        System.out.println("Length: " + name.length());
        System.out.println("First letter: " + name.charAt(0));
        System.out.println("Replaced: " + name.replace("J", "D"));
    }
}
```
**Output:**
```
Length: 11
First letter: J
Replaced: DYOTI SINGH
```



