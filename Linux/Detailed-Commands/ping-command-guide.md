# The `ping` Command

[Back to Linux Commands](../readme.md)

The `ping` command is a network administration utility used to test the reachability of a host on an Internet Protocol (IP) network and to measure the round-trip time for messages sent from the originating host to a destination computer.

## Basic Syntax

```
ping [options] destination
```

## Common Options

1. `-c count`: Stop after sending (and receiving) count packets
2. `-i interval`: Wait interval seconds between sending each packet
3. `-s packetsize`: Specifies the number of data bytes to be sent
4. `-t ttl`: Set the IP Time to Live
5. `-W timeout`: Time to wait for a response, in seconds
6. `-v`: Verbose output
7. `-4`: Use IPv4 only
8. `-6`: Use IPv6 only

Note: Available options may vary slightly between different operating systems.

## Examples

1. Basic ping to a domain:
   ```
   $ ping google.com
   ```

2. Ping with a specific number of packets:
   ```
   $ ping -c 5 192.168.1.1
   ```

3. Ping with a specific interval between packets:
   ```
   $ ping -i 2 example.com
   ```

4. Ping with a larger packet size:
   ```
   $ ping -s 1000 8.8.8.8
   ```

5. Ping with a specific timeout:
   ```
   $ ping -W 2 10.0.0.1
   ```

6. Ping using IPv6:
   ```
   $ ping -6 ipv6.google.com
   ```

7. Ping with verbose output:
   ```
   $ ping -v example.com
   ```

8. Ping with a specific TTL (Time To Live):
   ```
   $ ping -t 64 192.168.1.1
   ```

9. Continuous ping (until stopped with Ctrl+C):
   ```
   $ ping google.com
   ```

10. Ping sweep (checking multiple IPs):
    ```
    for ip in $(seq 1 10); do ping -c 1 192.168.1.$ip | grep "64 bytes"; done
    ```

## Output Explanation

A typical ping output looks like this:

```
PING google.com (172.217.16.142) 56(84) bytes of data.
64 bytes from fra16s11-in-f14.1e100.net (172.217.16.142): icmp_seq=1 ttl=118 time=10.6 ms
64 bytes from fra16s11-in-f14.1e100.net (172.217.16.142): icmp_seq=2 ttl=118 time=10.5 ms
64 bytes from fra16s11-in-f14.1e100.net (172.217.16.142): icmp_seq=3 ttl=118 time=10.7 ms
```

- `icmp_seq`: Sequence number of the packet
- `ttl`: Time To Live
- `time`: Round-trip time in milliseconds

## Common Use Cases

1. Testing network connectivity
2. Measuring network latency
3. Troubleshooting network issues
4. Checking if a server is up and responding
5. Network performance monitoring

## Notes

- `ping` uses ICMP (Internet Control Message Protocol) Echo Request and Echo Reply messages.
- Some networks or hosts may block ICMP traffic, making `ping` ineffective.
- Continuous pinging can be considered a form of DoS attack if not used responsibly.
- On Windows, `ping` stops after 4 packets by default. On Unix-like systems, it continues until stopped manually.
- Root or administrator privileges may be required for some advanced options.

[Back to Linux Commands](../readme.md)
