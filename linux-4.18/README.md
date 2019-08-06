# Compile 4.18.0-25-generic 


## 1. Disable Secure Boot

## 2. Compile Kernel

```
cd linux-4.18/

sudo apt-get build-dep linux-image-$(uname -r)
sudo apt-get install libncurses5-dev flex bison libssl-dev dkms libelf-dev
sudo apt-get install git

cp /boot/config-4.18.0-25-generic  .config

make mrproper
make

sudo make modules_install
sudo make install
```


## 3. Update Grub and Reboot
```
sudo update-grub
sudo update-grub2

// update grub pointer to the correct stub
sudo vim /boot/grub/grub.cfg 
sudo vim /etc/default/grub

sudo reboot
```


## 4. Check 

Then the image should be today's date with 4.18.0
```
uname -a
```

