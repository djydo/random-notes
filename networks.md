# Computer Networks

1. Transport Protocols: reassembles data segment into data streams. The two common transport protocols are TCP and UDP. Other transport protocols include DCCP (Datagram Congestion Control Protocol), SCTP (Stream Control Protocol), RSVP (Resource Reservation Protocol) etc.  The illustration of TCP 3-way handshake is given below.

    ```ascii
        client ------------------SYN------------------->>> server
        client <<<---------------SYN/ACK------------------ server
        client ------------------ACK------------------->>> server
    ```

    TCP is a connection oriented communication. It sets up a transport layer connection using (3-way handshake or call setup), establishes a virtual circuit, segment data stream, sequence each tranmitted segment and tears down the connection when transmission is done.  

2. View, save and erase configuration on Cisco router
   - view ios version and running configuration on RAM

   ```bash
        Corp#show running-config
        Building configuration...

        Current configuration : 1226 bytes
        !
        version 12.4
        no service timestamps log datetime msec
        no service timestamps debug datetime msec
        service password-encryption
        !
        hostname Corp
        !
        !
        !
        enable secret 5 $1$mERr$FfVcDhEqgnRRRoHAYAyaG0
        !
        !
        !
        !
        !
        !
        no ip cef
        no ipv6 cef
        --More--
   ```

   - save configuration

   ```bash
            Corp#copy run startup-config
            Destination filename [startup-config]?
            Building configuration...
            [OK]

            Corp#wr
            Building configuration...
            [OK]
   ```

   - Erase startup configuration

   ```bash
        Corp#erase startup-config 
        Erasing the nvram filesystem will remove all configuration files! Continue? [confirm]
        [OK]
        Erase of nvram: complete
        %SYS-7-NV_BLOCK_INIT: Initialized the geometry of nvram
   ```
