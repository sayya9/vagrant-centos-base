Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.define "centos"
  config.vm.hostname = "centos"
  config.ssh.private_key_path = ["~andrew/.ssh/id_rsa", "~/.vagrant.d/insecure_private_key"]
  config.ssh.insert_key = false
  config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"
  config.vm.network :forwarded_port, guest: 22, host: 2301, id: 'ssh'
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048", "--cpus", "2"]
  end
end
