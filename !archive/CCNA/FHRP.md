First Hop Redundancy Protocols 
- to provide an alternate path to the internet *like a backup gateway*
- virtual ip and virtual mac are used to relay back to hosts

If R1 (active) goes down, R2 (standby) becomes active router
- note: active/standby was negotiated via multicast hello msgs
- R2 sends gratuitous arp reply to update all the switches mac address tables
- If R1 comes back online, it will become a standby (changeable)

HSRP (Hot Standby Router Protocol)
- cisco proprietary
- active, standby
- v1, v2- ipv6 & more groups
- multicast addresses
	- v1 - 224.0.0.2
	- v2 - 224.0.0.102
- virtual mac (X is the group number)
	- v1 - 0000.0c07.acXX
	- v2 - 0000.0c9f.fXXX

VRRP (Virtual Router Redundancy Protocol)
- open standard
- master, backup
- multicast: 224.0.0.18
- virtual mac: 0000.5e00.01XX

GLBP (Gateway Load Balancing Protocol)
- cisco proprietary
- load balances within _a single subnet_
- single AVG is elected
- up to 4 AVFs assigned by AVF
- multicast: 224.0.0.102
- virtual mac: 0007.b400.XXYY



