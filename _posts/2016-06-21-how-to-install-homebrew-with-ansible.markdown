---
layout: post
title: "How to install Homebrew with Ansible"
date: "2016-06-21 15:04:04 +0300"
permalink: /:title
---

I've tried shell, command and https://github.com/geerlingguy/ansible-role-homebrew
but here is the answer. File structure.

```
roles/brew
├── files
│   └── install-homebrew.sh
└── tasks
    └── main.yml
```

main.yml

```yaml
---
- name: Check if Homebrew is already installed
  stat:
    path: /usr/local/bin/brew
  register: b

  - name: Install Homebrew
    script: install-homebrew.sh
    when: not b.stat.exists
```

install-homebrew.sh

```bash
#!/bin/bash
yes | /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Problems with other ways to do it

curl command prompts user something so we need to add `yes` to pass *y*

This means we cannot use Ansible command module, because pipe is not supported.

Shell module seems to run the command properly, but for some reason it does not
exit ever (perhaps because `yes` runs forever).
