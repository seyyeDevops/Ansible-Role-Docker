# Ansible Docker Setup

This repository provides an Ansible playbook for installing and configuring Docker on a Debian-based system. It includes tasks for updating the system, installing necessary packages, adding the Docker GPG key, and configuring Docker settings.

## Prerequisites

- Ansible installed on the control node.
- Root or sudo access on the target node(s).

> **Tip:** If you are in Iran, use a shecan or proxy to download Docker packages. (i use arvancloud docker registry , you can change it in ./defaults/main.yml )

## Directory Structure

```plaintext
.
├── ansible.cfg
├── docker-playbook.yml
├── inventory
│   └── hosts.yml
└── roles
    └── docker-setup
        ├── defaults
        │   └── main.yml
        ├── files
        ├── tasks
        │   ├── config.yml
        │   ├── install.yml
        │   └── main.yml
        └── templates
            └── daemon.j2
```

## Usage

1. **Clone this repository:**

    ```bash
    git clone https://github.com/yourusername/ansible-docker-setup.git
    cd ansible-docker-setup
    ```

2. **Update the inventory file:**

    Modify the `inventory/hosts.yml` file to include your target nodes.

3. **Run the playbook:**

    ```bash
    ansible-playbook -i inventory/hosts.yml docker-playbook.yml
    ```
also you can use tag for run task