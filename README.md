# Port Osmocom-Iuh to HUAWEI femtocells
As the main WCDMA operator in my country is relatively weak compare to the easy access lager operator's various TD-SCDMA femtocells,HUAWEI femtocell is almost the only choice for WCDMA UTRAN research.Here are some resources for developing TR-069 ACSserver for huawei femtocells configuraion and possible initiating the Iuh interface with HUAWEI's devices

The standard femtocell system map

```bash
        +------------+           +--------+          +----------+
 UE <-->| hNodeB     |<--Iuh---->| HNB-GW |<--IuCS-->| OsmoMSC  |
 UE <-->| femto cell |     ...-->|        |    ...-->|          |
        |            |           |        |          +----------+
        +------------+<--GTP-U   |        |
                              \  |        |          +------+           +------+
                              |  |        |<--IuPS-->| SGSN |<--GTP-C-->| GGSN |
                              |  +--------+    ...-->|      |   GTP-U-->|      |
                              |                      +------+  /        +------+
                              \_______________________________/
```

While the huawei also implemented its own infrastructure for femtocells operation,it's obviously similar to the standard infrastructure

![uBro](https://github.com/copslock/osmo-iuh_huawei/raw/master/huawei_ubro_infrastructure.png "uBro infrastructure")

And possible standard protocol for end-user devices management and network communication

![Ports](https://github.com/copslock/osmo-iuh_huawei/raw/master/huawei_ports.png "Huawei femto ports")

Here are some information about the HUAWEI femtocells product line,which may help you finding devices for own test.


Hisilicon SD6121 based home solution
--------

HUAWEI UAP2105

![UAP2105](https://github.com/copslock/osmo-iuh_huawei/raw/master/uap2105.jpg "UAP2105")

The one possible easiest to get in various european country which famous for the 2015's UART debug access low-tech "CVE"

HUAWEI UAP2815

![UAP2815](https://github.com/copslock/osmo-iuh_huawei/raw/master/uap2815.png "UAP2815")

Model may not entered mass production,hard to get one

HUAWEI UAP2835(2855)

![UAP2835](https://github.com/copslock/osmo-iuh_huawei/raw/master/uap2835.png "UAP2835")

Ralink 3052F AP(UAP2855 main board)+Radio board(possible form UAP2815),relative easy to get from 46001


Freescale&TI basestation chipsets solution for enterprise
--------

HUAWEI UAP3801(E)

![UAP3801](https://github.com/copslock/osmo-iuh_huawei/raw/master/uap3801b.png "UAP3801")

Easy to get from russian operator MTS and Megafon

HUAWEI UAP3801B

![UAP3801B](https://github.com/copslock/osmo-iuh_huawei/raw/master/uap3801.png "UAP3801B")

Still avaliable due to relatively higher price,but SMA port and TCI100 basestaion solution.


Resources
--------

UAP2835 Radio board system dump

```bash
https://github.com/copslock/osmo-iuh_huawei/raw/master/uap2835.7z
```

VxWorks based,possible also applied to UAP2105&UAP2815 for using almost the same chipsets


Targets
--------

I.Implementation of HUAWEI's AP Manager protocol(CWMP TR-069)

II.Solution for the IPSec certification scheme

III.Deal with the possible non-standrad Iuh protocol details


Disclaimer
--------

HUAWEI is good at 'Banning' everthing which is technical about thier product,this is just a research for helping reborn the dead sold infrastructure devices,and possible get more understanding of the current communication standards.Anything like IMSI&SMS catcher is illegal and allrights reversed 
