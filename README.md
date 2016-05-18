piControl is allow reboot and shutdown from browser in local network. It's using node.js.

## Install Node.js
	curl -sLS https://apt.adafruit.com/add | sudo bash
	sudo apt-get install node

## Install forever

	npm install forever -g
	
## Copy file

	sudo mkdir /opt/piControl/
	
Copy all files to /opt/piControl/

or you can make git clone

	cd /opt
	sudo git clone git://github.com/saturngod/piControl.git piControl

## Edit Control file

Open the pictlnode.

Edit **forever** and **APP** path.

## Create Service

	sudo cp /opt/piControl/pictlnode /etc/init.d/pictlnode
	sudo chmod +x /etc/init.d/pictlnode
	update-rc.d pictlnode defaults
	sudo insserv pictlnode
	reboot
	
After reboot , check your ip first.

	ifconfig
	
After you know the IP , call ***http://[your_ip_address]:1337*** from any browser in your local network.

Recommend to use static IP to control the raspberry pi.


## API

### Shutdown

http://[yourip]:1337/shutdown

### Restart

http://[yourip]:1337/restart

### Free Space

http://[yourip]:1337/freedisk

## Todo 

- Make installer like `npm install picontrol` and everything done.
