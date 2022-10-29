# 112628
Setting up Ubuntu Server cloud image using cloud-init.

Requires running on a Linux system somewhere (guest or host).

1. Install `genisoimage`.
    ```shell
    sudo apt install genisoimage
    ```

2. Create a `user-data` file.

    ```shell
    #cloud-config
	users:
	  - default
	  - name: tom
		ssh-authorized-keys:
          - ssh-rsa ...
		sudo: ALL=(ALL) NOPASSWD:ALL
		groups: sudo
		shell: /bin/bash
    ```

3. Create a `meta-data` file.

	```shell
	hostname: ubuntu01
	```

5. Create a `network-config` file to configure a static IP.

    ```shell
    version: 2
    ethernets:
      enp0s8:
	match:
	  name: enp0s8
	addresses:
	- 192.168.56.11/24	
    ```

4. Create userdata.iso file. This step assumes that the host has a shared file system (folder) in `/mnt/host`.

	```shell
	genisoimage -output /mnt/host/userdata.iso -volid cidata -joliet -rock user-data meta-data
	```

5. Add the userdata.iso to the CD device on the cloud image VM.

## References

* [cloud-init networking](https://cloudinit.readthedocs.io/en/latest/topics/network-config.html) 
* [NoCloud datasource](https://cloudinit.readthedocs.io/en/latest/topics/datasources/nocloud.html). This is used on my machine since I'm using VirtualBox. YMMV
 
