# xorg-x11-vnc

* vncserver issue font path: https://dylanninin.com/blog/2013/07/19/tigervnc_exception.html

```bash
$ mkdir $HOME/.vnc

$ cat $HOME/.vnc/xstartup |egrep -v '#'|grep -v "^$"
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &
x-terminal-emulator -geometry 80x24+10+10 -ls -title "$VNCDESKTOP Desktop" &
x-window-manager &
exec /usr/bin/mate-session

$ systemctl get-default
$ systemctl set-default graphical.target




yum update
yum install epel-release
yum update
yum install xorg-x11*
yum groupinstall "X Window system"
yum groupinstall "MATE Desktop"

yum install lightdm-gtk lightdm-settings
systemctl set-default graphical.target
systemctl get-default

yum install pixman pixman-devel libXfont
yum update libXfont

vncserver
To resolvfont path error see here
vncserver -geometry   -fp /etc/X11/fontpath.d
```
