# https://portal.cloud.hashicorp.com/vagrant/discover
#config.vm.box = "generic/rhel9" # issue with libxml2-devel needed for PHP
#config.vm.box = "generic/rocky9"
#config.vm.box = "generic/oracle9"
#config.vm.box = "generic/alma9"
#config.vm.box = "generic/centos9s"
#config.vm.box = "centos/stream9"
#config.vm.box = "centos/stream10"
#config.vm.box = "generic/debian12"
#config.vm.box = "debian/bookworm64"

#config.vm.box = "generic/fedora39"
#config.vm.box = "fedora/40-cloud-base"
#config.vm.box = "generic/rhel8"
#config.vm.box = "generic/oracle8"
#config.vm.box = "generic/ubuntu2204"
#config.vm.box = "ubuntu/jammy64"

#config.vm.box = "generic/openbsd7"
#config.vm.box = "generic/netbsd9"
#config.vm.box = "generic/freebsd14"
#config.vm.box = "generic/alpine319"
#config.vm.box = "generic/opensuse42"

distros = [
  #"generic/rhel9", # subscription is required
  "generic/rocky9",
  "generic/oracle9",
  "generic/alma9",
  "generic/centos9s",
  "centos/stream9",
  "centos/stream10",
  "ubuntu/jammy64",
  "debian/bookworm64",
]

Vagrant.configure("2") do |config|
    distros.each_with_index do |distro, index|
    config.vm.define "machine#{index}" do |machine|
      machine.vm.box = distro
      machine.vm.hostname = "machine#{index}"
      machine.vm.network "private_network", ip: "192.168.56.#{100 + index}"
      machine.vm.synced_folder ".", "/vagrant", disabled: true
    end
  end

  #
  # Run Ansible from the Vagrant Host
  #
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.compatibility_mode = "2.0"
    ansible.version = "latest"
    ansible.verbose = "-v"
    ansible.groups = {
      #"web" => ["machine0", "machine1", "machine2", "machine3", "machine4", "machine5", "machine6", "machine7"], #
      "database" => ["machine0", "machine1", "machine2", "machine3", "machine4", "machine5", "machine6", "machine7"], #
    }
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end
end