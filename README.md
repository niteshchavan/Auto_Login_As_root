# install Xorg
```
sudo apt-get install xserver-xorg -y

sudo apt-get install xinit -y

sudo apt-get install x11-xserver-utils -y
```


# Auto_Login_As_root
Auto login as root

# Source

https://www.nixcraft.com/t/how-to-configure-autologin-on-the-raspbian-buster-console/3922/2

nano /etc/systemd/logind.conf
```
[Login]

NAutoVTs=1
```

# Enable Auto login using raspi-config option is B2 using pi text login

nano /etc/systemd/system/getty@tty1.service.d/autologin.conf
```
ExecStart=-/sbin/agetty --autologin root --noclear %I $TERM
```
 nano /root/.profile
 ```
 [[ -z $DISPLAY && $XDG_VTNR -eq 1 ]] && startx -- -nocursor
 ```
# Running Tkinter in GUI if error is display not found 
 
export DISPLAY=0.0 #if not working then set dislpaly value to DISPLAY:0

xhost +  #allows to use any display no restrictions
 
