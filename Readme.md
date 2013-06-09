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

Known Issues
--------------------
Not sure why sample data is not downloaded when provisioning is run for the first time.
```
[2013-06-09T03:31:00+00:00] INFO: Processing remote_file[/tmp/vagrant-chef-1/magento-sample-data-1.6.1.0.tar.bz2] action run (vagrant_magento::default line 129)

================================================================================
Error executing action `run` on resource 'remote_file[/tmp/vagrant-chef-1/magento-sample-data-1.6.1.0.tar.bz2]'
================================================================================

NameError
---------
Cannot find a resource for action_run on ubuntu version 12.04
```
Workaround, re-run vagrant provision: `vagrant provision`



Configuration Options
---------------------


TODO:
 - [x] Add support to enable Magento Developer Mode
 - [ ] Add support for secure domains
 - [x] Add support for xdebug
 - [ ] Add support for Magento Enterprise
 - [ ] Add index for http://magentoversions.appspot.com to see available magento versions
