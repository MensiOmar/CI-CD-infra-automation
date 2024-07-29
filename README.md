# GitLab and GitLab Runner Installation Guide

This guide provides step-by-step instructions for installing GitLab and GitLab Runner on Ubuntu machines using Ansible playbooks. Ensure you have Ansible installed and configured on your machine before proceeding.

## Prerequisites

- An Ubuntu machine (required).
- Root access to the target machine(s) for installation.
- Ansible installed on your local machine.

## Installation Process

The installation process consists of several phases, each focusing on a specific aspect of the setup.

### Phase 1: Prepare Inventory

1. Update the `inventory.ini` file with the IP address and user credentials of the target Ubuntu machine(s).

### Phase 2: Install gitlab and gitlab runner
2. Execute the GitLab and GitLab Runner installation playbook:

```bash
ansible-playbook --ask-become-pass gitlab-installation.yml
```

   **Note:** The prerequisetes phase is specific to Ubuntu 20.04 machines, else you can use machines that already has docker , docker compose plugin and docker ,docker compose python sdks installed  .


### Phase 4: Set Admin Password

4. Change the admin password for GitLab once gitlab is running:

   run the configuration playbook:

```bash
ansible-playbook --ask-become-pass gitlab-configuration.yml -v
```

### Phase 5: Register GitLab Runner (Optional)

If you wish to register a newly created runner:

1. Create a runner from the GitLab UI.
2. Save the registration token provided by GitLab.
3. Run the registration playbook:

```bash
ansible-playbook --ask-become-pass runner-registration.yml -v
```

   Follow the prompts to complete the registration process.

By following these steps, you should have successfully installed GitLab and GitLab Runner on your Ubuntu machine(s). Remember to replace placeholders with actual values relevant to your environment.
