ansible-bash_it
===============

Ansible role to deploy [bash-it](https://github.com/Bash-it/bash-it) framework -
a collection of community Bash commands ands scripts.

Usage
-----

Include the role, and specify the user you want to install the bash_it for.
Note: The role will change the default shell for the user to be `/bin/bash`.

| Variable    | Default value                         | Description                      |
|-------------|---------------------------------------|----------------------------------|
| user        | {{ ansible_user_id }}                 | User to install bash-it for      | 
| theme       | pure                                  | Bash-it Theme to install         |
| aliases     | []                                    | A list of aliases to install     |
| plugins     | []                                    | A list of plugins to install     |
| completions | []                                    | A list of completions to install |
| repository  | https://github.com/revans/bash-it.git | Git repository for the bash-it   |
| version     | master                                | Git version tag to retrieve      |

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: mmannerm.ansible-bash_it
      user: vagrant
      aliases:
        - general
        - ansible
      plugins:
        - history
      completions:
        - git
```

License
-------

Apache 2.0

Author Information
------------------

Mika Mannermaa