# GPG-Memento

A short review of the command gpg to encrypt files

GPG (**G**NU **P**rivacy **G**uard) is a free version of PGP (**P**retty **G**ood **P**rivacy) software suite. It is used to encrypt and sign data.

Here we are going to see the command line tool integrated with GPG.
> In GUI mode a window will appear to ask the passphrase, in console mode a sem-GUI window will prompt.

### Prerequisite : 

If GPG isn't installed, you can do it via these commands :

```
apt install gpg -y
```
<i>For Debian distributions or</i>
```
dnf install gpg -y
```
<i>For RedHat ones</i>

## Encrypt file

To encrypt file we can use this command :  
`gpg -c fileName`

It will ask to write two times a passphrase. Afterwards, a new file with the extension **.gpg** is created : it is the encrypted file.

## Decrypt file

Now we can decrypt this file with this command :  
`gpg -d fileName.gpg`

> If we decrypt the second time in the same session, it won't ask us the passphrase because gpg agent has memorised the passphrase we had entered. It will ask us if we close our session. Or we can use this command to clear the cache : `gpgconf --reload gpg-agent`

If we want to save the decrypted file we can use the -o option :  
`gpg -o fileName -d gileName.gpg`

## Encrypt and decrypt in a script (batch mode)

If we want to use gpg in a script it is usefull to directly enter the passphrase in the command.
To encrypt directly with the passphrase :  
`gpg  --batch --passphrase thePassphrase -c fileName`

To decrypt directly with the passphrase and save it :  
`gpg  --batch --passphrase thePassphrase -o fileName  -d fileName.gpg`

___
Updated : 30/08/2022, Author : AnthonyF
