### Quick conversion technique for decibel to watts

1. Left-hand-side (LHS) is decibel while right-hand-side (RHS) is watts.
    * 10 dB is approximately equal to 10 W
    * doubling on watts scale is 3 dB e.g. 1 W -> 2 W = 3 dB, 3 mW -> 6 mW = 3 dBm

    ```c
    LHS (dB)    aproximately equal to  RHS (watts)
    10 dB        = 10 W
     3 dB        = 2 W
    ```

2. Operation:
   * addition on LHS is multiplication on RHS
   * subtraction on LHS is division on RHS


    ```c
    addition on  = multiplication 
    subtraction  = 
    
    Convert 17 dB  to Watts.
          17 dB
    (20 - 3) dB     = ((10 * 10)/2) W
                    = (100/2) W
                    = 50 W
     17dB is approximately equal to 50 W
    ```                