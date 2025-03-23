

## ** Formula for Compound Interest**  
The formula used in the program is:  

\[
A = P \times \left(1 + \frac{r}{n}\right)^{(n \times t)}
\]

Where:  
- **A** = Final amount after interest  
- **P** = Principal (initial investment)  
- **r** = Annual interest rate (decimal form)  
- **n** = Number of times interest is compounded per year  
- **t** = Number of years  

---

## ** Code Explanation**  

1. **Import Scanner** – Allows user input.  
2. **Declare variables** – `principal`, `rate`, `timesCompounded`, `years`, and `amount`.  
3. **Take user input** – User enters principal, rate, compounding frequency, and duration.  
4. **Convert rate to decimal** – Divide by 100 for percentage conversion.  
5. **Apply compound interest formula** – Use `Math.pow()` for exponentiation.  
6. **Display the final amount** – Prints the total after `t` years.  

---

## ** Sample Input & Output**  

```
Enter the principal amount: 20000
Enter the interest rate(in years): 3
Enter the number of times compounded per year: 1
Enter the number of years: 1
The amount after 1 year is: Rs20600.0
```

---
```java
import java.util.Scanner;

public class CompoundInterestCalculator {
    public static void main(String[] args) {
        // Create Scanner object for user input
        Scanner scanner = new Scanner(System.in);

        // Declare variables
        double principal, rate, amount;
        int timesCompounded, years;

        // Get user input
        System.out.print("Enter the principal amount: ");
        principal = scanner.nextDouble();

        System.out.print("Enter the annual interest rate (in %): ");
        rate = scanner.nextDouble() / 100; // Convert percentage to decimal

        System.out.print("Enter the number of times interest is compounded per year: ");
        timesCompounded = scanner.nextInt();

        System.out.print("Enter the number of years: ");
        years = scanner.nextInt();

        // Calculate compound interest
        amount = principal * Math.pow(1 + rate / timesCompounded, timesCompounded * years);

        // Display the result
        System.out.printf("The amount after %d years is: Rs%.2f\n", years, amount);

        // Close the scanner
        scanner.close();
    }
}
```
