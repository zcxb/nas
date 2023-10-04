# nas

My home nas server configurations

## init server

### 1. ssh config

```bash
# /etc/ssh/sshd_config
# edit these lines

PermitRootLogin yes
PasswordAuthentication yes
```

then restart sshd

```bash
systemctl restart sshd
```

### 2. set static ip

```bash
# /etc/network/interfaces
auto eth0
iface lo inet loopback
iface eth0 inet static # use static replace dhcp
address 192.168.x.x
netmask 255.255.255.0
gateway 192.168.1.1
```

then restart network

```bash
systemctl restart networking
```
