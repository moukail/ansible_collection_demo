### Vagrant
#### install virtualbox
```bash
wget https://download.virtualbox.org/virtualbox/7.1.8/virtualbox-7.1_7.1.8-168469~Ubuntu~noble_amd64.deb
sudo dpkg -i virtualbox-7.1_7.1.8-168469~Ubuntu~noble_amd64.deb

sudo apt install gcc-12 g++-12
sudo /sbin/vboxconfig
VBoxManage --version
```

# host manager
```bash
vagrant plugin install vagrant-hostmanager
vagrant hostmanager
```

#### delete VM
```bash
vagrant destroy -f
```

#### start VM
```bash
vagrant up --provider=virtualbox --provision
```

#### connect to VM
```bash
vagrant ssh
vagrant ssh machine0
```

#### 
```bash
vagrant reload --provision
```
