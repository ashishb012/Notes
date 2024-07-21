# cal Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `cal` (calendar) command in Unix-like operating systems is used to display a calendar in the terminal. Its basic syntax is:

```
cal [OPTIONS] [[[DAY] MONTH] YEAR]
```

## Common Options

1. `-1, --one`: Display only the current month (this is the default)
2. `-3, --three`: Display the previous, current, and next month
3. `-s, --sunday`: Set Sunday as the first day of the week
4. `-m, --monday`: Set Monday as the first day of the week (this is often the default)
5. `-j, --julian`: Display Julian dates (day of year 1-366)
6. `-y, --year`: Display a calendar for the whole year
7. `-V, --version`: Display version information and exit
8. `-h, --help`: Display help message and exit

Note: Some systems may have slightly different options. Always check `man cal` for the most accurate information for your system.

## Examples

1. Display calendar for the current month:
   ```
   cal
   ```

2. Display calendar for a specific month and year:
   ```
   cal 7 2023
   ```
   This displays the calendar for July 2023.

3. Display calendar for a specific year:
   ```
   cal 2023
   ```

4. Display a three-month calendar:
   ```
   cal -3
   ```
   This shows the previous, current, and next month.

5. Display calendar with Sunday as the first day of the week:
   ```
   cal -s
   ```

6. Display calendar with Monday as the first day of the week:
   ```
   cal -m
   ```

7. Display Julian date calendar:
   ```
   cal -j
   ```

8. Display calendar for the whole year:
   ```
   cal -y 2023
   ```

9. Display calendar for a specific date:
   ```
   cal 14 2 2023
   ```
   This highlights February 14, 2023 in the displayed calendar.

10. Combine options:
    ```
    cal -3mj
    ```
    This displays a three-month Julian calendar with Monday as the first day of the week.

11. Display the current month of the previous year:
    ```
    cal $(date -d "last year" +"%m %Y")
    ```

12. Display the calendar for the month 3 months from now:
    ```
    cal $(date -d "3 months" +"%m %Y")
    ```

## Important Considerations

1. The default behavior of `cal` (whether it starts weeks on Sunday or Monday) can vary between systems. Use the `-s` or `-m` option to ensure consistent behavior across systems.

2. The `cal` command typically highlights the current day in the output.

3. Some versions of `cal` may have additional options or slightly different syntax. Always refer to the man pages (`man cal`) for the most accurate information for your system.

4. The `cal` command is often used in scripts to generate date-based information or in command-line tools that need to reference calendar dates.

5. For more advanced date and time operations, you might want to use the `date` command in conjunction with `cal`.

6. If you need to process calendar data programmatically, consider using more robust tools or libraries in languages like Python, which offer more extensive date and time manipulation capabilities.

Remember, while `cal` is a simple command, it can be quite useful for quick date references and in scripts that need to handle calendar-based logic.

[Back to Linux Commands](../readme.md)
