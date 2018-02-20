# PUBG-Radar
PUBG-Radar by sniffering udp packet

![alt text](https://github.com/Jerry1211/PUBG-Radar-master/blob/master/java_2018-02-20_14-26-00.png?raw=true)

Written in Kotlin

# Build
Using [maven](https://maven.apache.org/)

# Linux

Execute the following commands on the vmware or middle pc:
1. run `sudo apt-get install dsniff` to install `arpspoof`.
2. edit `/etc/sysctl.conf`. add/uncomment `net.ipv4.ip_forward=1`. save and run `sudo sysctl -p` to enable ip_forward.
3. run `sudo arpspoof -i <eth_interface_name> -t <game_pc_ip> <router_ip>` to spoof game pc.
4. run `sudo arpspoof -i <eth_interface_name> -t <router_ip> <game_pc_ip> ` to spoof router.
5. run `sudo java -jar pubg-radar-with-dependencies.jar <middle_pc_ip> <PortFilter|PPTPFilter> <game_pc_ip>`

If you experienced `X Error of failed request:  RenderBadPicture (invalid Picture parameter)` on Linux build, try switch to branch `linux`. Run with arguments `<ip_to_sniff> <PortFilter|PPTPFilter> [target_ip]`

# PacketSniffer (for VMWare/MiddlePC)


**Note**: make sure your vmware instance or middle pc is in the same LAN as your game pc.(vmware instance should use bridged network)
Here is an easy way using [arpspoof](https://github.com/alandau/arpspoof/releases/tag/v0.1) to redirect packets from your game pc to a middle pc.

# Windows (VMWare/MiddlePC)

Follow the following instructions on your vmware or middle pc
1. run in Command Prompt 'arpsoof.exe <game_pc_ip>'
2. Run in Command Prompt 'java -jar pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar <middle_pc_ip> PortFilter <game_pc_ip>'

**Note** Load the Pubg Radar in the Menu, Press your "Push to Talk" Keybind once ingame.

# Windows (Game PC Only)
Run in Command Prompt 'java -jar pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar <game_pc_ip> PortFilter ' 
