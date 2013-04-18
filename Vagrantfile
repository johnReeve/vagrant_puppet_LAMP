Vagrant::Config.run do |config|

  # Enable the Puppet provisioner, with will look in manifests
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "default.pp"
    puppet.module_path = "modules"
  end

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise32"

  # Forward guest port 80 to host port 8888 and name mapping
  config.vm.forward_port 80, 8888

  #Make apache's www-data user the owner of the project so it can write files
  config.vm.share_folder("project", "/vagrant/project", "./project", :owner => "www-data", :group => "www-data")

end