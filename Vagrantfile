Vagrant.configure("2") do |config|
  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = "http://PROXYSESO.SCANIA.COM:8080"
    config.proxy.https    = "https://PROXYSESO.SCANIA.COM:8080"
    config.proxy.no_proxy = "localhost,127.0.0.1,.scania.com:8080"
  end
  config.vm.box = "jasonc/centos7"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.customize ['modifyvm', :id, '--cableconnected1', 'on']
  end
  config.vm.define "test1" do |test1|
  test1.vm.hostname = "test1"
  test1.vm.network "private_network", ip: "192.168.56.5"
  end
  config.vm.define "test2" do |test2|
  test2.vm.hostname = "test2"
  test2.vm.network "private_network", ip: "192.168.56.6"
  end
  end