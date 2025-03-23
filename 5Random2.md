### **"Thread-Safe" Generation**  

**Thread safety** refers to the ability of a piece of code, data structure, or method to be safely used by multiple threads at the same time without causing data corruption, unexpected behavior, or race conditions.

---

## **1. Understanding Threads**  
- A **thread** is a lightweight unit of execution within a program.
- **Multi-threading** means multiple threads run in parallel.
- If multiple threads **access and modify shared data** at the same time, issues can arise.

---

## **2. What is a Thread-Safe Class?**  
A **thread-safe class** ensures that:
- Multiple threads can access the object simultaneously **without issues**.
- It uses **synchronization mechanisms** (e.g., `synchronized`, `volatile`, `Atomic variables`).
- It prevents **race conditions** (when two threads try to modify a shared resource simultaneously).

---

## **3. Is `Random` Thread-Safe?**  
- **`Random` is **not thread-safe**.**  
  If multiple threads use a shared instance of `Random`, they may produce incorrect results due to **race conditions**.

### **Example of Race Condition with `Random`**
```java
import java.util.Random;

public class Main {
    static Random random = new Random();  // Shared Random instance

    public static void main(String[] args) {
        Runnable task = () -> {
            System.out.println(Thread.currentThread().getName() + ": " + random.nextInt(10));
        };

        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start();
        t2.start();
    }
}
```
 **Problem:**  
Multiple threads accessing the same `Random` instance **can cause incorrect behavior** because they might interfere with each other.

---

## **4. How to Generate Thread-Safe Random Numbers?**  
###  **Solution 1: Use `ThreadLocalRandom` (Best Choice for Multithreading)**
```java
import java.util.concurrent.ThreadLocalRandom;

public class Main {
    public static void main(String[] args) {
        Runnable task = () -> {
            int num = ThreadLocalRandom.current().nextInt(10);
            System.out.println(Thread.currentThread().getName() + ": " + num);
        };

        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start();
        t2.start();
    }
}
```
 **`ThreadLocalRandom` is thread-safe** because each thread gets its own isolated instance.

---

###  **Solution 2: Use `synchronized` Block**
```java
import java.util.Random;

public class Main {
    private static Random random = new Random();

    public static synchronized int getRandomNumber() {
        return random.nextInt(10);
    }

    public static void main(String[] args) {
        Runnable task = () -> {
            System.out.println(Thread.currentThread().getName() + ": " + getRandomNumber());
        };

        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start();
        t2.start();
    }
}
```
 **This method ensures only one thread can access `random` at a time.** However, it might slow down performance.

---

###  **Solution 3: Use `SecureRandom` for Cryptographic Safety**
```java
import java.security.SecureRandom;

public class Main {
    public static void main(String[] args) {
        SecureRandom secureRandom = new SecureRandom();
        int number = secureRandom.nextInt(10);
        System.out.println(number);
    }
}
```
 **`SecureRandom` is thread-safe** and used in cryptographic applications.

---

## **5. Summary**
| Random Generator | Thread-Safe? | Best For |
|-----------------|-------------|----------|
| `Random` |  No | Single-threaded applications |
| `Math.random()` |  Yes | Simple use cases |
| `ThreadLocalRandom` |  Yes | High-performance multi-threading |
| `SecureRandom` |  Yes | Cryptography & Security |

---

