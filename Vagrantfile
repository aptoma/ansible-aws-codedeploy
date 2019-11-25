VAGRANTFILE_API_VERSION = '2'
Vagrant.require_version '>= 1.7.0'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  vagrant_root = File.dirname(__FILE__)
  ENV['ANSIBLE_ROLES_PATH'] = "#{vagrant_root}/.."

  config.vm.box = "ubuntu/bionic64"

  # Run core
  config.vm.provision "role-test", type: "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
    ansible.raw_arguments = [
      '-e', 'ansible_python_interpreter=/usr/bin/python3'
    ]
  end
end
