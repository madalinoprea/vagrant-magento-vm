
h2. Usage
`
# Clone this git repo
git clone https://github.com/madalinoprea/vagrant-magento-vm.git
cd vagrant-magento-vm/

# Retrieve required cookbooks
git submodule update --init

# Review Vagrant, e.g change Magento version that is going to be installed
vagrant up
`

TODO:
 - Add support to enable Magento Developer Mode
 - Add support for secure domains
 - Add support for xdebug
 - Add support for Magento Enterprise
 - Add index for http://magentoversions.appspot.com to see available magento versions
