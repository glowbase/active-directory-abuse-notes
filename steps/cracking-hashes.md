# Cracking Hashes
## TGT
ASREPRoast
```bash
hashcat -m 18200 -a 0 hashes.asreproast /usr/share/wordlists/rockyou.txt --force
```

## SPN
Kerberoasting
```bash
hashcat -m 13100 -a 0 hashes.kerberoast /usr/share/wordlists/rockyou.txt --force
```