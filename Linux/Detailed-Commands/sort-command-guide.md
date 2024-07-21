# Comprehensive Guide to the 'sort' Command

[Back to Linux Commands](../readme.md)

The 'sort' command in Unix and Linux is used to sort lines of text files. It supports sorting alphabetically, numerically, by month, or based on a specific field in the file.

## Basic Syntax

```
sort [OPTIONS] [FILE(s)]
```

## Common Options

1. `-n, --numeric-sort`: 
   Sort numerically (use numeric value).

   Example:
   ```
   sort -n numbers.txt
   ```

2. `-r, --reverse`: 
   Reverse the result of comparisons.

   Example:
   ```
   sort -r file.txt
   ```

3. `-f, --ignore-case`: 
   Ignore case when sorting.

   Example:
   ```
   sort -f names.txt
   ```

4. `-u, --unique`: 
   Output only the first of an equal run.

   Example:
   ```
   sort -u duplicates.txt
   ```

5. `-k, --key=POS1[,POS2]`: 
   Start a key at POS1, end it at POS2 (origin 1).

   Example:
   ```
   sort -k 2 employee_data.txt
   ```

6. `-o, --output=FILE`: 
   Write result to FILE instead of standard output.

   Example:
   ```
   sort -o sorted_output.txt input.txt
   ```

7. `-M, --month-sort`: 
   Compare (unknown) < 'JAN' < ... < 'DEC'.

   Example:
   ```
   sort -M dates.txt
   ```

8. `-h, --human-numeric-sort`: 
   Compare human readable numbers (e.g., 2K 1G).

   Example:
   ```
   sort -h sizes.txt
   ```

## Additional Options

9. `-b, --ignore-leading-blanks`: 
   Ignore leading blanks.

10. `-d, --dictionary-order`: 
    Consider only blanks and alphanumeric characters.

11. `-g, --general-numeric-sort`: 
    Compare according to general numerical value.

12. `-i, --ignore-nonprinting`: 
    Consider only printable characters.

13. `-R, --random-sort`: 
    Sort by random hash of keys.

14. `-V, --version-sort`: 
    Natural sort of (version) numbers within text.

15. `--parallel=N`: 
    Change the number of sorts run concurrently to N.

16. `--batch-size=NMERGE`: 
    Merge at most NMERGE inputs at once.

17. `--check, -c`: 
    Check whether input is sorted; do not sort.

18. `--compress-program=PROG`: 
    Compress temporary files with PROG.

19. `--debug`: 
    Annotate the part of the line used to sort.

20. `--files0-from=F`: 
    Read input from the files specified by NUL-terminated names in file F.

## Usage Examples

1. Basic sort (alphabetical):
   ```
   sort names.txt
   ```

2. Sort numerically:
   ```
   sort -n numbers.txt
   ```

3. Sort in reverse order:
   ```
   sort -r file.txt
   ```

4. Sort ignoring case:
   ```
   sort -f mixed_case.txt
   ```

5. Sort and remove duplicates:
   ```
   sort -u duplicates.txt
   ```

6. Sort based on second field (column):
   ```
   sort -k 2 employee_data.txt
   ```

7. Sort numerically based on third field:
   ```
   sort -k 3n data.txt
   ```

8. Sort by month:
   ```
   sort -M dates.txt
   ```

9. Sort human-readable numbers:
   ```
   sort -h sizes.txt
   ```

10. Sort and save output to a file:
    ```
    sort -o sorted_output.txt input.txt
    ```

11. Sort multiple files together:
    ```
    sort file1.txt file2.txt > sorted_combined.txt
    ```

12. Check if a file is already sorted:
    ```
    sort -c sorted_file.txt
    ```

13. Sort version numbers:
    ```
    sort -V versions.txt
    ```

14. Random sort:
    ```
    sort -R items.txt
    ```

15. Sort with multiple keys (first by 2nd field, then by 3rd field numerically):
    ```
    sort -k2,2 -k3,3n data.txt
    ```

Remember that 'sort' is very versatile and can be combined with other commands like 'uniq' for more complex data processing tasks. The ability to sort based on specific fields makes it particularly useful for working with structured data files.

[Back to Linux Commands](../readme.md)
