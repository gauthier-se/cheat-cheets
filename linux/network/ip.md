# ip — Network Configuration

The modern replacement for `ifconfig` and `route`. Used to show or manipulate routing, network devices, interfaces, and tunnels.

```bash
ip addr
```

## Finding Your IP Address

```bash
# 1. Show private IP addresses of all interfaces
ip a
# Or short for 'ip addr show'

# 2. Show only IPv4 addresses (cleaner output)
ip -4 a

# 3. Get your PUBLIC IP address from the terminal
curl ifconfig.me
# Alternative: curl ipinfo.io/ip
```

## Gateway & Routing

```bash
# 1. Show the routing table (to find your default gateway/router IP)
ip route

# 2. Add a new default gateway (requires sudo)
ip route add default via 192.168.1.254

# 3. Delete a default gateway
ip route del default via 192.168.1.254
```

## Interfaces & Link State

```bash
# 1. Show the status of all network links (UP/DOWN, MAC addresses)
ip link

# 2. Bring an interface UP (e.g., eth0)
sudo ip link set eth0 up

# 3. Bring an interface DOWN
sudo ip link set eth0 down
```

## Other Useful Network Commands

| Command | Description |
| :--- | :--- |
| `ss -tuln` | Modern replacement for `netstat`. Show listening TCP/UDP ports |
| `traceroute <ip>` | Trace the path packets take to a network host |
| `mtr <ip>` | Combines `ping` and `traceroute` into a live updating dashboard |
