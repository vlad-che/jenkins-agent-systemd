# jenkins-agent-systemd
Running Jenkins Swarm Agent as systemd Service

**Add these three foles too /etc/jenkins/**
```
agent-password
labels
swarm-agent
```

**To start and stop jenkins-client**
```
systemctl start jenkins-agent.service
systemctl stop jenkins-agent.service
```

**To check service status**
```
systemctl status -l jenkins-agent.service
```

**To check on logs**
```
journalctl -u jenkins-agent -f
journalctl -u jenkins-agent -f -o cat

less /var/log/messages
```

**To enable service**
```
systemctl enable jenkins-agent
```
