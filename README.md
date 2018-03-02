# debian_bootstrap

debian_bootstrap is a simple ansible playbook to bootstrap a debian host created and configured by spartacus/rawinit from masterdebian9.

It performs multiple steps:

* apt-get update
* put on hold puppet package
* apt-get dist-upgrade
* reboot
* first puppet run for certificate request (after the certificate request it will wait for user input to confirm cert sign on puppetmaster)
* second puppet run for first config
* third puppet run to ultimate first config

## Usage
```
ansible-playbook -i newhost, debian_bootstrap.yml
```
