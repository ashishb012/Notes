# Comprehensive Guide to the 'uniq' Command

The 'uniq' command in Unix and Linux is used to report or filter out repeated lines in a file. It's often used in combination with the 'sort' command, as 'uniq' only detects adjacent duplicate lines.

## Basic Syntax

```
uniq [OPTIONS] [INPUT [OUTPUT]]
```

## Common Options

1. `-c, --count`: 
   Prefix lines with the number of occurrences.

   Example:
   ```
   uniq -c file.txt
   ```

2. `-d, --repeated`: 
   Only print duplicate lines, one for each group.

   Example:
   ```
   uniq -d file.txt
   ```

3. `-u, --unique`: 
   Only print unique lines.

   Example:
   ```
   uniq -u file.txt
   ```

4. `-i, --ignore-case`: 
   Ignore differences in case when comparing.

   Example:
   ```
   uniq -i file.txt
   ```

5. `-f, --skip-fields=N`: 
   Avoid comparing the first N fields.

   Example:
   ```
   uniq -f 1 file.txt
   ```

6. `-s, --skip-chars=N`: 
   Avoid comparing the first N characters.

   Example:
   ```
   uniq -s 3 file.txt
   ```

7. `-w, --check-chars=N`: 
   Compare no more than N characters in lines.

   Example:
   ```
   uniq -w 5 file.txt
   ```

## Additional Options

8. `--group[=METHOD]`: 
   Show all items, separating groups with an empty line.

9. `-z, --zero-terminated`: 
   Line delimiter is NUL, not newline.

10. `-D`: 
    Print all duplicate lines.

11. `--all-repeated[=METHOD]`: 
    Like -D, but allow separating groups with an empty line.

12. `-N, --check-chars=N`: 
    Compare only the first N characters. Synonym for -w.

## Usage Examples

1. Basic usage (remove adjacent duplicate lines):
   ```
   uniq input.txt output.txt
   ```

2. Count occurrences of lines:
   ```
   sort file.txt | uniq -c
   ```

3. Display only duplicate lines:
   ```
   uniq -d file.txt
   ```

4. Display only unique lines:
   ```
   uniq -u file.txt
   ```

5. Ignore case when comparing lines:
   ```
   uniq -i file.txt
   ```

6. Skip the first field when comparing:
   ```
   uniq -f 1 file.txt
   ```

7. Skip the first 3 characters when comparing:
   ```
   uniq -s 3 file.txt
   ```

8. Compare only the first 5 characters:
   ```
   uniq -w 5 file.txt
   ```

9. Combine with sort to find unique lines in unsorted file:
   ```
   sort file.txt | uniq
   ```

10. Find duplicate lines in a file:
    ```
    sort file.txt | uniq -d
    ```

11. Count occurrences of lines, sorted by most frequent:
    ```
    sort file.txt | uniq -c | sort -nr
    ```

12. Ignore case and count occurrences:
    ```
    sort file.txt | uniq -ic
    ```

13. Display all duplicate lines:
    ```
    uniq -D file.txt
    ```

14. Group output with empty lines between groups:
    ```
    sort file.txt | uniq --group
    ```

15. Combine multiple options:
    ```
    sort file.txt | uniq -c -w 10 -i
    ```

Remember that 'uniq' only works on sorted input for comparing and removing duplicates across the entire file. That's why it's often used in combination with the 'sort' command. The 'uniq' command is particularly useful for data processing tasks, log file analysis, and any scenario where you need to identify or remove duplicate entries.
