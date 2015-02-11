# gitlab-ansible

Setting up GitLab using by Ansible.

## Requirements

* Ansible
* VirtualBox
* Vagrant 1.5+

## Usage

### production

First of all, install CentOS 6.x to the server.

Create Ansible inventory file.

    $ ${EDITOR} production/inventory
    [default]
    gitlab.example.com  ansible_ssh_user=admin

Create configuration file.

    $ ${EDITOR} production/group_vars/all
    ---
    gitlab_external_url: https://gitlab.example.com
    gitlab_ssh_host: gitlab.example.com
    gitlab_email_from: gitlab@example.com

Run ansible playbook.

    $ ansible-playbook -i production/inventory site.yml

Login.

* https://gitlab.example.com/<br>(root / 5iveL!fe)

### local vagrant

Run ansible playbook.

    $ vagrant up
    $ vagrant provision

Login.

* [https://10.200.19.34/](https://10.200.19.34/)<br>(root / 5iveL!fe)
