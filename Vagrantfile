Vagrant.configure("2") do |config|
  config.vm.define "default" do |c|
    c.vm.box = "precise64"
    c.vm.network :forwarded_port, guest: 80, host: 2000
    c.vm.network :forwarded_port, guest: 22, host: 2222, id: "ssh"

    c.vm.provision :ansible do |ansible|
      ansible.playbook = "site.yml"
      ansible.inventory_path = "inventory/vagrant"
    end
  end
end
