Launch bar to bottom:
```bash
gsettings set com.canonical.Unity.Launcher launcher-position Bottom
```

Install security updates only:
```
sudo sh -c 'grep ^deb /etc/apt/sources.list | 
    grep security > /etc/apt/sources.security.only.list'
apt-get -s dist-upgrade -o Dir::Etc::SourceList=/etc/apt/sources.security.only.list -o Dir::Etc::SourceParts=/dev/null  | 
    grep "^Inst" | awk -F " " {'print $2'}
checkrestart -v
```
(for Debian)
```
# Show security updates
apt-get -s dist-upgrade |grep "^Inst" |grep -i securi 
# Install
apt-get -s dist-upgrade | grep "^Inst" | 
    grep -i securi | awk -F " " {'print $2'} | 
    xargs apt-get install
```
