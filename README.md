playbook-go
===========

This ansible playbook aims to install `Go` in your \*nix box.

### USAGE

Just clone into your roles folder and then include it in your roles
listing:

```yml
- hosts: ...
  gather_facts: true                        # Unless rbenv is not provided
  roles:
    - role:     playbook-ruby
      rbenv_root:  /home/<the user>/.rbenv
      version:     2.1.2
```

**NOTES:**
- See [variable defaults](defaults/main.yml)
- If `rbenv_root` is not provided, it will build one based on the ansible
  user which will require setting `gather_facts` to true.

### LICENSE

The MIT License, [see](LICENSE.md).
