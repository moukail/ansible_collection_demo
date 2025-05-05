# Ansible Collection - moukail.my_collection

Documentation for the collection.

###
```bash
docker run -dit --name galaxy ansible/galaxy tail -f /dev/null
```

### collection
```bash
ansible-galaxy collection init moukail.my_collection --init-path ./collections
chmod +x collections/moukail/my_collection/plugins/modules/hello_module.py

ansible-galaxy collection build collections/moukail/my_collection --output-path ./
ansible-galaxy collection publish moukail-my_collection-*.tar.gz --token xxxxxxxxxxxxxxxxxxxxxxxxxxx
ansible-galaxy collection install moukail-my_collection-*.tar.gz -p ~/.ansible/collections
ansible-galaxy collection install /path/to/collection -p ./collections

ansible-galaxy collection install -r requirements.yml
ansible-galaxy collection list

ansible-playbook test_playbook.yml -vvv
```

### role
```bash
ansible-galaxy role init myrole --init-path ./roles
ansible-galaxy role list --roles-path ./roles
ansible-galaxy role remove myrole --roles-path ./roles

ansible-galaxy role info nginx
ansible-galaxy role import --role-name myrole --token xxxxxxxxxx github_user github_repo
ansible-galaxy role setup source github_user github_repo secret

ansible-galaxy role search nginxinc
ansible-galaxy role info nginxinc.nginx
ansible-galaxy role install nginxinc.nginx
ansible-galaxy role install elastic.elasticsearch

```