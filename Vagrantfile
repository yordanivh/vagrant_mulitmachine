Vagrant.configure("2") do |config|

    (1..2).each do |i|
      config.vm.define vm_name="web#{i}" do |node|
        node.vm.box = "yordan/box"
        node.vm.hostname = vm_name
      end
    end
  
    config.vm.define vm_name="mysql" do |node|
      node.vm.box = "yordan/box"
      node.vm.hostname = vm_name
      
    end
  end
