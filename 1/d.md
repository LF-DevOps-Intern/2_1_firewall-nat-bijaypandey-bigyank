We can also add a specific port to the firewall rule with the following command:

```bash
sudo firewall-cmd --zone=public --permanent --add-port=5000/tcp
```

To add a range of port we can use the following command

```bash
sudo firewall-cmd --zone=public --permanent --add-port=4990-4999/udp
```
