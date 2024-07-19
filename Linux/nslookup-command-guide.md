# nslookup Command Guide

## Basic Syntax

```
nslookup [option] [name | -] [server]
```

## Purpose

`nslookup` (Name Server Lookup) is a network administration command-line tool for querying the Domain Name System (DNS) to obtain domain name or IP address mapping, or other DNS records.

## Modes

1. Interactive mode: Enter `nslookup` without arguments
2. Non-interactive mode: Provide arguments on the command line

## Common Options

1. `-query=type`: Set query type (e.g., A, AAAA, CNAME, MX, NS, PTR, SOA, TXT)
2. `-server=name`: Specify the name or IP address of the name server to use
3. `-debug`: Turn on debugging mode
4. `-port=value`: Specify the port number to use for the DNS query
5. `-timeout=number`: Set the number of seconds to wait for a reply
6. `-recurse`: Enable recursive query mode (default)
7. `-norecurse`: Disable recursive query mode
8. `-vc`: Use virtual circuit (TCP instead of UDP)
9. `-type=value`: Specify the type of information to be printed
10. `-help` or `-?`: Display brief help

## Examples

1. Basic domain lookup:
   ```
   nslookup example.com
   ```

2. Reverse DNS lookup:
   ```
   nslookup 93.184.216.34
   ```

3. Query a specific DNS server:
   ```
   nslookup example.com 8.8.8.8
   ```

4. Look up MX (mail exchanger) records:
   ```
   nslookup -type=mx example.com
   ```

5. Query for NS (name server) records:
   ```
   nslookup -type=ns example.com
   ```

6. Find all DNS records for a domain:
   ```
   nslookup -type=any example.com
   ```

7. Perform a reverse IPv6 lookup:
   ```
   nslookup -type=ptr 2001:db8::1
   ```

8. Query for AAAA (IPv6) records:
   ```
   nslookup -type=aaaa example.com
   ```

9. Look up TXT records:
   ```
   nslookup -type=txt example.com
   ```

10. Use TCP instead of UDP:
    ```
    nslookup -vc example.com
    ```

11. Set a custom timeout:
    ```
    nslookup -timeout=10 example.com
    ```

12. Disable recursive query:
    ```
    nslookup -norecurse example.com
    ```

13. Use debugging mode:
    ```
    nslookup -debug example.com
    ```

14. Query a specific port:
    ```
    nslookup -port=54 example.com
    ```

15. Interactive mode example:
    ```
    nslookup
    > server 8.8.8.8
    > set type=A
    > example.com
    > exit
    ```

## Tips

1. Use `server` in interactive mode to change the DNS server.
2. Use `set type` in interactive mode to change the query type.
3. Remember that `nslookup` is considered deprecated on some systems; consider using `dig` as an alternative.
4. Results may vary depending on your network configuration and the DNS servers used.
5. For security investigations, compare results from multiple DNS servers.

Remember to always consult the manual (`man nslookup`) or use `nslookup -help` for the most up-to-date and system-specific information, as options may vary slightly between different systems.
