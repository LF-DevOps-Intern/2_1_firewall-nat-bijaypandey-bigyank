We can block a range of IPs or an entire subnet using a CIDR (Classless Inter-Domain Routing) notation. For example to reject an entire subnet in the **255.255.255.0** subnet, execute following command.

```bash
sudo firewall-cmd --permanent --add-rich-rule="rule family='ipv4' source address='192.168.2.0/24' reject"
```

After adding the rule we can reload firewalld with the help of following command

```bash
sudo firewall-cmd --reload
```

We can verify the added rule with the following command

```bash
sudo firewall-cmd --list-rich-rules
```

![enter image description here](https://i.imgur.com/wdek8QN.png)
