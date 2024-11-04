# Transferring public server to private server using Openstack

## Launch your AWS instance with following preferences:
- Ubuntu OS
- Ubuntu 22.04 LTS
- t2.xlarge (16GB ram)
- 50 GB storage
- HTTP/HTTPS and All traffic (anywhere) enabled

### Now open your instance in PuTTY and follow the following commands.

#### Install the openstack snap:

```bash
sudo snap install openstack --channel 2024.1/beta
```

### Prepare the machine:

```bash
sunbeam prepare-node-script | bash -x && newgrp snap_daemon
```

### Bootstrap the cloud:

```bash
sunbeam cluster bootstrap --accept-defaults
```

### Configure the cloud and obtain credentials:

```bash
sunbeam configure --accept-defaults --openrc demo-openrc
```

### Launch a VM:

```bash
sunbeam launch ubuntu --name test
```
