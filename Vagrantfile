Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-24.04"

  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apache2 git

    TIME=$(date '+%Y-%m-%d %H:%M:%S %Z')

    echo "<h1>Hello from the updated Vagrant setup</h1>" | sudo tee /var/www/html/index.html
    echo "<p>Provisioned at: $TIME</p>" | sudo tee -a /var/www/html/index.html
  SHELL

end
