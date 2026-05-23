# ssh — Secure Shell

Secure encrypted connection to a remote machine over a network.

```bash
ssh user@hostname
```

## Options

| Command | Description |
| :--- | :--- |
| `-p <port>` | Connect to a specific port (default is 22) |
| `-i <key>` | Use a specific private key file |
| `-X` | Enable X11 forwarding (run GUI apps remotely) |
| `-v` | Verbose mode (useful for debugging connection issues) |

## Port Forwarding (Tunnels)

| Command | Description |
| :--- | :--- |
| `-L 8080:localhost:80` | **Local Forwarding**: Access a remote port (80) locally (on 8080) |
| `-R 8080:localhost:80` | **Remote Forwarding**: Expose your local port (80) to the remote server (on 8080) |
| `-D 1080` | **Dynamic Forwarding**: Creates a SOCKS proxy on your local port 1080 |

## SSH Keys

```bash
# 1. Generate a new SSH key (Ed25519 is the modern standard)
ssh-keygen -t ed25519 -C "your_email@example.com"

# 2. Copy your public key to a remote server (allows passwordless login)
ssh-copy-id user@hostname

# 3. Add a private key to the SSH agent (so you don't type the password)
ssh-add ~/.ssh/id_ed25519
```

## Useful Config (`~/.ssh/config`)

You can create an `~/.ssh/config` file to save connection details:

```text
Host myserver
    HostName 192.168.1.50
    User admin
    Port 2222
    IdentityFile ~/.ssh/id_ed25519_custom
```
*Then, simply type `ssh myserver` to connect.*
