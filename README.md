# os_bootstrap

os_bootstrap is a simple ansible playbook to bootstrap a debian/centos host created and configured by spartacus/rawinit from masterdebian/mastercentos.

It performs multiple steps:

* `apt-get update` | `yum update`
* `put on hold puppet packages`
* `apt-get dist-upgrade` | `yum update`
* `reboot`
* first puppet run for certificate request (after the certificate request it will wait for user input to confirm cert sign on puppetmaster)
* enable puppet at startup
* second puppet run for first config
* third puppet run to ultimate first config

## Usage
```
ansible-playbook -i newhost, os_bootstrap.yml
```
