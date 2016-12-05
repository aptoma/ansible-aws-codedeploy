VAGRANTFILE_API_VERSION = '2'
Vagrant.require_version '>= 1.7.0'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  vagrant_root = File.dirname(__FILE__)
  ENV['ANSIBLE_ROLES_PATH'] = "#{vagrant_root}/.."

  config.vm.box = "ubuntu/xenial64"
  # Install python
  config.vm.provision "install python", type: "shell" do |s|
    s.inline = "sudo apt-get -y install python-minimal"
  end

  # Run core
  config.vm.provision "role-test", type: "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end
end
