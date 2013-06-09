Setup Instructions
-------------------

```bash
# Clone this git repo
git clone https://github.com/madalinoprea/vagrant-magento-vm.git
cd vagrant-magento-vm/

# Retrieve required cookbooks
git submodule update --init

# Review Vagrant, e.g change Magento version that is going to be installed
vagrant up
```

By default, Magento's url is magento.local and vm's ip is192.168.33.10. Please configure your hosts file accordingly:
```bash
192.168.33.10 magento.local
```



Configuration Options
---------------------


TODO:
 - [x] Add support to enable Magento Developer Mode
 - [ ] Add support for secure domains
 - [x] Add support for xdebug
 - [ ] Add support for Magento Enterprise
 - [ ] Add index for http://magentoversions.appspot.com to see available magento versions
