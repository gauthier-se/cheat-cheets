# ipcalc — IP Calculator

Perform simple manipulation and calculation of IP addresses and subnet masks.

```bash
ipcalc 192.168.1.1/24
```

## Options

| Command | Description |
| :--- | :--- |
| `-n` | Show the network address |
| `-b` | Show the broadcast address |
| `-m` | Show the subnet mask |
| `-p` | Show the prefix (e.g., /24) |

## Examples

```bash
# 1. Display all information about an IP and its subnet
ipcalc 192.168.1.100/24
# Outputs: Address, Netmask, Wildcard, Network, HostMin, HostMax, Broadcast, Hosts/Net

# 2. Extract just the Network address
ipcalc -n 192.168.1.50/26

# 3. Show binary representation of the IP and mask
ipcalc -b 10.0.0.1/8
```
