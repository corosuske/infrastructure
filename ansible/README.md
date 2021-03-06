# Setting up with Ansible

Start by getting ansible on your host:

http://docs.ansible.com/ansible/intro_installation.html#installing-the-control-machine

Make sure the `fosdem_hosts` file is up to date

Setup the ENV if you want to operate outside of the repo:

    export FOSDEM_REPO="$(git rev-parse --show-toplevel)"
    export ANSIBLE_CONFIG="${FOSDEM_REPO}/ansible/fosdem_ansible.cfg"
    export ANSIBLE_INVENTORY="${FOSDEM_REPO}/ansible/fosdem_hosts"
    ls -l "${ANSIBLE_CONFIG}" "${ANSIBLE_INVENTORY}"

Check the connectivity

    ansible all -m ping 

Deploy

    ansible-playbook site.yml
