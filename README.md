# Galleon

## A Collection of Fleet Bundles

Welcome! 👋

I created this repository to store all of my manifests I deploy to my [RKE2](https://docs.rke2.io/) cluster using [Fleet](https://fleet.rancher.io/). Please copy my homework as you see fit for deploying to Kubernetes at home! ⚓️

## Setup

- Fork this repository
- Adjust it to your needs
- Create a GitRepo in Fleet called "galleon" pointed at your repo
- Create the dependent secrets for deployments
- Profit 🎉

## Harvester Notes

I am using some cloud configs in order to spin up my virtual machines

For Kubernetes, I am using the following:

```yaml
#cloud-config
package_update: true
package_upgrade: true
package_reboot_if_required: true

users:
  - name: valentina
    groups:
      - sudo
    shell: /bin/bash
    sudo: ['ALL=(ALL) NOPASSWD:ALL']
    ssh_authorized_keys:
      - ssh-ed25519
        AAAAC3NzaC1lZDI1NTE5AAAAII8WYFLUYD70w4Pk+1J5Gl8LUyLKr7/TK1evoqdTIVVx
        violet@Mac-mini.localdomain

packages:
  - qemu-guest-agent
  - neofetch
  - wget
  - nano
  - tree
  - nfs-common

runcmd:
  - - systemctl
    - enable
    - '--now'
    - qemu-guest-agent.service
  - - modprobe
    - macvlan
```

For Docker, I am using the following:

```yaml

#cloud-config
package_update: true
package_upgrade: true
package_reboot_if_required: true

groups:
  - docker

users:
  - name: valentina
    groups:
      - sudo
      - docker
    shell: /bin/bash
    sudo: [ 'ALL=(ALL) NOPASSWD:ALL' ]
    ssh_authorized_keys:
      - ssh-ed25519
        AAAAC3NzaC1lZDI1NTE5AAAAII8WYFLUYD70w4Pk+1J5Gl8LUyLKr7/TK1evoqdTIVVx
        violet@Mac-mini.localdomain
apt:
  sources:
    docker.list:
      source: deb [arch=amd64] https://download.docker.com/linux/ubuntu $RELEASE stable
      keyid: 9DC858229FC7DD38854AE2D88D81803C0EBFCD88

packages:
  - apt-transport-https
  - ca-certificates
  - curl
  - gnupg-agent
  - software-properties-common
  - docker-ce
  - docker-ce-cli
  - containerd.io
  - unattended-upgrades
  - qemu-guest-agent
  - neofetch

runcmd:
  - - systemctl
    - start
    - docker
  - - systemctl
    - enable
    - docker
  - - systemctl
    - enable
    - --now
    - qemu-guest-agent.service
```
