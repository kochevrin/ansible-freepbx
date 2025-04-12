# FreePBX 17 Ansible Playbook for Debian 12

This Ansible playbook automates the installation of FreePBX 17 on a clean Debian 12 build, including the compilation of Asterisk from source.

## Usage

1. Clone the repository:

    ```bash
    git clone https://github.com/kochevrin/ansible-freepbx.git
    cd ansible-freepbx
    ```

2. Edit configuration files:

    - Check the version of Asterisk (https://downloads.asterisk.org/pub/telephony/asterisk/)
    - Adjust the Asterisk and FreePBX versions in `playbooks/Debian-FreePBX17/vars/versions.yml`:

        ```yaml
        asterisk_version: 21.8.0
        freepbx_version: "17.0"
        ```

 3. - If you need a complete installation of FreePBX, not just the necessary modules, you should uncomment the task `Install FreePBX modules` and comment out the task `Download and install extra FreePBX modules` in `playbooks/Debian-FreePBX17/roles/install-freepbx-ui/tasks/main.yml`

 4. Run the playbook:

    ```bash
    ansible-playbook playbooks/Debian-FreePBX17/freepbx17.yml -i inventory/servers --ask-pass
    ```

## Configuration Files

### `vars/versions.yml`

## License

This project is licensed under the [MIT License](LICENSE).
