# The `ifconfig` Command

[Back to Linux Commands](../readme.md)

The `ifconfig` (interface configuration) command is used to configure, control, and query network interface parameters in Unix-like operating systems. It's primarily used for viewing and modifying network interface configurations.

Note: On many modern Linux distributions, `ifconfig` is being replaced by the `ip` command, but `ifconfig` is still widely used and available.

## Basic Syntax

```
ifconfig [interface] [options]
```

## Common Options

1. `up`: Activate the interface
2. `down`: Deactivate the interface
3. `[-]arp`: Enable or disable the use of ARP protocol
4. `[-]promisc`: Enable or disable promiscuous mode
5. `[-]allmulti`: Enable or disable all-multicast mode
6. `mtu N`: Set MTU (Maximum Transmission Unit) to N
7. `netmask addr`: Set netmask address
8. `add addr`: Add IPv6 address
9. `del addr`: Delete IPv6 address

## Examples

1. Display information for all interfaces:
   ```
   $ ifconfig
   ```

2. Display information for a specific interface:
   ```
   $ ifconfig eth0
   ```

3. Activate an interface:
   ```
   $ ifconfig eth0 up
   ```

4. Deactivate an interface:
   ```
   $ ifconfig eth0 down
   ```

5. Assign IP address and netmask:
   ```
   $ ifconfig eth0 192.168.1.100 netmask 255.255.255.0
   ```

6. Change MAC address:
   ```
   $ ifconfig eth0 hw ether 00:11:22:33:44:55
   ```

7. Enable promiscuous mode:
   ```
   $ ifconfig eth0 promisc
   ```

8. Disable promiscuous mode:
   ```
   $ ifconfig eth0 -promisc
   ```

9. Set MTU:
   ```
   $ ifconfig eth0 mtu 1500
   ```

10. Add IPv6 address:
    ```
    $ ifconfig eth0 add 2001:db8::1/64
    ```

11. Remove IPv6 address:
    ```
    $ ifconfig eth0 del 2001:db8::1/64
    ```

12. Enable multicast mode:
    ```
    $ ifconfig eth0 allmulti
    ```

## Output Explanation

A typical `ifconfig` output looks like this:

```
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.1.100  netmask 255.255.255.0  broadcast 192.168.1.255
        inet6 fe80::a00:27ff:fe1e:826c  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:1e:82:6c  txqueuelen 1000  (Ethernet)
        RX packets 54071  bytes 7137365 (6.8 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 47923  bytes 4187911 (3.9 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

- `flags`: Interface flags (UP, BROADCAST, RUNNING, MULTICAST)
- `mtu`: Maximum Transmission Unit
- `inet`: IPv4 address
- `netmask`: Subnet mask
- `broadcast`: Broadcast address
- `inet6`: IPv6 address
- `ether`: MAC address
- `RX packets`: Received packets statistics
- `TX packets`: Transmitted packets statistics

## Common Use Cases

1. Viewing network interface configurations
2. Configuring IP addresses and netmasks
3. Enabling or disabling network interfaces
4. Changing MAC addresses
5. Modifying interface parameters like MTU
6. Troubleshooting network connectivity issues

## Notes

- `ifconfig` typically requires root or sudo privileges for configuration changes.
- On many modern systems, `ifconfig` is considered deprecated in favor of the `ip` command.
- The exact options and output may vary slightly between different Unix-like operating systems.
- Changes made with `ifconfig` are typically not persistent across reboots. For persistent changes, modify the appropriate network configuration files.

[Back to Linux Commands](../readme.md)
