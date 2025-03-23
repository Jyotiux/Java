```java
import java.util.Scanner;
import java.util.Random;

public class MadLibsGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter an adjective: ");
        String adjective1 = scanner.nextLine();
        System.out.print("Enter a noun (animal or person): ");
        String noun1 = scanner.nextLine();
        System.out.print("Enter an adjective: ");
        String adjective2 = scanner.nextLine();
        System.out.print("Enter a verb with -ing: ");
        String verb1 = scanner.nextLine();
        System.out.print("Enter an adjective: ");
        String adjective3 = scanner.nextLine();
        System.out.print("Enter a place: ");
        String place = scanner.nextLine();
        System.out.print("Enter a favorite food: ");
        String food = scanner.nextLine();

        System.out.println("\n Here's your Mad Libs Story! \n");
        System.out.printf("Yesterday, I visited a %s park in %s.%n", adjective1, place);
        System.out.printf("There, I saw a %s %s.%n", adjective2, noun1);
        System.out.printf("It was %s and %s around!%n", adjective2, verb1);
        System.out.printf("Afterward, I ate some %s and felt %s!%n", food, adjective3);


        scanner.close();
    }
}
```

Output
```
Enter an adjective: magical
Enter a noun (animal or person): unicorn
Enter an adjective: sparkling
Enter a verb with -ing: dancing
Enter an adjective: delighted
Enter a place: enchanted forest
Enter a favorite food: chocolate cake

 Here's your Mad Libs Story! 

Yesterday, I visited a magical park in enchanted forest.
There, I saw a sparkling unicorn.
It was sparkling and dancing around!
Afterward, I ate some chocolate cake and felt delighted!

```
