# Age in Days

This exercise involves writing a Java program to calculate your age in days based on your birthday. The program will use the `LocalDate` class from the `java.time` package and the `Scanner` class for user input.

---

## Objective
Create a Java program that:
1. Asks the user for their birthday (year, month, and day).
2. Calculates the user's current age in days.
3. Prints the results, including the entered birthday and the current date.

---

## Steps to Complete

### 1. Create a New Java Project
- Open **Eclipse**.
- Create a new Java project named `AgeInDays`.

### 2. Create the Main Class
- Inside the project, create a new class and name it appropriately (e.g., `AgeInDaysCalculator`).
- Implement the program in the `main` method of the class.

### 3. Program Functionality
- Use the `Scanner` class to read the user's input for:
    - Year of birth
    - Month of birth
    - Day of birth
- Use the `LocalDate` class to:
    - Get today's date using `LocalDate.now()`.
    - Create a `LocalDate` object for the user's birthday using `LocalDate.of(year, month, day)`.
- Calculate the age in days by subtracting the birthday from today's date.

---

## Example Program

### User Interaction
The program's input and output may look like this:

```
In which year were you born? (e.g., 1950)
1970
In which month were you born? (e.g., 2 for February)
3
On which day of the month were you born? (1-31)
2
You were born on 1970-03-02.
Today is 2018-09-27.
You are 17741 days old.
```

### Example Implementation
```java
import java.time.LocalDate;
import java.time.temporal.ChronoUnit;
import java.util.Scanner;

public class AgeInDaysCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // User input for year, month, and day of birth
        System.out.println("In which year were you born? (e.g., 1950)");
        int year = scanner.nextInt();
        System.out.println("In which month were you born? (e.g., 2 for February)");
        int month = scanner.nextInt();
        System.out.println("On which day of the month were you born? (1-31)");
        int day = scanner.nextInt();

        // Creating LocalDate objects
        LocalDate birthday = LocalDate.of(year, month, day);
        LocalDate today = LocalDate.now();

        // Outputting dates
        System.out.println("You were born on " + birthday + ".");
        System.out.println("Today is " + today + ".");

        // Calculating age in days
        long ageInDays = ChronoUnit.DAYS.between(birthday, today);
        System.out.println("You are " + ageInDays + " days old.");

        scanner.close();
    }
}
```

---

## Hints
- Use the `LocalDate.now()` method to get today's date.
- Use the `LocalDate.of(year, month, day)` method to create a date from the user input.
- Use the `ChronoUnit.DAYS.between(date1, date2)` method to calculate the difference in days.
- Use the `Scanner` class with the `nextInt()` method to get user input.

---

## Notes
- Ensure the class name matches your file name if you use a different name.
- Test the program with various inputs to ensure accuracy.

Happy coding! 🎉
