# #Capture-packets-with-tcpdump
* One of the more useful tools when testing Linux systems is TCPDUMP, which we can use to capture TCP packets that are transmitted on the local network. While more advanced tools such as Wireshark are ideal for displaying and analyzing packets. TCPDump is a raw capture tool, which comes into its own when doing remote captures.
* You'll need to make sure when you're trying to capture packets from other hosts on the network that you've got promiscuous mode set, this is set in the virtual machine configuration, under network, advanced
# Tools and operating systems used 
* Tools -> tcpdump
* Os -> linux
# Task 1 To provide list of network interfaces
 command -> $ tcpdump -D 
* above command provides list of network inetrfaces
* make sure linux is case sensitive operating system
# Task 2 Capture the any interfaces packets
command -> $ tcpdump -c 10 -i any
* -c specifies count of packets to capture
* -i specifies interface to listen
# Task 3 Suppressed host name resolution and port name resolution
command -> $ tcpdump -c 10 -i eth0 -nn
* The -nn option ensures that IP addresses and protocol numbers are not resolved, which can help speed up the process by avoiding DNS lookups and protocol number resolutions
#  Task 4 Capture traffic from host
command -> $ tcpdump -c 10 host 192.168.XXX.XXX
* This command provides packet traffic of specified host
# Task 5 Capture UDP packets from the network
command -> $ tcpdump -c 10 udp
# Task 6 Network traffic from subnet
command -> $ tcpdump net 192.168.XXX.0/24
#Task 7 Capture the network packets from the host with specified port
command -> $ tcpdump -c 10 port 22 host 192.168.XXX.XXX
# Task 8  Drag and drop the captured network packets information in outputfile with specifiec filter
command -> $ tcpdump -c 10 ip6 -w ip6.pcap
* This command captures 10 IPv6 packets and saves them to a file named ip6.pcap. Here is a breakdown of the command:
* -c 10: Captures 10 packets and then stops.
ip6: Filters for IPv6 packets.
-w ip6.pcap: Writes the captured packets to a file named ip6.pcap instead of displaying them on the terminal.
# Task 9 Looking into multiple port traffics
command -> $ tcpdump -c 10 ' src 10.10.10.6 and (dst port 21 or 22 or 23)'
* This command will capture 10 packets (-c 10) that originate from the source IP address 10.10.10.6 and are destined for ports 21, 22, or 23
# Task 9 breakdown of what the command does:
 * tcpdump: The command-line utility used for capturing and analyzing network traffic.
* -c 10: This option specifies that tcpdump should capture 10 packets and then stop.
* src 10.10.10.6: This filter specifies that only packets originating from the source IP address 10.10.10.6 should be captured.
* (dst port 21 or 22 or 23): This filter specifies that only packets destined for ports 21, 22, or 23 should be captured.
* Port 21 is typically used for FTP (File Transfer Protocol).
* Port 22 is typically used for SSH (Secure Shell).
* Port 23 is typically used for Telnet.
