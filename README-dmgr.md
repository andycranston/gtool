# dmgr

## Server specs

+ 20 x CPU
+ 48GB RAM
+ 2 x NICs
+ 2 x HDDs (1st 96 GB / 2nd 1.2 TB both thin provisioned)

Leave second NIC disconnected.

After install of OS edit VM and connect 2nd NIC.

Edit VM and change CD/DVD drive 1 to a Client Device.

Login as labuser and check route to internet:

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
./dmgr
```

If you are asked to logout then logout, log back in and run:

```
cd gtool
./dmgr
```

Run:

```
sudo apt update
sudo apt upgrade
```

Use the nplan script to setup a *.yaml file in /etc/netplan - for example:

```
./nplan 10.173.129.197 10.173.129.198 172.19.15.56 > /tmp/foo
sudo cp /tmp/foo /etc/netplan/00-installer-config.yaml
cd /etc/netplan
sudo netplan apply
```

Reboot and check everythings is ok.

This is now a good place to save the VM as a template or snapshot the VM.

Now proceed with the installation of domain manager.

-----------------------------------------------------------------
End of document
