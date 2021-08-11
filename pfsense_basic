# Firewall
#### Managing the firewall rule
+ Firewall rules restrict access from the Internet.
+ Understanding the term:
	+ `Rule`: **single entry** on the `Firewall` > `Rules`. A rule instructs the firewall how to handle traffic.
	+ `Ruleset`: a **group of rules**. Either all firewall rules as a whole, or a set of rules in a specific context on an interface tab.

+ *Note:* Always keep this in mind when creating new rules, especially when crafting rules to restrict traffic. The most permissive rules should be toward the bottom of the list, so that restrictions or exceptions can be made above them.

<hr>

# Stateful Filtering
+ pfsense remembers information about connections flowing through the firewall so that it replies that traffic automatically. This data is retained in the **State Table**.
+ This mechanism indicates that traffic **only need** permission from the interface when it enters the firewall.

<hr>

# State Table Size
+ The firewall state table has a maximum size ~1KB of RAM per state. 
+ The default state table size of pfsense takes 10% of the RAM available in the firewall. If we configure 1GB of RAM for the firewall, the state table size can hold approximately 100,000 entries.
+ To increase the state table size:
	+ Navigate to `System` -> `Advanced` on the `Firewall & NAT` tab.
	+ Enter the desired number of **Firewall Maximum States**.
	+ Click `Save`

<hr>

# Block & Reject
+ There are two ways to disallow traffic using firewall rules on the pfsense: `Block` and `reject`
+ Differences between them:
	+ The rule set to `block` will silently drop traffic. This is the behavior of the default deny rule in pfSense.
	+ The rule set to `reject` will response back to the client for denied `TCP` and `UDP` traffic.
		+ Rejected `TCP` will receive `TCP RST` packet in response.
		+ Rejected `UDP` wll receive `ICMP` unreachable packet in response.
		+ Also note that packets with IP protocols other than `TCP` and `UDP` will be silently dropped. 
+ `block` is recommended for WAN.
+ `reject` is recommended for LAN.
