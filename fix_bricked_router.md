## How to fix a bricked TP-LINK WDR4300 router
### Method 1: Fix using 30-30-30 reset



### Method 2: Fix using serial connnector
This method should be applied only when method 1 fails.

  * Requirements:
    - USB to TTL Serial Converter CP2102
    - 3-Pin pin head connector for printed board
    - Soldering iron kit
    - Multimeter 


 


### NB: Connection to console may not work right off the bat
    * problem: After connecting the serial cable with appropriate configuration settings on computer and terminal emulator software (e.g. putty or teraterm) the console may go blank for a long period of time.
    * fix: hold down ctl+c and see if there is a response on the screen. If ctl+c doesn't work alone, hold down ctl+c while you pull out and push in the serial connector ground cable. 

### References
1. https://www.youtube.com/watch?v=t35Pei_eb6o
2. https://www.youtube.com/watch?v=wCwBvoueBG4
3. https://www.youtube.com/watch?v=fme7kwTkttk
4. https://openwrt.org/toh/tp-link/tl-wdr4300
5. http://www.rubycoloredglasses.com/2016/04/tp-link-wdr4300-recovery/