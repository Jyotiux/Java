# **Java Random Number Generation **  

## **1. Introduction to Random Numbers in Java**  
Java provides several ways to generate random numbers. The most common method is using the `Random` class from `java.util.Random`, but other methods include `Math.random()`, `ThreadLocalRandom`, and `SecureRandom` for cryptographic security.

---

## **2. Using the `Random` Class**  
The `Random` class in Java is a widely used utility for generating random numbers of different types.

### **2.1 Generating a Random Integer**
```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        int number = random.nextInt(6) + 1;  // Generates a number between 1 and 6
        System.out.println(number);
    }
}
```
**Output:**  
(Random number between **1 and 6**)

### **2.2 Generating a Random Double**
```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        double number = random.nextDouble();  // Generates a number between 0.0 and 1.0
        System.out.println(number);
    }
}
```
**Output:**  
(Random double value between **0.0 and 1.0**)

### **2.3 Generating a Random Boolean**
```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        boolean isHeads = random.nextBoolean();  // Generates either true or false
        System.out.println(isHeads);
    }
}
```
**Output:**  
(`true` or `false`)

### **2.4 Generating a Random Float**
```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        float number = random.nextFloat();  // Generates a float between 0.0 and 1.0
        System.out.println(number);
    }
}
```
**Output:**  
(Random float value between **0.0 and 1.0**)

### **2.5 Generating a Random Long**
```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        long number = random.nextLong();  // Generates a random long value
        System.out.println(number);
    }
}
```
**Output:**  
(A random long integer)

### **2.6 Generating a Random Gaussian (Normally Distributed) Value**
```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        double gaussianValue = random.nextGaussian();  // Generates a normally distributed random value
        System.out.println(gaussianValue);
    }
}
```
**Output:**  
(A random value with a mean of 0 and a standard deviation of 1)

---

## **3. Using `Math.random()`**  
The `Math.random()` method generates a pseudo-random number between `0.0` and `1.0`.

```java
public class Main {
    public static void main(String[] args) {
        double number = Math.random();  // Generates a number between 0.0 and 1.0
        System.out.println(number);
    }
}
```
**Output:**  
(A random value between **0.0 and 1.0**)

### **3.1 Generating a Random Integer using `Math.random()`**
```java
public class Main {
    public static void main(String[] args) {
        int number = (int) (Math.random() * 6) + 1;  // Generates a number between 1 and 6
        System.out.println(number);
    }
}
```
**Output:**  
(A random integer between **1 and 6**)

---

## **4. Using `ThreadLocalRandom` (Efficient for Multithreading)**
`ThreadLocalRandom` is a faster alternative to `Random` when multiple threads generate random numbers.

```java
import java.util.concurrent.ThreadLocalRandom;

public class Main {
    public static void main(String[] args) {
        int number = ThreadLocalRandom.current().nextInt(1, 6);  // Random number between 1 and 5
        System.out.println(number);
    }
}
```
**Output:**  
(A random integer between **1 and 5**)

---

## **5. Using `SecureRandom` (For Cryptography & Security Applications)**
`SecureRandom` is used when higher security randomness is required.

```java
import java.security.SecureRandom;

public class Main {
    public static void main(String[] args) {
        SecureRandom secureRandom = new SecureRandom();
        int number = secureRandom.nextInt(6) + 1;  // Random number between 1 and 6
        System.out.println(number);
    }
}
```
**Output:**  
(A cryptographically secure random integer between **1 and 6**)

---

## **6. Summary of Methods**
| Method | Range | Thread-Safe? | Use Case |
|--------|-------|-------------|----------|
| `Random.nextInt(n)` | `0` to `n-1` | No | General-purpose random numbers |
| `Random.nextDouble()` | `0.0` to `1.0` | No | Random floating-point numbers |
| `Random.nextBoolean()` | `true` or `false` | No | Coin flips, probability checks |
| `Math.random()` | `0.0` to `1.0` | Yes | Simple random numbers |
| `ThreadLocalRandom` | Depends | Yes | Efficient for multi-threading |
| `SecureRandom` | Depends | Yes | Cryptography and security |

