# pkill Command Guide: Options and Examples

The `pkill` command in Unix and Linux is used to send signals to processes based on their name or other attributes. It's a combination of `pgrep` and `kill`. Its basic syntax is:

```
pkill [OPTIONS] PATTERN
```

## Common Options

1. `-<signal>` or `-s <signal>`: Specify the signal to send (default is SIGTERM)
2. `-f`: Match against full command line instead of just the process name
3. `-n`: Select only the newest (most recently started) matching process
4. `-o`: Select only the oldest (least recently started) matching process
5. `-P <ppid>`: Only match processes whose parent process ID is ppid
6. `-g <pgrp>`: Only match processes in the process group with ID pgrp
7. `-t <term>`: Only match processes associated with terminal term
8. `-u <euid>`: Only match processes whose effective user ID is euid
9. `-U <uid>`: Only match processes whose real user ID is uid
10. `-x`: Only match processes whose name (or command line) exactly match the pattern
11. `-i`: Ignore case distinctions in both the pattern and the process names
12. `-v`: Negates the matching (selects processes that do not match)
13. `-w`: Use stricter matching for the command name
14. `-c`: Count the number of matched processes instead of sending a signal

## Examples

1. Basic usage (terminate processes by name):
   ```
   pkill firefox
   ```
   This sends the SIGTERM signal to all processes named "firefox".

2. Send a specific signal:
   ```
   pkill -9 chrome
   ```
   This sends the SIGKILL signal (9) to all processes named "chrome".

3. Match full command line:
   ```
   pkill -f "python script.py"
   ```
   This terminates all processes with "python script.py" in their command line.

4. Terminate the newest matching process:
   ```
   pkill -n java
   ```
   This terminates only the most recently started Java process.

5. Terminate processes for a specific user:
   ```
   pkill -u username
   ```
   This terminates all processes owned by "username".

6. Case-insensitive matching:
   ```
   pkill -i firefox
   ```
   This terminates processes named "firefox", "Firefox", "FIREFOX", etc.

7. Exact name matching:
   ```
   pkill -x bash
   ```
   This terminates processes named exactly "bash", but not "bash_script".

8. Terminate processes associated with a specific terminal:
   ```
   pkill -t pts/0
   ```
   This terminates all processes associated with the terminal pts/0.

9. Count matching processes:
   ```
   pkill -c nginx
   ```
   This counts the number of processes that match "nginx" without terminating them.

10. Terminate child processes of a specific parent:
    ```
    pkill -P 1234
    ```
    This terminates all child processes of the process with PID 1234.

11. Terminate processes in a specific process group:
    ```
    pkill -g 5678
    ```
    This terminates all processes in the process group 5678.

12. Negate the matching:
    ```
    pkill -v -u root
    ```
    This terminates all processes not owned by the root user.

13. Use with sudo for system-wide process management:
    ```
    sudo pkill httpd
    ```
    This terminates all Apache web server processes, requiring root privileges.

14. Terminate processes and their children:
    ```
    pkill -e --ns $$ firefox
    ```
    This terminates Firefox processes and their child processes within the current namespace.

Important Notes:
- `pkill` sends SIGTERM by default, which allows processes to exit gracefully. Use `-9` (SIGKILL) with caution as it forcefully terminates processes.
- Be careful when using `pkill` with broad patterns, as it might terminate important system processes.
- `pkill` is often used in scripts for automated process management.
- The `-f` option is particularly useful for identifying processes running specific scripts or commands.
- Always double-check the pattern before running `pkill`, especially when using it with sudo.
- `pkill` is related to `pgrep`, which finds processes but doesn't send signals.

