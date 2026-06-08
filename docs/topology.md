                           +----------------------+
                           |    HQ / Data Center  |
                           |----------------------|
                           | Active Directory     |
                           | DNS / NTP            |
                           | Monitoring           |
                           | Internet Access   |
                           +----------+-----------+
                                      |
                                      |
                     +----------------+----------------+
                     | MPLS / ISP Network Infrastructure |
                     +----------------+----------------+
                                      |
         -----------------------------------------------------------------
         |               |               |               |               |
         |               |               |               |               |
+--------+-----+ +-------+------+ +------+-------+ +------+-------+ +-----+--------+
| Gdansk       | | Poznan       | | Lodz         | | Wroclaw      | | Plock        |
| Router       | | Router       | | Router       | | Router       | | Router       |
+--------+-----+ +-------+------+ +------+-------+ +------+-------+ +-----+--------+
         |               |               |               |               |
         |               |               |               |               |
     +---+---+       +---+---+       +---+---+       +---+---+       +---+---+
     |Switch |       |Switch |       |Switch |       |Switch |       |Switch |
     +---+---+       +---+---+       +---+---+       +---+---+       +---+---+
         |               |               |               |               |
   --------------- --------------- --------------- --------------- ---------------
   VLAN10 Users    VLAN10 Users    VLAN10 Users    VLAN10 Users    VLAN10 Users
   VLAN11 Voice    VLAN11 Voice    VLAN11 Voice    VLAN11 Voice    VLAN11 Voice
   VLAN12 Guest    VLAN12 Guest    VLAN12 Guest    VLAN12 Guest    VLAN12 Guest