# puppet
Pense bête sur puppet
## installation de puppet 6 server sur stretch
* https://puppet.com/docs/puppetserver/6.0/install_from_packages.html
* wget https://apt.puppet.com/puppet6-release-stretch.deb
* dpkg -i puppet6-release-stretch.deb
* apt-get update
* apt-get install puppetserver
* puppetserver ca setup
* systemctl enable puppetserver
* systemctl start puppetserver (voir /etc/default/puppetserver pour reduire la mémoire à 512 M sur un VM qui va servir peu de noeuds)
* /etc/hosts --> 127.0.0.1 puppet
* /etc/puppetlabs/code/environments/production/manifests/site.pp
```
node default {
  notify { "compiled on puppetmaster1": }
}

```
* puppet agent -t
