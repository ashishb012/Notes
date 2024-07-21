# Comprehensive Guide to the 'ps' Command

[Back to Linux Commands](../readme.md)

The 'ps' command in Unix and Linux systems is used to provide information about currently running processes. The name 'ps' stands for "process status".

## Basic Syntax

```
ps [options]
```

## Option Styles

ps accepts several styles of options:

1. UNIX options, which may be grouped and must be preceded by a dash
2. BSD options, which may be grouped and must not be used with a dash
3. GNU long options, which are preceded by two dashes

## Common Options

### UNIX Options

1. `-e`: Select all processes
   ```
   ps -e
   ```

2. `-f`: Full-format listing
   ```
   ps -ef
   ```

3. `-l`: Long format
   ```
   ps -l
   ```

4. `-u username`: Select by effective user ID or name
   ```
   ps -u root
   ```

### BSD Options

5. `a`: Show processes for all users
   ```
   ps a
   ```

6. `u`: Display the process's user/owner
   ```
   ps u
   ```

7. `x`: Show processes without controlling ttys
   ```
   ps ax
   ```

### GNU Long Options

8. `--sort`: Specify sorting order
   ```
   ps --sort=-pcpu
   ```

9. `--forest`: Show process hierarchy
   ```
   ps --forest
   ```

10. `--headers`: Repeat header lines, one per page of output
    ```
    ps --headers
    ```

## Additional Options

11. `-C cmdlist`: Select by command name
    ```
    ps -C sshd
    ```

12. `-o format`: User-defined format
    ```
    ps -eo pid,ppid,cmd
    ```

13. `-p pidlist`: Select by process ID
    ```
    ps -p 1234,5678
    ```

14. `--ppid`: Select by parent process ID
    ```
    ps --ppid 1234
    ```

15. `r`: Restrict the selection to only running processes
    ```
    ps r
    ```

16. `T`: Select all processes associated with this terminal
    ```
    ps T
    ```

17. `--no-headers`: Print no header line at all
    ```
    ps --no-headers
    ```

18. `--width`: Set the screen width
    ```
    ps --width 100
    ```

19. `--context`: Display security context format (for SELinux)
    ```
    ps --context
    ```

20. `--cols n`: Set screen width
    ```
    ps --cols 120
    ```

## Usage Examples

1. Display all processes:
   ```
   ps -e
   ```

2. Display all processes with full details:
   ```
   ps -ef
   ```

3. Display processes for a specific user:
   ```
   ps -u username
   ```

4. Display processes with a specific PID:
   ```
   ps -p 1234
   ```

5. Display processes and sort by memory usage:
   ```
   ps aux --sort=-%mem
   ```

6. Display processes and sort by CPU usage:
   ```
   ps aux --sort=-%cpu
   ```

7. Display process tree:
   ```
   ps -ejH
   ```
   or
   ```
   ps axjf
   ```

8. Display security information:
   ```
   ps -eo pid,user,group,args,etime,lstart
   ```

9. Display only process IDs:
   ```
   ps -eo pid
   ```

10. Display processes with specific columns:
    ```
    ps -eo pid,ppid,cmd,%cpu,%mem --sort=-%cpu
    ```

11. Display processes for a specific command:
    ```
    ps -C firefox
    ```

12. Display processes with threads:
    ```
    ps -eLf
    ```

13. Display processes without a controlling terminal:
    ```
    ps ax
    ```

14. Display processes with real-time priority:
    ```
    ps -eo pid,user,pri,rtprio,command
    ```

15. Display processes owned by root:
    ```
    ps -U root -u root u
    ```

16. Display processes excluding grep command:
    ```
    ps aux | grep '[h]ttpd'
    ```

17. Display top CPU consuming processes:
    ```
    ps aux --sort=-%cpu | head -n 10
    ```

18. Display top memory consuming processes:
    ```
    ps aux --sort=-%mem | head -n 10
    ```

19. Display process start time and running time:
    ```
    ps -eo pid,cmd,etime,etimes
    ```

20. Display security context (SELinux):
    ```
    ps -eZ
    ```

Remember, the 'ps' command provides a snapshot of the current processes. For continuous monitoring, you might want to use commands like 'top' or 'htop'. Also, different Unix-like systems might have slight variations in the available options and their exact behavior.

[Back to Linux Commands](../readme.md)
