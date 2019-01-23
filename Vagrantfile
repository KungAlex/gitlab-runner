VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.define "gitlab-runner" do |gr|

        gr.vm.network "public_network", bridge: "enp0s31f6"

        gr.vm.provider "virtualbox" do |vb|
            vb.gui = false
            vb.name = "gitlab-runner"
            vb.memory = "2048"
        end

	    gr.vm.provision :ansible do |ansible|
    	    ansible.playbook = "playbook.yml"
        end
  end
  
end