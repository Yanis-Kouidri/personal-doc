# Curl

## Perform HTTP request

Basic in stdout

```bash
curl https://example.com
```

Save into a file

```bash
curl -o file.txt https://example.com
```

Follow redirections (301/302)

```bash
curl -L https://example.com
```

Print only HTTP headers

```bash
curl -I https://example.com
```

Force IPv4

```bash
curl -4 https://example.com
```

Force IPv6

```bash
curl -6 https://example.com
```

Use verbose output

```bash
curl -v https://example.com
```
