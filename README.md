# jenkins-agent-systemd
Running Jenkins Swarm Agent as systemd Service

**Add these three foles too /etc/jenkins/**
```
client-password
labels
swarm-client
```

**To start and stop jenkins-client**
```
systemctl start jenkins-client.service
systemctl stop jenkins-client.service
```

**To check service status**
```
systemctl status -l jenkins-client.service
```

**To check on logs**
```
journalctl -u jenkins-client -f
journalctl -u jenkins-client -f -o cat

less /var/log/messages
```

**To enable service**
```
systemctl enable jenkins-client
```
