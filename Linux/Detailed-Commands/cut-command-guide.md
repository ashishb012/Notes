# Comprehensive Guide to the 'cut' Command

[Back to Linux Commands](../readme.md)

The 'cut' command in Unix and Linux is used to extract sections from each line of input (usually a file). It can select columns or fields based on delimiter, character positions, or byte positions.

## Basic Syntax

```
cut OPTION... [FILE]...
```

## Common Options

1. `-f, --fields=LIST`: 
   Select only these fields.

   Example:
   ```
   cut -f 1,3 file.txt
   ```

2. `-d, --delimiter=DELIM`: 
   Use DELIM instead of TAB for field delimiter.

   Example:
   ```
   cut -d ',' -f 2 file.csv
   ```

3. `-c, --characters=LIST`: 
   Select only these characters.

   Example:
   ```
   cut -c 1-5 file.txt
   ```

4. `-b, --bytes=LIST`: 
   Select only these bytes.

   Example:
   ```
   cut -b 1-10 file.bin
   ```

5. `--complement`: 
   Complement the set of selected bytes, characters or fields.

   Example:
   ```
   cut -f 2 --complement file.txt
   ```

6. `-s, --only-delimited`: 
   Do not print lines not containing delimiters.

   Example:
   ```
   cut -d ',' -s -f 1 file.csv
   ```

7. `--output-delimiter=STRING`: 
   Use STRING as the output delimiter instead of the input delimiter.

   Example:
   ```
   cut -d ',' -f 1,2 --output-delimiter=':' file.csv
   ```

## Additional Options

8. `--help`: 
   Display help information and exit.

9. `--version`: 
   Output version information and exit.

## Usage Examples

1. Extract the first field (column) from a tab-delimited file:
   ```
   cut -f 1 file.txt
   ```

2. Extract the second and fourth fields from a comma-separated file:
   ```
   cut -d ',' -f 2,4 file.csv
   ```

3. Extract characters 3 to 7 from each line:
   ```
   cut -c 3-7 file.txt
   ```

4. Extract the first 10 bytes from a binary file:
   ```
   cut -b 1-10 file.bin
   ```

5. Extract all fields except the second one:
   ```
   cut -f 2 --complement file.txt
   ```

6. Extract the first three characters from each line:
   ```
   cut -c -3 file.txt
   ```

7. Extract from the 5th character to the end of each line:
   ```
   cut -c 5- file.txt
   ```

8. Use a different output delimiter:
   ```
   cut -d ',' -f 1,2 --output-delimiter=':' file.csv
   ```

9. Extract fields 1-3 and 5:
   ```
   cut -f 1-3,5 file.txt
   ```

10. Extract odd-numbered fields:
    ```
    cut -f 1,3,5,7,9 file.txt
    ```

11. Extract fields with a space delimiter:
    ```
    cut -d ' ' -f 2,3 file.txt
    ```

12. Extract the first 16 bytes in hexadecimal format:
    ```
    cut -b 1-16 file.bin | xxd -g 1
    ```

13. Extract fields and change delimiter in one command:
    ```
    cut -d ',' -f 1,3 --output-delimiter=' : ' file.csv
    ```

14. Extract fields from multiple files:
    ```
    cut -f 1 file1.txt file2.txt file3.txt
    ```

15. Use with pipeline to process command output:
    ```
    ls -l | cut -d ' ' -f 5,9
    ```

Remember that 'cut' is particularly useful for processing structured text files, log files, and in shell scripts for data extraction. It's often used in combination with other commands like 'grep', 'sort', and 'uniq' for more complex text processing tasks.

[Back to Linux Commands](../readme.md)
