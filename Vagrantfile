Vagrant.configure("2") do |config|
    config.vm.box = "debian/buster64"
    config.vm.provision :shell, path: "init.sh"

    config.vm.define "admin" do |admin|
        admin.vm.hostname = "admin"
        admin.vm.network "private_network", ip: "10.0.9.10"
    end

    config.vm.define "mariadb" do |mariadb|
        mariadb.vm.hostname = "mariadb"
        mariadb.vm.network "private_network", ip: "10.0.9.11"
        mariadb.vm.provision :shell, path: "mariadb/init.sh"
    end

    config.vm.define "webserver" do |webserver|
        webserver.vm.hostname = "webserver"
        webserver.vm.network "private_network", ip: "10.0.9.12"
        webserver.vm.provision :shell, path: "webserver/init.sh"
    end
end