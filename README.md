# jenkins-agent-systemd
Running Jenkins Swarm Agent as systemd Service

<https://wiki.jenkins.io/display/JENKINS/Swarm+Plugin>

**Add new user "jenkins-swarm" in Jenkins UI and allow this user to create new agents.**

**Create group jenkins and user jenkins on target host.**

**Add these three files too /etc/jenkins/**
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
