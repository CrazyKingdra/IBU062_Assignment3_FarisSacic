Devices in the network:
-Router: Cisco ISR4331
-Switch 1: Cisco 2960 IOS15
-Switch 2: Cisco 2960 IOS15
-Host Configs:
 -PC0:168.90.0.3
 -PC1:168.90.0.4
 -SERVER0:168.90.0.5
 -LAPTOP0:168.90.0.2
 -SERVER1:210.3.14.2
 -SERVER2:210.3.14.3
 -PC2:210.3.14.4
 -PC3:168.90.0.6
 -PC4:210.3.14.5

 DHCP Config:
 After finishing the network topology I entered the CLI of the router after which I used the following commands:

 enable
 configure terminal
 interface GigabitEthernet 0/0/0
 ip address 168.90.0.1 255.255.0.0
 no shutdown
 exit
 interface GigabitEthernet 0/0/1
 ip address 210.3.14.1 255.255.255.0
 no shutdown
 exit
 ip dhcp pool SWITCH1
 network 168.90.0.0 255.255.0.0
 default-router 168.90.0.1
 exit
 ip dhcp pool SWITCH2
 network 210.3.14.0 255.255.255.0
 default-router 210.3.14.1
 exit