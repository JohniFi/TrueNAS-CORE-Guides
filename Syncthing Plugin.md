# How to Install Syncthing Plugin on TrueNAS core
## 1. Install Syncthing Plugin
1. **TrueNAS** -> **Plugins** -> **Syncthing** -> **INSTALL**
2. Choose **DHCP** (or **NAT**)
## 2. Add associated User
1. **TrueNAS** -> **Accounts** -> **Groups** -> **ADD**
	- ***GID***: *983*
	- **Name**: *syncthing*
1. **TrueNAS** -> **Accounts** -> **Users** -> **ADD**
	- **Username**: *syncthing*
	- **User ID**: *983*
	- **Primary Group**: *syncthing*
	- **Disable Password**: *yes*
	- **Samba Authentication**: ☑ -> ☐
## 3. Add a Dataset and set permissions
1. TrueNAS -> Storage - Pools
2. Add a Dataset for Syncthing Data (e.g. tank/syncthing_data)
3. **⋮** -> **Edit Permissions**
4. **User**: *syncthing*
5. **Apply User**: ☑
6. **Group**: *syncthing*
7. **Apply Group**: ☑
## 4. Set Mountpoints
1. **Plugins** -> *syncthing* -> **MOUNT POINTS** -> **ACTIONS** -> **Add**
	- e.g. */mnt/tank/syncthing* -> */mnt/tank/iocage/jails/syncthing/root/mnt/data*
## 5. Enable ssl
1. **TrueNAS** -> **Plugins** -> *Syncthing* -> **MANAGE**
2. Syncthing GUI -> Actions -> Settings -> GUI
	- **GUI Listen Address**: *0.0.0.0:8384* (this will bypass nginx)
	- **GUI Authentication User**: *some_username*
	- **GUI Authentication Password**: *secret_password*
	- **Use HTTPS for GUI**: ☑
3. To manage Syncthing go to https://[ip_adress]:8384/ 
-----
#TrueNAS #Syncthing
