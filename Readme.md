Goal
------------------
Create a Vagrant configuration that offers ability to install different versions of Magento with minimum effort.

Tested for 1.8 alpha and 1.7 with sample data.

Setup Instructions
-------------------
Install Virtual Box: https://www.virtualbox.org/wiki/Downloads
Install Vagrant for your platform: http://downloads.vagrantup.com/

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

Credentials (configurable via chef):

 
|       | User  | Password |
| ----- | ------| -------- |
| MySQL | root  | root     |
| Admin | admin | m123123 |



Configuration Options
---------------------
<dl>

<dt>vagrant_magento.source.version</dt>
<dd>Specified Magento version that will be installed.  Default: magento-1.8.0.0-alpha1</dd>

<dt>vagrant_magento.source.url</dt>
<dd>Base url used to download the zip files, we'll try to retrieve {url}/{version}.tar.bz2. Default: http://magentoversions.appspot.com</dd>
 
<dt>vagrant_magento.sample_data.install</dt>
<dd>Default: true. Downloads sample data provided by Magento.</dd>

<dt>vagrant_magento.sample_data.version</dt>
<dd>Default: 1.6.1.0</dd>

<dt>vagrant_magento.sample_data.url</dt>
<dd>Default: http://www.magentocommerce.com/downloads/assets</dt>
 
<dt>vagrant_magento.debug.enabled</dt>
<dd>Installs Magneto Debug. Default: true</dd>

</dl>

Available versions
--------------------
 
Using default repository (http://magentoversions.appspot.com/index.html) contains the following version, these versions
are available:

 * magento-1.4.2.0
 * magento-1.5.1.0
 * magento-1.6.2.0
 * magento-1.7.0.2
 * magento-1.8.0.0-alpha1 (default)

TODO:
- [x] Add support to enable Magento Developer Mode
- [ ] Add support for secure domains
- [x] Add support for xdebug
- [ ] Add support for Magento Enterprise
- [x] Add index for http://magentoversions.appspot.com to see available magento versions
