# Deauth-packets-injection
__NOTE: This script is only for educational and learning purposes and I am not responsible for misuse. Never use it to annoy or harm other people or systems. Use it only against your own networks and devices!!!__



This script injects many deauth packets against a client connected to an Access Point. So, what is a deauth packet?
> Deauthentication packets are legitimate from the IEEE 802.11 standard and are used for disconnect a client from the wireless network for
> various reasons. For example, when the password  its wrong, the AP send this packet to avoid that the client connects. Other example, 
> when the network reach the maximum number of possible connected clients, the AP sends deauth packets to the next clients that try to 
> connect.

Here is an example of how this packets are injected (left). Also we can view an deauthentication packet sniffing (right). As we can view, this packets need a source and destination MAC addresses.
<p align="center">
  <img src="https://github.com/davidahid/Deauth-packets-injection/blob/master/images/imgs.png">
</p>

Knowing all this, we can use it to inject packets at our will to disconnect a specific device from almost any network.
The program that we going to use is the aircrack-ng suit in Kali Linux.

### Configuration
First we need to install the aircrack-ng suite. There is two methods:

__First method:__
```sh
sudo apt-get update
sudo apt-get install aircrack-ng
```

__Second method:__

We install all the dependencies for aircrack.
```sh
sudo apt-get -y install build-essential libssl-dev libnl-3-dev libnl-genl-3-dev dpkg-dev g++ g++-4.8 libc-dev-bin libc6-dev libstdc++-4.8-dev zlib1g-dev debian-keyring g++-multilib g++-4.8-multilib gcc-4.8-doc libstdc++6-4.8-dbg glibc-doc libstdc++-4.8-doc libalgorithm-merge-perl libssl-doc libalgorithm-diff-xs-perl
sudo apt-get update
```
And now we just download, decompress, compile and install the suite.
```sh
wget https://download.aircrack-ng.org/aircrack-ng-1.5.2.tar.gz
tar -zxvf aircrack-ng-1.2-rc4.tar.gz
cd aircrack-ng-1.2-rc4
make
make install
```
