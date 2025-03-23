```java
import java.util.Scanner;

public class AreaCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Choose shape: \n1. Rectangle\n2. Circle\n3. Triangle");
        int choice = scanner.nextInt();

        double area = 0;
        switch (choice) {
            case 1: // Rectangle
                System.out.print("Enter width: ");
                double width = scanner.nextDouble();
                System.out.print("Enter height: ");
                double height = scanner.nextDouble();
                area = width * height;
                System.out.printf("Area of Rectangle: %.2f cm²\n", area);
                break;

            case 2: // Circle
                System.out.print("Enter radius: ");
                double radius = scanner.nextDouble();
                area = Math.PI * radius * radius;
                System.out.printf("Area of Circle: %.2f cm²\n", area);
                break;

            case 3: // Triangle
                System.out.print("Enter base: ");
                double base = scanner.nextDouble();
                System.out.print("Enter height: ");
                double triHeight = scanner.nextDouble();
                area = 0.5 * base * triHeight;
                System.out.printf("Area of Triangle: %.2f cm²\n", area);
                break;

            default:
                System.out.println("Invalid choice!");
                break;
        }

        scanner.close();
    }
}
```
Output
```
Choose shape:
1. Rectangle
2. Circle
3. Triangle
1
Enter width: 4
Enter height: 6
Area of Rectangle: 24.00 cm²
```
