# Enable DNS resolver
```bash
VBoxManage modifyvm "VM name" --natdnshostresolver1 on
```
# Host as localhost to VM:
1. Shut your virtual machine down.
2. Go to VirtualBox Preferences -> Network -> Host-only Networks -> click the "+" icon. Click OK.
3. Select your box and click the "Settings" icon -> Network -> Adapter 2 -> On the "Attached to:" dropdown, select "Host-only Adapter" and your network (vboxnet0) should show up below by default. Click OK.
4. Once you start your box up again, you should be able to access localhost at http://10.0.2.2/ - if not check ifconfig interfaces and select correct IP.
You can refer to it by localhost and access other localhosted sites by adding their references to the hosts file (C:\windows\system32\drivers\etc\hosts) like the following:
```bash
10.0.2.2    localhost
10.0.2.2    subdomain.localhost
```
