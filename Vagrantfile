# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

ENV["ANSIBLE_CONFIG"] = "ansible.vagrant.cfg"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine.
  # 7474 is the default Neo4j port. The port here must be the same as the one in vars/vagrant.yml
  config.vm.network :forwarded_port, guest: 7474, host: 7474

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vagrant.yml"
    ansible.sudo = true
    ansible.verbose = "vv"
    ansible.limit = "all"
  end
end
