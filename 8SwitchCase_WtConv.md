###  Switch Statement in Java
The `switch` statement allows selecting one of many code blocks to be executed based on the value of a variable.

```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner= new Scanner(System.in);
        System.out.print("Enter the day of the week: ");
        String day = scanner.nextLine();

        switch(day){
            case "Monday", "Tuesday", "Wednesday", "Thursday", "Friday" -> System.out.println("It is a weekday");
            case "Saturday", "Sunday" -> System.out.println("It is a weekend");
            default -> System.out.println(day + " is not a day");
        }
        scanner.close();
    }
}
```
Output:
```
Enter the day of the week: Tuesday
It is a weekday
```


###  Weight Conversion Program
This program converts weight between pounds (lbs) and kilograms (kgs).

```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double weight, newWeight;
        int choice;
        
        System.out.println("Choose an option:");
        System.out.println("1: Convert lbs to kgs");
        System.out.println("2: Convert kgs to lbs");
        System.out.print("Choose an option: ");
        choice = scanner.nextInt();

        if(choice == 1){
            System.out.print("Enter weight in lbs: ");
            weight = scanner.nextDouble();
            newWeight = weight * 0.453592;
            System.out.printf("Weight in kgs: %.2f\n", newWeight);
        } else if(choice == 2){
            System.out.print("Enter weight in kgs: ");
            weight = scanner.nextDouble();
            newWeight = weight * 2.20462;
            System.out.printf("Weight in lbs: %.2f\n", newWeight);
        } else {
            System.out.println("Invalid choice");
        }
        scanner.close();
    }
}
```
Output:
```
Choose an option:
1: Convert lbs to kgs
2: Convert kgs to lbs
Choose an option: 2
Enter weight in kgs: 50
Weight in lbs: 110.23
```
