Vagrant::Config.run do |config|
  ## Chose your base box
  config.vm.box = "icat_precise64_v1"
  config.vm.customize ["modifyvm", :id, "--memory", 2048]

  ## To share a folder with the host..
  #config.vm.share_folder "foo", "/home/glassfish3/icat42", "/Users/steve/Documents/icat"

  config.vm.forward_port 4848, 4848
  config.vm.forward_port 8080, 8080

end
