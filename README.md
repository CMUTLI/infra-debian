# Installation Procedures for TLI Debian Systems

## 1. Boot standard netinst
## 2. Select Advanced options

![Screenshot showing Advanced Options selected](/assets/1-advanced.png)

## 3. Select Automated install

![Screenshot showing Automated Install selected](/assets/2-automated.png)

## 4. Enter Debian preconfiguration file location
Use `debian.tli.cmu.edu`; it will assume the default file path for the distribution.

![Screenshot showing Download Debconf Preconfiguration File URI entered](/assets/3-preseed.png)

## 5. Enter a temporary root password
The first `state.apply` by salt will override it, so just go wih something that can't be owned before you do the inital salt.

![Screenshot showing a default root password entered](/assets/4-root.png)

## 6. Confirm temporary root password

![Screenshot showing a root password confirmation entered](/assets/5-root-confirm.png)

## 7. Enter a temporary deploy user password
The default username of `deploy` is provided by the preseed file. The first `state.apply` by salt will also override this, so just go wih something that can't be owned before you do the inital salt.

![Screenshot showing a default deploy password entered](/assets/6-deploy.png)

## 8. Confirm temporary deploy user password

![Screenshot showing a deploy password confirmation entered](/assets/7-deploy-confirm.png)

## 9. Reboot
Assuming the `preseed/late_command` to install salt was successful, the salt minion will be running after the reboot and a key will be pending on the salt master. There's no actual need to login to the machine directly. See the Eberly documentation for saltstack to go from here.

Note: For inspection, the salt bootstrap script will be available under `/home/deploy`. To debug the salt installation or review the salt installation output, it's redirected to a `.out` file colocated with the bootstrap script.
