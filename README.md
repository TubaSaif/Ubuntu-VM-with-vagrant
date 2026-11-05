# Ubuntu VM with Vagrant

This folder creates a clean Ubuntu 22.04 virtual machine in VirtualBox using
Vagrant.

## Requirements

1. [Oracle VirtualBox](https://www.virtualbox.org/)
2. [Vagrant for Windows](https://developer.hashicorp.com/vagrant/downloads)

## Usage

Open PowerShell in this folder and start the VM:

```powershell
vagrant up
```

The VM uses the `ubuntu/jammy64` box and is available at:

- Private network IP: `192.168.56.10`
- Host port forwarding for guest port 80: `http://localhost:8080/`

The port forwarding is available if you install and configure a web server
inside the VM yourself.

## Login

SSH into the VM with:

```powershell
vagrant ssh
```

The default login user is:

```text
Username: vagrant
Password: vagrant
```

Vagrant normally uses an automatically generated SSH key, so the password is
not required when using `vagrant ssh`. The `vagrant` user can use `sudo`
without a password.

## Useful commands

```powershell
vagrant status
vagrant ssh
vagrant halt
vagrant reload
vagrant destroy -f
```

To run a command without opening an interactive shell:

```powershell
vagrant ssh -c "uname -a"
```

## VM configuration

The VM configuration is defined in `Vagrantfile`:

- Ubuntu 22.04 (`ubuntu/jammy64`)
- Hostname: `lemp-vagrant`
- Private IP: `192.168.56.10`
- Memory: 2048 MB
- CPUs: 2

To change these settings, edit `Vagrantfile` and run:

```powershell
vagrant reload
```
