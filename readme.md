

1 1st nic
2 2st hd

`wget -qO- https://github.com/minlearn/onekeydevdesk2/raw/master/_pages/inst.sh | bash -s - -n IPV4:192.210.194.18,MASK:255.255.255.240,GATE:192.210.194.17 -t onekeydevdesk`



/etc/network/interfaces
	address 192.210.194.18/28
	gateway 192.210.194.17

mkdir /volume1
fstab
/dev/sda1 /volume1 ext4 defaults 0 0
