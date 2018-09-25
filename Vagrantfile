Vagrant.configure("2") do |config|
  config.vm.define "docker" do |host|
    host.vm.box = "ubuntu/trusty64"
    host.vm.hostname = "docker"
    
    for i in 10000..10010
      config.vm.network :forwarded_port, guest: i, host: i
    end
    config.vm.synced_folder ".", "/vagrant" 
    host.vm.provider :virtualbox do |v|
      v.name = "docker"
      v.memory = 8192
      v.cpus = 2
      v.linked_clone = true
    end
  end  
end
