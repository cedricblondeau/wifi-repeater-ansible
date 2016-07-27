# wifi-repeater-ansible

A simple and straightforward playbook to set up a WiFi repeater service using create_ap.

## Usage

### Configure

First, create a inventory/config file (let's name it laptop):

```bash
cp inventories/sample inventories/laptop
```

#### Example: Execute playbook on a remote target using the same WiFi adapter

```
[repeater]
192.168.33.10 ansible_port=2222 ansible_user=ubuntu

[repeater:vars]
wifi_interface=wlp2s0
interface_with_internet=wlp2s0
access_point_name=Fsociety
access_point_passphrase=YouMustChangeThis1234!
``

### Run

```
ansible-playbook -i inventories/laptop playbook.yml --ask-become-pass -vvvv
```

## Support / compatibility

Successfully tested with Ansible 2.1 and a fresh install of Ubuntu 16.04 Desktop on target (QCA9565 / AR9565 Wireless Network Adapter, nl80211 driver).
