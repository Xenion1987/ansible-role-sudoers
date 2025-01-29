 Ansible role: sudoers
===

Manage user or group sudoers files on Linux systems.

Requirements
---

- Collections:
  - community.general
- Min. Ansible version: 2.11

Role Variables
---

main
---

| Variable | Type | Required | Choices | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `sudoers_install_sudo` | `bool` | `false` | `false`, `true` | `true` | Installs `sudo` if set to `true`. |
| `sudoers_manage_group_files` | `bool` | `false` | `false`, `true` | `false` | Enable or disable sudoers management for groups. |
| `sudoers_manage_user_files` | `bool` | `false` | `false`, `true` | `false` | Enable or disable sudoers management for users. |
| `sudoers_groups` | `list` | `false` | | `[]` | A list of sudoers configurations for groups. |
| `sudoers_groups.commands` | `list` | `false` | | `[]` | The commands allowed by the sudoers rule. <br />Multiple can be added by passing a list of commands. <br />Use `ALL` for all commands. |
| `sudoers_groups.group` | `str` | `false` | | | The name of the group for the sudoers rule. <br />This option cannot be used in conjunction with `user`. |
| `sudoers_groups.name` | `str` | `true` | | `sudoers_mygroupname` | The name of the sudoers rule. |
| `sudoers_groups.nopassword` | `bool` | `false` | `false`, `true` | `false` | Whether a password will be required to run the `sudo`'d command. |
| `sudoers_groups.state` | `str` | `true` | `absent`, `present` | `present` | Whether the rule should exist or not. |
| `sudoers_users` | `list` | `false` | | `[]` | A list of sudoers configurations for users. |
| `sudoers_users.commands` | `list` | `false` | | `[]` | The commands allowed by the sudoers rule. <br />Multiple can be added by passing a list of commands. <br />Use `ALL` for all commands. |
| `sudoers_users.name` | `str` | `true` | | `sudoers_john.doe` | The name of the sudoers rule. |
| `sudoers_users.nopassword` | `bool` | `false` | `false`, `true` | `false` | Whether a password will be required to run the `sudo`'d command. |
| `sudoers_users.state` | `str` | `true` | `absent`, `present` | `present` | Whether the rule should exist or not. |
| `sudoers_users.user` | `str` | `false` | | | The name of the user for the sudoers rule. <br />This option cannot be used in conjunction with `group`. |



Dependencies
---

None

Example Playbook
---

```yaml
- name: "Play | sudoers"
  hosts: all
  roles:
    - role: sudoers
```

License
---

BSD, MIT

Author Information
---

Xenion1987 @ Access-InTech
