# Ansible Collection - moukail.my_collection

Documentation for the collection.


```bash
ansible-galaxy collection init moukail.my_collection
cd moukail\my_collection
chmod +x plugins/modules/hello_module.py

ansible-galaxy collection build
ansible-galaxy collection install collections/moukail/my_collection/moukail-my_collection-*.tar.gz
ansible-playbook test_playbook.yml -vvv
```