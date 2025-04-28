# Get-Weekly-Temperatures
A Python app that records daily average temperatures for a week. Users enter a day and its temperature. Typing "week" displays all days, temperatures, and the weekly average. Uses lists, loops, and conditionals for basic input handling and calculations.
# Pseudocode
Initialize two empty lists: days_list and temps_list
Loop:
    Prompt user: "Enter a day of the week (or 'week' to finish):"
    If user input is "week":
        Break the loop
    Else:
        Prompt user: "Enter average temperature for {day}:"
        Add the day to days_list
        Add the temperature (converted to float) to temps_list
If days_list is not empty:
    For each day and temp, print day and temperature
    Calculate weekly average:
        Sum all temperatures and divide by the number of days
    Print weekly average
Else:
    Print "No data entered."
# Python Sourcecode
Initialize two empty lists to store days and temperatures
days_list = []
temps_list = []

print("Enter the day of the week and corresponding temperature.")
print("Type 'week' when you are finished.\n")

while True:
    day = input("Enter a day (Monday, Tuesday, ..., Sunday) or 'week' to finish: ").strip()

    if day.lower() == "week":
        break
    else:
        try:
            temp = float(input(f"Enter the average temperature for {day}: "))
            days_list.append(day)
            temps_list.append(temp)
        except ValueError:
            print("Invalid temperature. Please enter a number.")

Output the stored days and temperatures
if days_list:
    print("\nWeekly Report:")
    for i in range(len(days_list)):
        print(f"{days_list[i]}: {temps_list[i]}°")

    Calculate and display the weekly average temperature
    weekly_average = sum(temps_list) / len(temps_list)
    print(f"\nWeekly Average Temperature: {weekly_average:.2f}°")
else:
    print("No data entered.")

# Screenshot
<img width="1655" alt="Screenshot 2025-04-28 at 12 01 11 AM" src="https://github.com/user-attachments/assets/0b83310f-433e-49a7-a116-70f1f6b41e38" />


