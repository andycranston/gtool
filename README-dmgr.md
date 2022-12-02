# dmgr

## Server specs

+ 20 x CPU
+ 48GB RAM
+ 2 x NICs
+ 2 x HDDs (1st 200GB / 2nd 500GB)

Leave second NIC disconnected

After install of OS check route to internet:

```
ping 8.8.8.8
ping 8.8.4.4
ping 174.138.8.7
```

Check name resolution:

```
ping www.github.com
```

Download gtool:

```
git clone https://github.com/andycranston/gtool.git
```

Run:

```
cd gtool
sh perms
./dmgr
```

If you are asked to logout then logout, backon and run:

```
cd gtool
./dmgr
```

If Ubuntu 20.04.x LTS AND a VMware virtual machine then edit the /etc/multipath.conf file and add these lines:

```
blacklist {
    devnode sda
    devnode sdb
}
```

Run:

```
sudo systemctl restart multipathd
```

Run:

```
sudo apt update
sudo apt upgrade
```

Use the nplan script to setup a *.yaml file in /etc/netplan - for example:

```
./nplan 10.173.129.197 10.173.129.198 172.19.15.56 > /tmp/foo
cd /etc/netplan
sudo vi *.yaml
```

Reconnect the SB NIC.

Apply the new netplan:


```
sudo netplanm apply
```

Reboot and check everythings is ok.

This is now a good place to save the VM as a template.

Or push on with the installation of domain manager.











