# kubeadm-ha-ansible

Ansible playbook with Kubeadm to build Kubernetes HA environment

~~~
for i in $(cat inventory/staging/inventory.cfg | grep "ansible_host" | awk '{print $2}' | sed 's/ansible_host=//'); do ssh-copy-id root@$i ; done

ansible -i inventory/staging/inventory.cfg -m ping all
ansible-playbook -i inventory/staging/inventory.cfg main.yml
~~~
