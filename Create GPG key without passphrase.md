GPG cli requires you to put passphrase on the key since 2.2+. If you want to avoid using passphrase, you must use `--pinentry-mode=loopback`

`gpg --full-gen-key --passphrase '' --pinentry-mode=loopback`
