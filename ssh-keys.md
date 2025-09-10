
### SSH Keys ###

GitHub has a good resource that shows the key setup steps - I've referred to this
many times as I forget the specific commands needed.

the steps in brief are:
- `ssh-keygen -t ed25519 -C "your_email@example.com"`
  - it will ask where to store it.. if you have multiple keys, do NOT
    accept the defaults!! give it a descriptive name instead
  - give it a passphrase - yes, do this, it is best practice
  - store this passphrase in a secure store somewhere
  - use the email address above to make a unique identity as the os uses this
    comment to determine what key to use
  - I used:
    - key "id": "david@router.lan"
    - key file: ~/.ssh/router_key

The instructions then go on to talk about adding the key to the ssh-agent.
My preference for some keys is to NOT add them to the agent as an aspect
of zero trust. I want the system to ask me for that password.

What if my login session is compromized?
- sudo is always password protected
- having immediate access to ssh keys for important systems would be bad

Keys that are used VERY frequently I do tend to add them to the agent.
- github, gitlab keys


