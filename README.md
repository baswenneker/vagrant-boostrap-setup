vagrant-boostrap-setup
======================
###setup vagrant
```
mkdir xxx-theme
cd xxx-theme
mkdir xxx-theme-project
vagrant init precise32 http://files.vagrantup.com/precise32.box
```
###add to Vagrantfile
```
# Port 9000 is where grunt server is doing serving from
config.vm.network :forwarded_port, guest: 9000, host: 9000
# Port 35729 is required by LiveReload to reflect content changes
config.vm.network :forwarded_port, guest: 35729, host: 35729
config.vm.synced_folder "xxx-theme-project", "/home/vagrant/xxx-theme-project"
```

###boot vagrant
```
vagrant up
vagrant ssh
```

###install node (add)
```
sudo apt-get update && sudo apt-get install -y git python-software-properties && sudo add-apt-repository -y ppa:chris-lea/node.js && sudo apt-get update  && sudo apt-get install -y nodejs
```

###install yeoman and generator
```
sudo npm install -g yo grunt-cli bower generator-webapp
```

###create project
```
cd xxx-theme-project
```

###generate webapp
```
yo webapp
sudo npm install
```

###launch server
```
grunt serve --allow-remote
```

###point browser to
```
http://0.0.0.0:9000
```
