# Test repository

This repository is purely for testing settings, and ensuring the setup is right, without making multiple commits on the main code base.

## Adding SSH signing support to your configuration
GitHub allows you to configure an ssh key as a `Signing key`. This is useful from a Mac, as they do not allow GPG signing on a forwarded connection for security reasons.

On the remote machine in `~/.gitconfig`
```
[user]
    signingkey = ~/.ssh/signing_key.pub
[commit]
    gpgsign = true
[gpg]
    program = /usr/local/bin/gpg
    format = ssh
[gpg "ssh"]
    allowedSignersFile = /home/daren/.config/git/allowed_signers
```

Copy the key from your mac to the remote server, note it's named `signing_key.pub` to avoid it being confused with other ssh keys that may be created.
