We can install firewallD on CentOs with the help of the following command

```bash
sudo yum install firewalld
```

We can verify that the service is running and reachable by typing:

```bash
sudo firewall-cmd --state
```

We can also enable firewallD so that it runs even after the system reboot with the following command:

```bash
sudo systemctl enable firewalld
```

![enter image description here](https://i.imgur.com/Sk4LwcP.png)
