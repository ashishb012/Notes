# The `ss` Command

The `ss` (Socket Statistics) command is a powerful tool used to investigate sockets. It's a modern replacement for `netstat` and can display more TCP and state information than other tools.

## Basic Syntax

```
ss [options] [filter]
```

## Common Options

1. `-n`: Don't resolve service names
2. `-r`: Resolve numeric address/ports
3. `-a`: Display all sockets (listening and non-listening)
4. `-l`: Display only listening sockets
5. `-p`: Show process using the socket
6. `-t`: Display TCP sockets
7. `-u`: Display UDP sockets
8. `-x`: Display Unix domain sockets
9. `-4`: Display only IPv4 sockets
10. `-6`: Display only IPv6 sockets
11. `-0`: Display PACKET sockets
12. `-w`: Display RAW sockets
13. `-f FAMILY`: Display sockets of type FAMILY (unix, inet, inet6, link, netlink)
14. `-K`: Show kernel TCP memory usage
15. `-s`: Print summary statistics
16. `-E`: Continually display sockets as they are destroyed
17. `-Z`: Show process security context
18. `-z`: Show process in inode info
19. `-N NSNAME`: Switch to the specified network namespace

## State Filters

- `established`, `syn-sent`, `syn-recv`, `fin-wait-1`, `fin-wait-2`, `time-wait`, `closed`, `close-wait`, `last-ack`, `listening`, `closing`

## Examples

1. Show all TCP sockets:
   ```
   ss -t -a
   ```

2. Show all UDP sockets:
   ```
   ss -u -a
   ```

3. Show all established SSH connections:
   ```
   ss -o state established '( dport = :ssh or sport = :ssh )'
   ```

4. Show all listening TCP ports:
   ```
   ss -tl
   ```

5. Show all listening TCP ports with process info:
   ```
   ss -tlp
   ```

6. Show IPv4 socket summary:
   ```
   ss -s -4
   ```

7. Show all established connections:
   ```
   ss -t state established
   ```

8. Show all sockets connecting to a specific IP:
   ```
   ss dst 192.168.1.100
   ```

9. Show all sockets on a specific port:
   ```
   ss -tnlp sport = :80
   ```

10. Display timer information:
    ```
    ss -to
    ```

11. Show sockets in TIME-WAIT state:
    ```
    ss -t state time-wait
    ```

12. Show kernel TCP memory usage:
    ```
    ss -K
    ```

13. Continuously display new sockets:
    ```
    ss -tna --events
    ```

14. Show sockets with specific criteria:
    ```
    ss -tn src :80 or src :443
    ```

15. Display sockets of a specific process:
    ```
    ss -tlp | grep nginx
    ```

## Output Explanation

A typical `ss` output looks like this:

```
Netid  State   Recv-Q  Send-Q  Local Address:Port  Peer Address:Port  Process
tcp    ESTAB   0       0       192.168.1.2:ssh     192.168.1.100:52986
```

- `Netid`: Protocol (tcp, udp, raw, etc.)
- `State`: TCP state (LISTEN, ESTABLISHED, etc.)
- `Recv-Q`: Bytes in receive queue
- `Send-Q`: Bytes in send queue
- `Local Address:Port`: Local IP address and port number
- `Peer Address:Port`: Remote IP address and port number
- `Process`: Process ID and name (if -p option is used)

## Common Use Cases

1. Troubleshooting network issues
2. Monitoring network connections
3. Analyzing network traffic patterns
4. Identifying processes using specific ports
5. Investigating potential security issues
6. Performance tuning of network applications

## Notes

- The `ss` command typically requires root or sudo privileges for full functionality.
- It's more efficient and faster than `netstat`, especially on systems with many connections.
- The `ss` command can use various filters to display only the information you need.
- It can show detailed TCP state information, which is useful for advanced troubleshooting.
- The `-K` option for showing kernel socket memory usage is particularly useful for performance tuning.
- Use `man ss` for a complete list of options and more detailed information.
