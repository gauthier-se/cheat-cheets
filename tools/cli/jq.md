# jq — JSON Processor

Filters, transforms, and formats JSON from the command line.

```bash
# Format JSON
echo '{"a":1,"b":2}' | jq .

# Extract a field
cat data.json | jq '.name'

# Filter an array
cat users.json | jq '.[] | select(.age > 25)'

# Transform structure
cat data.json | jq '{name: .name, city: .address.city}'

# Count elements
cat items.json | jq 'length'

# Extract keys
cat config.json | jq 'keys'

# First element of an array
cat data.json | jq '.[0]'

# Raw output (without quotes)
cat data.json | jq -r '.name'
```

```bash
brew install jq
```
