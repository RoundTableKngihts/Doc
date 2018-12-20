#Some Linux Skills(Mark)
------------------------
##When you are in amazo s3
*	sudo -i : change to root permission(with no password)

##How to deal with multi displays in command line?
*	Command: xrandr --output => select display's model.<br>
--right-of(--left-of) => the position which is relative to the other display.<br>
--auto ==> auto select the resolution of the display

##How to open pic like : jpg, png in command line?
*	xdg-open (in ubuntu system)

##How to open pdf in command line?
*	evince (in ubuntu system)

##How to open an image file like: png,img
*	eog

##How to add IP
*	1.sudo ifconfig eth0:1 192.168.8.43 broadcast 192.168.8.255 netmask 255.255.255.0 up
*	2.sbin/route add -host 192.168.8.43 dev eth0:1

##How to get resource from magnet url?
*	use the libtorrent of python.(did not confirm)