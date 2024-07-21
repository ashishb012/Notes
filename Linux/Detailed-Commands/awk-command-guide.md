# Comprehensive Guide to the 'awk' Command

[Back to Linux Commands](../readme.md)

The 'awk' command is a powerful text-processing tool in Unix and Linux systems. It's named after its creators: Aho, Weinberger, and Kernighan. Awk is particularly useful for processing and analyzing structured text data.

## Basic Syntax

```
awk [options] 'program' file(s)
awk [options] -f programfile file(s)
```

## Common Options

1. `-F fs`: 
   Set the input field separator to fs. By default, it's whitespace.

   Example:
   ```
   awk -F: '{print $1}' /etc/passwd
   ```

2. `-v var=value`: 
   Assign value to variable var before program execution begins.

   Example:
   ```
   awk -v name="John" '{print "Hello, " name}' file.txt
   ```

3. `-f programfile`: 
   Read the AWK program source from file programfile.

   Example:
   ```
   awk -f script.awk data.txt
   ```

4. `-W option`: 
   Set various options. Common ones include:
   - `compat`: Run in compatibility mode
   - `dump-variables`: Print a sorted list of global variables to file
   - `lint`: Warn about questionable constructs
   - `posix`: Run in POSIX mode

   Example:
   ```
   awk -W lint '{print $1}' file.txt
   ```

## Additional Options

5. `-b, --characters-as-bytes`: 
   Treat all input data as single-byte characters.

6. `-c, --traditional`: 
   Run in compatibility mode.

7. `-C, --copyright`: 
   Print the copyright notice.

8. `-d[file], --dump-variables[=file]`: 
   Print sorted list of global variables to file or standard output.

9. `-e program-text`: 
   Use program-text as AWK program.

10. `-E file, --exec=file`: 
    Similar to -f, but uses 'file' as a program even if it starts with a '#'.

11. `-g, --gen-pot`: 
    Generate a GNU .pot (Portable Object Template) file.

12. `-h, --help`: 
    Print a help message.

13. `-L [fatal], --lint[=fatal]`: 
    Warn about questionable or non-portable constructs.

14. `-n, --non-decimal-data`: 
    Recognize octal and hexadecimal values.

15. `-N, --use-lc-numeric`: 
    Use locale's decimal point character when parsing input data.

16. `-O, --optimize`: 
    Enable optimizer.

17. `-p[file], --profile[=file]`: 
    Profile AWK program and send profile to file or standard output.

18. `-P, --posix`: 
    Run in strict POSIX compatibility mode.

19. `-r, --re-interval`: 
    Enable interval expressions in regexps.

20. `-S, --sandbox`: 
    Run in sandbox mode.

21. `-t, --lint-old`: 
    Warn about constructs that are not portable to the original version of UNIX awk.

22. `-V, --version`: 
    Print version information.

## AWK Program Structure

An AWK program typically consists of:

- BEGIN { ... } : Actions to be performed before processing input
- pattern { action } : Actions to be performed on matching lines
- END { ... } : Actions to be performed after processing input

## Built-in Variables

- `FS`: Input field separator (default: whitespace)
- `OFS`: Output field separator (default: space)
- `RS`: Input record separator (default: newline)
- `ORS`: Output record separator (default: newline)
- `NF`: Number of fields in the current record
- `NR`: Number of the current record
- `FNR`: Number of the current record in the current file
- `FILENAME`: Name of the current input file

## Usage Examples

1. Print specific fields:
   ```
   awk '{print $1, $3}' file.txt
   ```

2. Use a different field separator:
   ```
   awk -F: '{print $1}' /etc/passwd
   ```

3. Use built-in variables:
   ```
   awk '{print NR ":", $0}' file.txt
   ```

4. Use patterns to filter lines:
   ```
   awk '/pattern/ {print $0}' file.txt
   ```

5. Use comparison operators:
   ```
   awk '$3 > 100 {print $1, $3}' data.txt
   ```

6. Use BEGIN and END blocks:
   ```
   awk 'BEGIN {print "Start"} {print $0} END {print "End"}' file.txt
   ```

7. Use variables:
   ```
   awk '{sum += $1} END {print "Sum:", sum}' numbers.txt
   ```

8. Use if statements:
   ```
   awk '{if ($3 > 100) print $1, "High"; else print $1, "Low"}' data.txt
   ```

9. Use loops:
   ```
   awk '{for (i=1; i<=NF; i++) print $i}' file.txt
   ```

10. Use arrays:
    ```
    awk '{count[$1]++} END {for (word in count) print word, count[word]}' file.txt
    ```

11. Use multiple file inputs:
    ```
    awk 'FNR==1{print "File:",FILENAME} {print}' file1.txt file2.txt
    ```

12. Use functions:
    ```
    awk 'function max(x,y){return x>y?x:y} {print max($1,$2)}' data.txt
    ```

13. Use string manipulation:
    ```
    awk '{print substr($1,1,3)}' file.txt
    ```

14. Use regular expressions:
    ```
    awk '/^[0-9]+$/ {print "Number:", $0}' file.txt
    ```

15. Calculate average:
    ```
    awk '{sum+=$1; count++} END {print "Average:", sum/count}' numbers.txt
    ```

16. Print lines between two patterns:
    ```
    awk '/start/,/end/' file.txt
    ```

17. Replace field contents:
    ```
    awk '{gsub(/old/, "new", $2); print}' file.txt
    ```

18. Read command line variables:
    ```
    awk -v name="John" '{print "Hello, " name}' file.txt
    ```

19. Use system commands:
    ```
    awk '{system("echo " $0)}' file.txt
    ```

20. Format output:
    ```
    awk '{printf "%-10s %s\n", $1, $2}' file.txt
    ```

Remember, awk is a powerful tool for text processing and data extraction. It's particularly useful for working with structured data like CSV files or log files. When used in combination with other Unix commands, it can perform complex data manipulations efficiently.

[Back to Linux Commands](../readme.md)
