# netstat Command Guide

[Back to Linux Commands](../readme.md)

## Basic Syntax

```
netstat [options]
```

## Purpose

The `netstat` (network statistics) command is a useful tool for monitoring network connections and their status, routing tables, interface statistics, masquerade connections, and multicast memberships.

## Common Options

1. `-a`: Show both listening and non-listening sockets
2. `-l`: Show only listening sockets
3. `-t`: Display TCP connections
4. `-u`: Display UDP connections
5. `-n`: Show numerical addresses and port numbers, instead of hostnames and service names
6. `-p`: Show the PID and name of the program to which each socket belongs
7. `-r`: Display the kernel routing table
8. `-i`: Show network interface statistics
9. `-s`: Display summary statistics for each protocol
10. `-c`: Continuously list the information
11. `-e`: Display additional information (use with -e)
12. `-o`: Include timers
13. `-v`: Verbose mode
14. `-W`: Do not truncate IP addresses

## Examples

1. Display all active connections and their status:
   ```
   netstat -a
   ```

2. Show only listening TCP ports:
   ```
   netstat -tl
   ```

3. Display active internet connections with numeric addresses and port numbers:
   ```
   netstat -tn
   ```

4. Show statistics for all protocols:
   ```
   netstat -s
   ```

5. Display the routing table:
   ```
   netstat -r
   ```

6. Show network interface statistics:
   ```
   netstat -i
   ```

7. List all TCP connections and the program using them:
   ```
   netstat -tp
   ```

8. Continuously display active internet connections:
   ```
   netstat -tc
   ```

9. Show listening UDP ports:
   ```
   netstat -ul
   ```

10. Display all active UNIX domain sockets:
    ```
    netstat -ax
    ```

11. Show network statistics for a specific interface:
    ```
    netstat -i eth0
    ```

12. Display the state of all sockets:
    ```
    netstat -ant
    ```

13. Show multicast group memberships:
    ```
    netstat -g
    ```

14. Display network connections with process name and PID:
    ```
    sudo netstat -tulpn
    ```

15. Show network connections with timer information:
    ```
    netstat -to
    ```

Remember that on many modern Linux systems, `netstat` is considered deprecated and the `ss` command is recommended as its replacement. However, `netstat` is still widely used and available on most systems.

For the most up-to-date and complete information, always refer to the manual (`man netstat`) or the official documentation of your specific Linux distribution.

[Back to Linux Commands](../readme.md)
