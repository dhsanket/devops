Vagrant.configure("2") do |config|
  config.vm.box = "scalefactory/centos6"
#  config.ssh.insert_key = false
#  config.ssh.password = "abcd"
#   config.ssh.port = 2222
  config.vm.network :forwarded_port, guest: 80, host: 1234, id: "ssh", auto_correct: true
end
