Vagrant.require_version ">= 1.4.3"
VAGRANTFILE_API_VERSION = "2"

#   Vagrant recipe for setting up jenkins, maven, java using centos 64 base box
#
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
        config.vm.define :master do |master|
                master.vm.box = "centos65"
                master.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box"
                master.vm.provider "virtualbox" do |v|
                  v.name = "scm-box"
                  v.customize ["modifyvm", :id, "--memory", "4196"]
                end
                master.vm.network :private_network, ip: "10.211.55.101"
                master.vm.hostname = "scm-box"
                master.vm.provision :shell, :path=> 'provision.sh'
        end
end

