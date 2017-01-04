##My Pi

Inital run would assume basic setup up of Raspian OS and will need to be run with the `--ask-pass` flag, giving the 'pi' user's password (usually `raspberry` by default).

An `ansible.secret` file will need to be added to the root of the project containg the ansible-vault password if you have encrypted files that need to be included.

This should set up all necessary users with private/public ssh key authentication, meaning subsequent playbook runs won't need password authentication.

## Running the Playbook

Example command for PI:

```sh
# Install ansible-galaxy role dependencies
ansible-galaxy install -r requirements.yml
```

```sh
# Run 'my-pi' playbook
ansible-playbook -i hosts -u "pi" --vault-password-file=ansible.secret my-pi.yml --ask-pass --check --diff
```
