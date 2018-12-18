# OpenWrt Configuration
The current wireless configuration on OpenWrt device is available at `\etc\config\wireless`
To view the configuration
```
cat \etc\config\wireless
```
## set a configuration
For example: enabling a wifi radio interface card `iface[0]` on a device can be set using command

```
uci set wireless.@wifi-iface[0].disabled=0; uci commit wireless; wifi
```
To set an STA to ignore fat channel intolerability (allowing the use of 40 MHz bandwidth on 2.4 GHz), use the following command. Note that this may violate the country's regulatory policy/restrictions.
```
uci set wireless.radio0.noscan=1
uci commit
reboot
``` 


## reset driver
To reset the driver, use the following command.
 ```
  wifi down && sleep 5 && wifi
 ````

## common 
Some common device configuration options.[1](https://oldwiki.archive.openwrt.org/doc/uci/wireless)
```
require_mode='g'
channel='auto'
```
  - require_mode:  (ap mode) Set the minimum mode that connecting clients need to support to be allowed to connect. Supported values are `g = 802.11g`, `n = 802.11n` or `ac = 802.11ac`

  - channel: Specifies the wireless channel to use. "auto" defaults to the minimum channel available 

## for ath9k
Some specific device configuration.[1](https://oldwiki.archive.openwrt.org/doc/uci/wireless)
```
htmode='HT40+'
chbw='20'
```
  - htmode: specifies the channel width in `802.11n` and `802.11ac` mode. 
  
    The possible values are:
              HT20 (single 20MHz channel),
              HT40- (2x 20MHz channels, primary/control channel is upper, secondary channel is below)
              HT40+ (2x 20MHz channels, primary/control channel is lower, secondary channel is above).
              HT40 (2x 20Mz channels, auto selection of upper or lower secondary channel on versions 14.07 and above). 
              NONE (disables 802.11n rates and enforce the usage of legacy 802.11 b/g/a rates)
              VHT20 / VHT40 / VHT80 / VHT160 (channel width in 802.11ac, extra channels are picked according to the specification) 
    
   - chbw: specifies a narrow channel width, possible values are: 5 (5MHz channel), 10 (10MHz channel) or 20 (20MHz channel). 



## References

1. https://oldwiki.archive.openwrt.org/doc/uci/wireless
2. https://www.smallnetbuilder.com/wireless/wireless-features/31743-bye-bye-40-mhz-mode-in-24-ghz-part-1
3. https://forum.openwrt.org/t/40mhz-802-11n-setup-saved-but-is-20mhz-wide/19547/23
4. http://support.huawei.com/enterprise/en/knowledge/EKB1000079063 
5. http://lists.shmoo.com/pipermail/hostap/2012-October/026781.html
6. http://wiki.ninux.org/40MHzTable
7. Primary and secondary channel https://www.cwnp.com/802-11n-primary-and-secondary-channels/
8. 40 MHz channel on 2.4 GHz: https://github.com/kaloz/mwlwifi/issues/25