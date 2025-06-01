# FreePBX 17 Ansible Playbook for Debian 12

This Ansible playbook automates the installation of FreePBX 17 on a clean Debian 12 build, including the compilation of Asterisk from source.

## Usage

1. Clone the repository:

    ```bash
    git clone https://github.com/kochevrin/ansible-freepbx.git
    cd ansible-freepbx
    ```

2. Edit configuration files:

    - Rename `inventory/servers.example` to `inventory/servers`
    - Adjust your username and server ip in `inventory/servers`
    - Check the version of Asterisk (https://downloads.asterisk.org/pub/telephony/asterisk/)
    - Adjust the Asterisk and FreePBX versions in `playbooks/Debian-FreePBX17/vars/versions.yml`:

        ```yaml
        asterisk_version: 21.8.0
        freepbx_version: "17.0"
        ```

     - If you need a complete installation of FreePBX, not just the necessary modules, you should uncomment the task `Install FreePBX modules` and comment out the task `Download and install extra FreePBX modules` in `playbooks/Debian-FreePBX17/roles/install-freepbx-ui/tasks/main.yml`

 4. Run the playbook:

    ```bash
    ansible-playbook playbooks/Debian-FreePBX17/freepbx17.yml -i inventory/servers --ask-pass
    ```

## Documentation

Detailed documentation is available in the `docs/` directory:

- [Main Documentation](docs/freepbx.md)
- Images and additional resources are located in `docs/images/`

## Configuration Files

#### `vars/versions.yml`
#### `inventory/servers`

## License

This project is licensed under the [MIT License](LICENSE).
