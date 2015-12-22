ruby
====

[![travis](https://travis-ci.org/joiggama/ansible-ruby.svg?branch=master)](https://travis-ci.org/joiggama/ansible-ruby)
[![gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/joiggama/ansible-ruby)

This ansible role aims to install ruby on ubuntu systems.

Requirements
------------

None.

Role Variables
--------------

| Name                      | Default                             |                                             |
|:-------------------------:|:-----------------------------------:|:-------------------------------------------:|
| ruby_default_version      |                                     | Default ruby version (rbenv global)         |
| ruby_forbid_gem_docs      | true                                | Wheter or not to install gem docs           |
| rbenv_root                | {{ ansible_env.HOME }}/.rbenv       | Install path for rbenv                      |
| rbenv_version             | master                              | Install version of rbenv (via facts)        |
| ruby_build_root           | {{ rbenv_root }}/plugins/ruby-build | Install path for rbenv                      |
| ruby_build_version        | master                              | Install version of ruby-build               |
| ruby_version              | 2.2.3                               | Ruby version to install (ruby-build format) |

**NOTE:** Some of these defaults require facts to be gathered.

Dependencies
------------

- [joiggama.rbenv](https://github.com/joiggama/ansible-rbenv)
- [joiggama.ruby-build](https://github.com/joiggama/ansible-ruby-build)

**NOTE:** This role already provides [sane defaults](#role-variables) for these dependencies.

Example Playbook
----------------

```yml
- gather_facts: true
  hosts:        all
  roles:
    - ansible-ruby
```

License
-------

[MIT](LICENSE.md)
