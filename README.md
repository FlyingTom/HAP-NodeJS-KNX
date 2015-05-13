

# HAPServerKNX

This repository is a fork of KhaosT's brilliant nodeJS HAP server. <br>
My intention was to push KNX integration for running the HAP server on a raspberry, using 
<ul>
<li>
<a href="https://github.com/andreek/node-eibd"> node-eibd () from andreek</a> 
<li>
<a href="https://github.com/knxd/knxd">knxd initiated by makki</a> from <a href="http://knx-user-forum.de/forum/öffentlicher-bereich/knx-eib-forum/39972-eibd-war-bcusdk-fork-knxd">http://knx-user-forum.de</a>
</ul>
I found an outdated fork from <a href="https://github.com/2ndsky">2ndsky</a> who showed where the value update function basically resides. As his fork was way behind KhaosT's, I decided for a fresh fork. Kudos for his work anyway!




## Why

I grabbed a raspberry2, with latest raspbian, installed 
<ol>
	<li>knxd (see README.md from https://github.com/knxd/knxd),
	<ul>
		<li>added <b>debhelper</b> and <b>libusb-1.0.0-dev</b> to the dependencies to get pthsem to compile
		<li>followed the tips on <a href="http://michlstechblog.info/blog/raspberry-pi-eibd-with-a-knx-usb-interface">michlstechblog.info</a> to get my GIRA USB bus interface to work
	</ul>
	<li> forked and installed KhaosT's HAP-NodeJS server
	<li> node-eibd in the node_modules folder in my project
</ol>

## Usage

_a detailed installation description to come_

## Developing

Open: <ul>
<li>create a factory to parse an export from ETS to create all accessories at once
<li>make the accessories event enabled, to reflect the changes ad-hoc
</ul>

Done:
<ul>
<li>accessory can register their KNX group addresses with a little bus monitor, to get their values updated. Siri answers with the correct state, no matter where the status change came from!
<li>can parse an OPC style address export from my ETS4 for *light switches* (DPT/EIS 1) with additional dimmers (EIS5 1 byte) absolute brightness values.
Please see documentation with the accessory files.  
</ul>

### Tools
Beeing a newbie to Javascript and nodeJS (and also to github) I tried to get some standard tools to support me ...

Created with [Nodeclipse](https://github.com/Nodeclipse/nodeclipse-1)
 ([Eclipse Marketplace](http://marketplace.eclipse.org/content/nodeclipse), [site](http://www.nodeclipse.org))   

Nodeclipse is free open-source project that grows with your contributions.
