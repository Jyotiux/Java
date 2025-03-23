

### Ternary Operator in Java
The ternary operator `? :` provides a shorthand way to write simple `if-else` statements.

```java
public class Main {
    public static void main(String[] args) {
        int income = 30000;
        double taxRate = (income >= 40000) ? 0.25 : 0.15;
        System.out.println("Tax Rate: " + taxRate);
    }
}
```
Output:
```
Tax Rate: 0.15
```

###  Temperature Conversion Program
This program converts temperatures between Celsius and Fahrenheit using the ternary operator.

```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner= new Scanner(System.in);
        double temp, newTemp;
        String unit;

        System.out.print("Enter the temperature: ");
        temp=scanner.nextDouble();

        System.out.print("Convert to Celsius or Fahrenheit? (C or F): ");
        unit = scanner.next().toUpperCase();

        newTemp = (unit.equals("C")) ? (temp - 32) * 5 / 9 : (temp * 9 / 5) + 32;

        System.out.printf("%.2f°%s", newTemp, unit);
        scanner.close();
    }
}
```
Output:
```
Enter the temperature: 100
Convert to Celsius or Fahrenheit? (C or F): c
37.78°C
```

