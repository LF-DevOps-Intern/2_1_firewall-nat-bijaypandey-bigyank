Lets start by creating two network interfaces for the CentOs that each behave as a LAN and WLAN Interface.

First let's create a Bridged Adapter in the CentOs

![enter image description here](https://i.imgur.com/LIAqJrm.png)

Second we have to create Host-only Adapter. To do so first we have to click on **File>Host Network Manager>Add**. This will add the 192.168.56.1/24 IP.

![enter image description here](https://i.imgur.com/BqJuEME.png)

Now you can see vboxnet0 in the "Name" dropdown in the VM.

![enter image description here](https://i.imgur.com/56STXlD.png)

Next, we have to add Host-only Adapter on the second VM aswell.

![enter image description here](https://i.imgur.com/3TYVSre.png)

Now configure network interface on VM1(CentOs) with the following command

![](https://i.imgur.com/D0BJ9zl.png)

On VM2(Ubuntu), we have to configure the interface aswell
![](https://i.imgur.com/1vTIwBF.png)

Now lets ping between the VM1 and VM2

![](https://i.imgur.com/FKg5Ven.png)

To Share connection between these two Virtual Machines we have to add following command to the CentOs

`modprobe iptable_nat`  
`echo 1 > /proc/sys/net/ipv4/ip_forward`  
`iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE`  
`iptables -A FORWARD -i enp0s8 -j ACCEPT`

![enter image description here](https://i.imgur.com/uj3deaS.png)

On the Ubuntu Server (VM1) we have to add **192.168.56.1** as our default gateway with the following command

```bash
sudo route add default gw 192.168.56.1
```

Finally we can simply ping a server from VM2 (Ubuntu) to verify that the connection has been established.
