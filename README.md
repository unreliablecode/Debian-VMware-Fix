# Debian-VMware-Fix
Vmware module not installable fix

Download the replacement files:
```
wget https://github.com/mkubecek/vmware-host-modules/archive/workstation-17.0.2.tar.gz
```
Extract the files:
```
tar -xzf workstation-17.0.2.tar.gz
```
```
cd into directory:
```
```
cd vmware-host-modules-workstation-17.0.2/
```
Create tar files of the modules:
```
tar -cf vmmon.tar vmmon-only
tar -cf vmnet.tar vmnet-only
```
Copy files to /usr/lib/vmware.modules.source (elevated privileges needed):
```
sudo cp -v vmmon.tar vmnet.tar /usr/lib/vmware/modules/source/
```
Install modules (elevated privileges needed):
```
sudo vmware-modconfig --console --install-all
```
