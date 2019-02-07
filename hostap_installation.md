## Hostap Installation
1. Method 1

     * on Ubuntu linux, install using package manager
        ``sudo apt-get install hostapd``
     * set the configuration in ``/etc/hostapd/hostapd.conf``

     * edit hostapd process configuration (process deamon) path
        ``` 
            sudo nano /etc/default/hostapd
            DAEMON_CONF=/etc/hostapd/hostapd.conf        
        ```
     * start hostapd using ```sudo service hostapd start```

    N.B: This method does not offer the flexibility to edit the installation configuration as provided by method 2

2. Method 2
     
     * download hostap source ``git clone git://w1.fi/srv/git/hostap.git``
     * install the dependencies
        ```
        apt-get install -y linux-headers-"`uname -r`" build-essential
        apt-get install -y libnl-3-dev libssl-dev libssl1.0.0
        ```
     * change to installation directory. For instance, home directory ``cd $HOME``
     * download hostapd source ```git clone git://w1.fi/srv/git/hostap.git```
     * change directory to the downloaded source ``` cd hostap/hostapd```
     * edit the hostapd's configuration file for installation configuration.
     * copy ``$HOME/hostap/hostapd/defconfig  $HOME/hostap/hostapd/.config``
     * compile and install
        ```
        make clean
        make
        make install
        ```
     * stop process for network manager ``sudo service network-manager stop``
     * stop auto loading of wireless card in /etc/network/interface
        ```
        nano /etc/network/interface
        iface wlan0 inet manual
       ```
     * start using ```./hostapd ./hostapd.conf```

    N.B: Possible compilation error ```/usr/bin/ld: cannot find -lnl-genl-3 ```. Solution is by installing libnl-genl-3-dev using ```sudo apt-get install libnl-genl-3-dev```


## References

1. https://forums.kali.org/showthread.php?23054-How-to-install-Hostapd-v2-3-devel-Disable-bss-neighbor-check-force-40-MHz-channels
2. https://askubuntu.com/questions/620633/error-on-installing-aircrack-ng-usr-bin-ld-cannot-find-lnl-genl-3
3. https://wireless.wiki.kernel.org/en/users/Documentation/hostapd 