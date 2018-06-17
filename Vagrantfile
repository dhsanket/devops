Vagrant.configure("2") do |config|
  config.vm.box = "scalefactory/centos6"
  config.vm.network :forwarded_port, guest: 80, host: 1234


  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'site.yml'
    ansible.verbose = 'v'
  end

end