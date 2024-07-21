# The `ip` Command

The `ip` command is a powerful and versatile networking tool used in Linux systems for configuring and managing network interfaces, routing, and tunnels. It's part of the iproute2 package and is considered the modern replacement for older networking commands like `ifconfig`, `route`, and `arp`.

## Basic Syntax

```
ip [ OPTIONS ] OBJECT { COMMAND | help }
```

Where OBJECT can be one of: `link`, `address`, `route`, `neigh`, `tunnel`, `maddress`, `mroute`, `mrule`, `monitor`, `xfrm`, `netns`, `l2tp`, `tcp_metrics`, `token`, `macsec`, and more.

## Common Objects and Their Uses

1. `link`: Network device configuration
2. `address` (or `addr`): Protocol address management
3. `route`: Routing table management
4. `neigh`: Neighbor/ARP tables management
5. `tunnel`: Tunnel configuration
6. `maddress`: Multicast address management
7. `netns`: Network namespace management

## Common Options

- `-4`: Use IPv4
- `-6`: Use IPv6
- `-s`: Display more detailed (statistics) information
- `-r`: Use basic output format
- `-b`: Print the broadcast address
- `-c`: Continuous output (for monitor object)

## Examples

1. Show information for all network interfaces:
   ```
   $ ip link show
   ```

2. Show IP addresses for all interfaces:
   ```
   $ ip addr show
   ```

3. Show information for a specific interface:
   ```
   $ ip addr show dev eth0
   ```

4. Bring an interface up or down:
   ```
   $ ip link set eth0 up
   $ ip link set eth0 down
   ```

5. Assign an IP address to an interface:
   ```
   $ ip addr add 192.168.1.100/24 dev eth0
   ```

6. Remove an IP address from an interface:
   ```
   $ ip addr del 192.168.1.100/24 dev eth0
   ```

7. Show the routing table:
   ```
   $ ip route show
   ```

8. Add a static route:
   ```
   $ ip route add 10.0.0.0/24 via 192.168.1.1
   ```

9. Delete a static route:
   ```
   $ ip route del 10.0.0.0/24
   ```

10. Show the ARP cache:
    ```
    $ ip neigh show
    ```

11. Add a static ARP entry:
    ```
    $ ip neigh add 192.168.1.100 lladdr 00:11:22:33:44:55 dev eth0
    ```

12. Flush the ARP cache for a specific interface:
    ```
    $ ip neigh flush dev eth0
    ```

13. Add an IPv6 address:
    ```
    $ ip -6 addr add 2001:db8::1/64 dev eth0
    ```

14. Show network statistics:
    ```
    $ ip -s link show dev eth0
    ```

15. Monitor network events:
    ```
    $ ip monitor
    ```

## Output Explanation

A typical `ip addr show` output looks like this:

```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 08:00:27:a6:bf:16 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.100/24 brd 192.168.1.255 scope global dynamic eth0
       valid_lft 86398sec preferred_lft 86398sec
    inet6 fe80::a00:27ff:fea6:bf16/64 scope link 
       valid_lft forever preferred_lft forever
```

- Interface flags: `<BROADCAST,MULTICAST,UP,LOWER_UP>`
- `mtu`: Maximum Transmission Unit
- `qdisc`: Queuing discipline
- `state`: Interface state (UP, DOWN, etc.)
- `link/ether`: MAC address
- `inet`: IPv4 address
- `inet6`: IPv6 address
- `scope`: Address scope (global, link, host)
- `valid_lft` and `preferred_lft`: Address lifetimes

## Notes

- The `ip` command typically requires root or sudo privileges for configuration changes.
- Changes made with `ip` are not persistent across reboots unless saved in network configuration files.
- The `ip` command is more powerful and flexible than older networking commands, offering a unified interface for various network-related tasks.
- For persistent changes, modify the appropriate network configuration files specific to your Linux distribution.
