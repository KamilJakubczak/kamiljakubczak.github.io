# NMAP

## List of contents

- [NMAP](#nmap)
  - [List of contents](#list-of-contents)
    - [Scan local network](#scan-local-network)
    - [Brutforce ssh](#brutforce-ssh)

### Scan local network

```bash
nmap -sn 192.168.0.1/24
```

### Brutforce ssh

```bash
nmap 192.168.0.1 -p 22 ssh-brute --script-args userdb=users.txt,passdb=pssw.txt
```