# Active Directory Abuse
A collection of notes for exploiting and abusing Active Directory environments.

## What have you got?
- [Nothing](steps/no-credentials.md)
- [Username](steps/got-username.md)
- [Credentials](steps/got-credentials.md)
- [Hashes](steps/cracking-hashes.md)
- [Administrator](steps/got-administrator.md)

### Quick Brain Dump
- Try RPC null authentication (`enumdomusers`, `querydispfinfo`)
- List SMB shares
- LDAP password attributes (`ldapsearch`)
- GetUserSPNs
- GetNPUsers
- Check SMB after finding credentials (`crackmapexec`)
- Bloodhound = Lord and Saviour