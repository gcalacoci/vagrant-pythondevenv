Vagrant.configure("2") do |config|
  config.vbguest.installer_options = { allow_kernel_upgrade: true }
  config.disksize.size = '25GB'
  config.vm.define "pythondevhost" do |pythondevhost|
    pythondevhost.vm.box = "rockylinux/9"
    pythondevhost.vm.hostname = 'pythondevhost'
    pythondevhost.vm.network :private_network, ip: '192.168.56.176'
    pythondevhost.vm.network :forwarded_port, guest: 22, host: 2203
    pythondevhost.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--name", "pythondevhost"]
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.memory = 8192
      v.cpus = 4
    end
  end
end
