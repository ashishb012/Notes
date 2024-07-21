# kill Command Guide

[Back to Linux Commands](../readme.md)

## Basic Syntax

```
kill [options] <pid> [...]
```

## Purpose

The `kill` command is used to send a signal to a process, typically to end the process. Despite its name, `kill` doesn't necessarily terminate a process - it sends a specified signal to a process, and the default signal (SIGTERM) requests that the process terminate gracefully.

## Warning

**Be cautious when using `kill`, especially with elevated privileges. Terminating essential system processes can lead to system instability or data loss.**

## Common Options

1. `-s, --signal <signal>`: Specify the signal to send (by name or number)
2. `-l, --list [signal]`: List signal names, or convert a signal number to a name
3. `-L, --table`: List signal names and numbers
4. `-n, --n-signal <n>`: Use signal number n
5. `-v, --verbose`: Be verbose
6. `-w, --timeout <seconds>`: Wait for specified processes to die
7. `-h, --help`: Display help information and exit
8. `-V, --version`: Output version information and exit

## Common Signals

1. SIGHUP (1): Hangup
2. SIGINT (2): Interrupt (same as Ctrl+C)
3. SIGQUIT (3): Quit
4. SIGKILL (9): Kill immediately (can't be caught or ignored)
5. SIGTERM (15): Terminate gracefully (default)
6. SIGSTOP (19): Stop process (can't be caught or ignored)
7. SIGCONT (18): Continue stopped process

## Examples

1. Terminate a process gracefully (default SIGTERM):
   ```
   kill 1234
   ```

2. Force kill a process (use with caution):
   ```
   kill -9 1234
   ```

3. Send a specific signal by name:
   ```
   kill -s SIGTERM 1234
   ```

4. Send a specific signal by number:
   ```
   kill -n 15 1234
   ```

5. Kill multiple processes:
   ```
   kill 1234 5678 9101
   ```

6. Kill a process group (notice the minus sign):
   ```
   kill -- -1234
   ```

7. List all available signals:
   ```
   kill -l
   ```

8. Convert a signal number to a name:
   ```
   kill -l 9
   ```

9. Be verbose (print the signal being sent):
   ```
   kill -v 1234
   ```

10. Wait for a process to die:
    ```
    kill -w 10 1234
    ```

11. Send SIGHUP (often used to reload configuration):
    ```
    kill -s SIGHUP 1234
    ```

12. Stop a process (can be continued later):
    ```
    kill -s SIGSTOP 1234
    ```

13. Continue a stopped process:
    ```
    kill -s SIGCONT 1234
    ```

14. Kill all processes by name using pkill (related command):
    ```
    pkill process_name
    ```

15. Kill the most recently started program:
    ```
    kill %1
    ```

## Safety Tips

1. Always verify the PID before killing a process.
2. Use `ps` or `top` commands to find the correct PID.
3. Prefer SIGTERM (default) over SIGKILL for graceful termination.
4. Be extremely cautious when using `kill` with sudo or as root.
5. Consider using safer alternatives like `pkill` or `killall` for targeting processes by name.

Remember to always consult the manual (`man kill`) or use `kill --help` for the most up-to-date and system-specific information, as options may vary slightly between different Unix-like systems.

[Back to Linux Commands](../readme.md)
