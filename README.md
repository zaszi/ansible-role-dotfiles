# Ansible Role: Dotfiles

Deploys personal dotfiles and scripts.

## Requirements

It is recommended to run this role with `become: false`, as most tasks are relevant to your particular user, not the entire system. The few tasks that require root will escalate privileges on their own (and thus you will still need a user that has sudo rights).

## Role Variables

| Variable                | Choices/**Default** | Comments                                                      |
| ----------------------- | ------------------- | ------------------------------------------------------------- |
| alacritty               | true, **false**     | Whether to install Alacritty configuration files              |
| bash                    | true, **false**     | Whether to install Bash configuration files                   |
| bash_root               | true, **false**     | Whether to install Bash configuration files for the root user |
| neovim                  | true, **false**     | Whether to install Neovim configuration files                 |
| neovim_plugins          | **[]**, …           | List of Neovim plugins to install                             |
| rust                    | true, **false**     | Whether to set up the Rust development tools                  |
| rust_components         | **[]**, …           | List of Rust components to install                            |
| rust_cargo              | **[]**, …           | List of Rust Cargo binaries to install                        |
| scripts                 | true, **false**     | Whether to install user scripts                               |
| sway                    | true, **false**     | Whether to install Sway and Waybar configuration files        |
| syncthing               | true, **false**     | Whether to set up Syncthing                                   |
| tmux                    | true, **false**     | Whether to install Tmux configuration files                   |
| weechat                 | true, **false**     | Whether to install Weechat relay service files                |
| weechat_backup_location | "", …               | Location of the Weechatconfiguration backup tarball           |

## Dependencies

This role requires my [dotfiles](https://github.com/zaszi/dotfiles) and my [scripts](https://github.com/zaszi/scripts) repositories to be cloned or otherwise placed under `files/`.

## Example Playbook

    - hosts: all
      become: false
      roles:
         - ansible-role-dotfiles

## License

Ansible-role-dotfiles is licensed under the [MIT license](https://github.com/zaszi/ansible-role-dotfiles/blob/master/LICENSE.md).
