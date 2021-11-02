We can allow services in firewalld by using following command. These commands adds the rules permanently so that these services will still be available after a reboot.

```bash
sudo firewall-cmd --zone=public --permanent --add-service=http
sudo firewall-cmd --zone=public --permanent --add-service=https
sudo firewall-cmd --zone=public --permanent --add-service=ssh

```

We can verify that this was successful by using the `--list-services` operation.

```bash
sudo firewall-cmd --zone=public --permanent --list-services
```

![enter image description here](https://i.imgur.com/Y2wI5up.png)
