# CPS 706: Lab 5 - ICMP

Mitchell Mohorovich - 500563037

![ping](https://i.imgur.com/yM7IX03.png)

 Ping screenshot

1. *What is the IP address of your host? What is the IP address of the destination host? *

 The IP address of my host is `141.117.233.56`. The IP address of the destination host is `143.89.14.12`.

2. *Why is it that an ICMP packet does not have source and destination port numbers?*

 There is no source and destination because ICMP runs on the network layer, not the application layer. Every ICMP packet has *Type* and *code* instead. These are used for packet identification.

3. *Examine one of the ping request packets sent by your host. What are the ICMP type and code numbers? What other fields does this ICMP packet have? How many bytes are the checksum, sequence number and identifier fields?*

 The ICMP type is `8`, and the code is `0`. The ICMP packet also has checksum, 2 identifier, 2 sequence number and a data field. The checksum, sequence number and identifier fields are all 2 bytes each.

4. *Examine the corresponding ping reply packet. What are the ICMP type and code numbers? What other fields does this ICMP packet have? How many bytes are the checksum, sequence number and identifier fields?*

 The ICMP type is `0`, and the code is also `0`. The ping reply packet has the same fields as the request packet: checksum, 2 identifier, 2 sequence number and data field.

 ![tracert](http://i.imgur.com/M80GsnQ.png)

 Tracert screenshot

5. *What is the IP address of your host? What is the IP address of the target destination host?*

 The IP address of my host is `141.117.233.56` and the destination IP is `128.93.162.84`.

6. *If ICMP sent UDP packets instead (as in Unix/Linux), would the IP protocol number still be 01 for the probe packets? If not, what would it be?*

 The IP protocol number would not be 01, it would be 11.

7. *Examine the ICMP echo packet in your screenshot. Is this different from the ICMP ping query packets in the first half of this lab? If yes, how so?*

 It is not different, it contains the same fields as the ping query ICMP packets.

8. *Examine the ICMP error packet in your screenshot. It has more fields than the ICMP echo packet. What is included in those fields?*

 The ICMP error packet is not the same as the ICMP echo packet. This packet contains the IP header, as well as the original ICMP packet the error is for.

9. *Examine the last three ICMP packets received by the source host. How are these packets different from the ICMP error packets? Why are they different?*

	The last three packets are type 0, rather than 11. They are different because that means the datagrams successfully reached the destination host before the TTL expired.

10. *Within the tracert measurements, is there a link whose delay is significantly longer than others?  Refer to the screenshot in Figure 4, is there a link whose delay is significantly longer than others?  On the basis of the router names, can you guess the location of the two routers on the end of this link?*

 The link between 11 and 12 shows a very large jump in delay. From the names in the figure, it is the link from New York, USA to Aubervilliers, France, which is across the Atlantic ocean.