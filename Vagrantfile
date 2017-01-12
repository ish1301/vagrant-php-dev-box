# Optimized for Vagrant 1.7 and above.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "vv"
    ansible.playbook = "playbooks/vagrant.yml"
  end

  config.vm.network "forwarded_port", guest: 80, host: 1234
  config.vm.network "private_network", ip: "192.168.50.4"
end
