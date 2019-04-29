### Installation of Cisco Packet Tracer 7.2 on Linux Machine

1. Download the Linux installation binary
2. Copy the download into a directory (folder)
3. Extract contents of the downloaded file using ```tar -xvf <file_name>```
4. Install using command: ``./install``
5. Read the license agreement and type 'Y' to accept
6. Set Packet Tracer and QT environment variables using ``set_ptenv.sh`` and ``set_qtenv.sh`` respectively. Ensure the files are executable (``chmod +x <filename>``). To set the environment variables, use the following commands
    ```
    ./set_ptenv.sh
    ./set_qtenv.sh
    ```
7. Type ``packettracer`` at the prompt to run Packet Tracer application.

### Note:
The Packet Tracer application may fail to run. This could be as a result of missing dependencies.
   * switch to installation directory and run ```ldd PacketTracerX | grep “not found”`` 
   * 'PacketTracerX' is the installed version of Packet Tracer e.g. PacketTracer7 or PacketTracer8
   * download and install the missing dependencies.

### Reference
[computer networking notes](https://www.computernetworkingnotes.com/ccna-study-guide/how-to-install-and-start-packet-tracer-in-ubuntu.html)