# Icaro
Basic Vagrant Box for PHP/Nginx/MySQL development

## Setup
This is a basic Vagrant box built on Ubuntu 16.04 configured for local web dev work. PHP 7.2 and Nginx are included in the provisioning. It has been kept as bare-bones as possible, as this is mainly used for small local dev projects and sometimes running legacy projects on. 

Clone this repo to a directory

```
git clone https://github.com/achubb/icaro
```

You can edit .provision/nginx/nginx.conf and change the `server_name` value form icaro.abt to a suitable local domain.

You can change the ip for the machine by editing the following line in the Vagrantfile

```
config.vm.network "private_network", ip: "192.168.68.88"
```

Running `vagrant up` will now install the Ubuntu 16.04 VM and set up nginx and PHP. Once complete you should be able to configure your hosts file to point to `192.168.68.88` using the test domain you configured (default is icaro.abt). 

## Installing MySQL
Should MySQL be needed, I find it simple to login to the vagrant machine `vagrant ssh` and setup MySQL by typing:

```
sudo apt-get install mysql-server
```

You can then set up the users and databases as necessary

The included index.php file includes a simple php script to test database connections. 
