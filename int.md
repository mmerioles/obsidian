behavioral
- introduction
- motive
- goals

 
self-led design
- build configuration scripts for maintaining NSOT (netbox)
- template out network device configs from exported data (intent-based networking)
- built patching pipeline to push out configs on deployment (ci)
- preparing packaging pipelines, code linting, unit tests in pytest, batfish
- implement observability tooling - tig, suzieQ, librenms
- integrating legacy hw into modern infrastructure via NSX edge bridging

basic linux knowledge
- `ps aux | grep <process>`, `htop/top` - running processes
- `nmcli/nmtui`


troubleshooting examples
- esxi server kernel panic
	- from report - PSOD
	- vsphere alarm validate issue
	- inspect NSX - TEP down
	- inspect LibreNMS - monitoring confirms SFP stopped operating
	- maintenance window 
	- inspect physical tor (leaf) - notconnect
		- simple check - bouncing interface
	- inspect racks, confirmed link light failure
	- check if server NIC is okay
		- test with different pairs of cables
	- confirm it was physical cable issue, coordinate orders
	
- iperf performance testing mtu NSX
	- hop by hop checks
	- shorting nsx
	- removing VRF
	- working with support
	- identify MTU

-  evpn vxlan validation
	- `show ip bgp summary` - iBGP peers to all leafs from spine
	- `show bgp l2vpn evpn` - l2evpn routes
	- `show ip pim neighbor` - multicast
	- `show ip pim rm`- validate pim rp members
	- `show nvm peers` - check active vtep peers (VXLAN tunnel peers)
	- `show nve vni` - check vlan/vni mapping
	- `show ip bgp vrf ISP` - check ISP routes

- mac flapping troubleshooting
	- check routing table
	- proprietary routing protocol, built on top of rip to dictate what route should be taken
	- wireshark to start a pcap, check the advertisement message

- microhard radios
	- build mesh network
	- validate single, and multihop performance
	- plot pcap files in python to visualize packet drops, retransmits