# killall Command Guide

## Basic Syntax

```
killall [options] name ...
```

## Purpose

The `killall` command is used to kill processes by name. It sends a signal to all processes running any of the specified commands. If no signal name is specified, SIGTERM is sent.

## Common Options

1. `-e, --exact`: Require an exact match for very long names
2. `-I, --ignore-case`: Case insensitive process name match
3. `-g, --process-group`: Kill the process group to which the process belongs
4. `-i, --interactive`: Ask for confirmation before killing
5. `-l, --list`: List all known signal names
6. `-q, --quiet`: Don't print complaints if no processes were killed
7. `-r, --regexp`: Interpret process name as an extended regular expression
8. `-s, --signal SIGNAL`: Send this signal instead of SIGTERM
9. `-u, --user USER`: Kill only processes the specified user owns
10. `-v, --verbose`: Report if the signal was successfully sent
11. `-w, --wait`: Wait for all killed processes to die
12. `-y, --younger-than TIME`: Kill processes younger than TIME
13. `-o, --older-than TIME`: Kill processes older than TIME
14. `--version`: Display version information

## Examples

1. Kill all processes with a given name:
   ```
   killall firefox
   ```

2. Kill processes with case-insensitive name matching:
   ```
   killall -I firefox
   ```

3. Send a specific signal to processes:
   ```
   killall -s SIGKILL firefox
   ```

4. Kill processes owned by a specific user:
   ```
   killall -u username process_name
   ```

5. Kill processes interactively (with confirmation):
   ```
   killall -i process_name
   ```

6. Kill processes using a regular expression:
   ```
   killall -r 'python[23]'
   ```

7. Kill processes younger than a specific time:
   ```
   killall -y 5m process_name
   ```

8. Kill processes older than a specific time:
   ```
   killall -o 1h process_name
   ```

9. Wait for all killed processes to die:
   ```
   killall -w process_name
   ```

10. List all known signal names:
    ```
    killall -l
    ```

11. Kill all processes in a specific process group:
    ```
    killall -g process_name
    ```

12. Use verbose output to confirm signal sent:
    ```
    killall -v process_name
    ```

13. Kill multiple processes at once:
    ```
    killall process1 process2 process3
    ```

14. Kill a process with exact name matching:
    ```
    killall -e long_process_name
    ```

15. Combine options for more specific targeting:
    ```
    killall -iv -u username -y 10m process_name
    ```

Remember to use `killall` with caution, especially when running as root, as it can terminate critical system processes. Always verify the processes you intend to kill before executing the command. For the most up-to-date and complete information, consult the manual (`man killall`) or the official documentation of your specific Linux distribution.
