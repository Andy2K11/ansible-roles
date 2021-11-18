API_VERSION = 2

UBUNTU = "ubuntu/hirsute64"     # Problems with apt
BENTO = "bento/ubuntu-21.04"
GENERIC = "generic/ubuntu2004"

Vagrant.configure(API_VERSION) do |config|

    # General vagrant configuration
    config.vm.box = BENTO
    config.ssh.insert_key = false
    config.ssh.port = 2891
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.synced_folder "~/.cache/apt", "/var/cache/apt"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 768
        vb.cpus = 1
        vb.linked_clone = true
    end

    config.vm.provision "ansible" do |ansible|
        ansible.inventory_path = "hosts.ini"
        ansible.playbook = "main.yml"
        ansible.compatibility_mode = "2.0"
    end

    config.vm.define "ubuntu" do |ubuntu|
        ubuntu.vm.hostname = "ubuntu.test"
        ubuntu.vm.network :private_network, ip: "192.168.60.51"
    end
end
