# Get-Weekly-Temperatures
A JAVA app that records daily average temperatures for a week. Users enter a day and its temperature. Typing "week" displays all days, temperatures, and the weekly average. Uses lists, loops, and conditionals for basic input handling and calculations.
# Pseudocode
Start
Create two ArrayLists: one for days and one for temperatures

Use a while-loop to repeatedly prompt the user:
    Ask the user to enter a day of the week or "week" to display summary
    If input is a valid day and not already entered:
        Prompt for average temperature
        Add day to days list
        Add temperature to temperatures list
    Else if input is "week":
        For each day in the list:
            Display day and its temperature
        Compute and display average temperature
        End the loop
    Else:
        Show invalid input message or duplicate day warning

End
# JAVA Sourcecode
import java.util.ArrayList;
import java.util.Scanner;

public class WeeklyTemperature {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<String> days = new ArrayList<>();
        ArrayList<Double> temperatures = new ArrayList<>();

        String[] validDays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
        while (true) {
            System.out.print("Enter a day of the week (Monday to Sunday) or 'week' to display results: ");
            String input = scanner.nextLine().trim();

            if (input.equalsIgnoreCase("week")) {
                if (days.size() == 0) {
                    System.out.println("No data entered yet.");
                    continue;
                }

                double total = 0;
                System.out.println("\n--- Weekly Temperatures ---");
                for (int i = 0; i < days.size(); i++) {
                    System.out.println(days.get(i) + ": " + temperatures.get(i) + "°F");
                    total += temperatures.get(i);
                }

                double average = total / temperatures.size();
                System.out.println("Weekly Average Temperature: " + average + "°F");
                break;
            }

            boolean isValidDay = false;
            for (String day : validDays) {
                if (day.equalsIgnoreCase(input)) {
                    input = day; // Capitalize properly
                    isValidDay = true;
                    break;
                }
            }

            if (!isValidDay) {
                System.out.println("Invalid day entered. Try again.");
                continue;
            }

            if (days.contains(input)) {
                System.out.println("Temperature for this day already entered.");
                continue;
            }

            System.out.print("Enter the average temperature for " + input + ": ");
            try {
                double temp = Double.parseDouble(scanner.nextLine());
                days.add(input);
                temperatures.add(temp);
            } catch (NumberFormatException e) {
                System.out.println("Invalid temperature. Please enter a numeric value.");
            }
        }

        scanner.close();
    }
}


# Screenshot
<img width="1706" alt="Screenshot 2025-04-29 at 2 30 17 PM" src="https://github.com/user-attachments/assets/e7c7fcdb-52dd-4c76-96c0-0b44d3c30a43" />



