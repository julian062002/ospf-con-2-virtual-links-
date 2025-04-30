# configuracion 
## router core 1
```conf 
Router>ENA
Router#CONF T
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#NO LOGGING CONSOLE
Router(config)#NO IP DOMAIN LOOKUP
Router(config)#HOSTNAME ROC1
ROC1(config)#INT G 0/1 
ROC1(config-if)#IP ADD 10.0.0.1 255.255.255.252
ROC1(config-if)#NO SHUT
	
ROC1(config-if)#INT G 0/0
ROC1(config-if)#IP ADD 10.0.0.22 255.255.255.252
ROC1(config-if)#NO SHUT

ROC1(config-if)#INT G 0/2/0
ROC1(config-if)#IP ADD 10.0.2.2 255.255.255.252
ROC1(config-if)#NO SHUT

%LINK-5-CHANGED: Interface GigabitEthernet0/2/0, changed state to down
ROC1(config-if)#INT LOOPBACK0

ROC1(config-if)#IP ADD 10.10.0.0 255.255.255.255
ROC1(config-if)#NO SHUT
	
ROC1(config-if)#ROUTER OSPF 1
ROC1(config-router)#NETWORK 10.10.0.0 0.0.0.0 AREA 0
ROC1(config-router)#NETWORK 10.0.0.0 0.0.0.3 AREA 0
ROC1(config-router)#NETWORK 10.0.0.20 0.0.0.3 AREA 0
ROC1(config-router)#NETWORK 10.0.2.0 0.0.0.3 AREA 5
```

