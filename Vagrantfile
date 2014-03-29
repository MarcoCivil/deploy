Vagrant.require_version ">= 1.5.1"

Vagrant.configure("2") do |config|
  config.vm.define "default" do |c|
    c.ssh.port = 2222
    c.vm.box = "precise64"
    c.vm.network :forwarded_port, guest: 80, host: 8000
    c.vm.network :forwarded_port, guest: 443, host: 8001

    c.vm.provision :ansible do |ansible|
      ansible.playbook = "site.yml"
      ansible.inventory_path = "inventory/vagrant"
    end
  end
end
