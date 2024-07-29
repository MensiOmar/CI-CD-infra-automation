# jenkins Installation Guide

This guide provides step-by-step instructions for installing jenkins using Ansible playbooks. Ensure you have Ansible installed and configured on your machine before proceeding.

## Prerequisites

- An Ubuntu machine (required).
- Root access to the target machine(s) for installation.
- Ansible installed on your local machine.

## Installation Process

The installation process consists of several phases, each focusing on a specific aspect of the setup.

### Phase 1: Prepare Inventory

1. Update the `inventory.ini` file with the IP address and user credentials of the target machine(s).

### Phase 2: Install jenkins
2. Execute the GitLab and GitLab Runner installation playbook:

```bash
ansible-playbook --ask-become-pass jenkins_installation.yml
```

   **Note:** The prerequisetes phase is specific to Ubuntu 20.04 machines, else you can use machines that already has docker , docker compose plugin and docker ,docker compose python sdks installed  .


### Phase 3: get first admin pass

3. once the installation is complete the ansible debugger will provide 
    you with the first admin pass copy it and paste it to proceed with the next phase



### Phase 4: complete admin account configuration:

4. jenkins will prompt you the steps to complete your registration
    follow it and you will have your account set up

By following these steps, you should have successfully installed jenkins machine(s). Remember to replace placeholders with actual values relevant to your environment.