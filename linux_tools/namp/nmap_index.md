# NMAP

## List of contents

1. [Scan local network](scan-local-network)
2. [Brutforce ssh](brutforce-ssh)

### Scan local network

```bash
nmap -sn 192.168.0.1/24
```

### Brutforce ssh

```bash
nmap 192.168.0.1 -p 22 ssh-brute --script-args userdb=users.txt,passdb=pssw.txt
```