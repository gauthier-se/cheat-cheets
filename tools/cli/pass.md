# pass — Password Manager

Command-line password manager, encrypted with GPG.

```bash
# Initialize the store
pass init "my-email@example.com"

# Add a password
pass insert Email/personal

# Generate a random password (20 characters)
pass generate Web/github 20

# Display a password
pass Email/personal

# Copy to clipboard (clears after 45s)
pass -c Email/personal

# List all passwords
pass

# Search
pass find github
```

```bash
brew install pass
```
