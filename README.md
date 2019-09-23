# jenkins-agent-systemd
Running Jenkins Swarm Agent as systemd Service

<https://wiki.jenkins.io/display/JENKINS/Swarm+Plugin>

1. Add new user "jenkins-swarm" in Jenkins UI and allow this user to create new agents.
2. Create group jenkins and user jenkins on target host.
3. Install Swarm Plugin on master
4. Download jar from master ${JENKINS_URL}/swarm/swarm-client.jar and place it to /var/lib/jenkins/swarm-client.jar, owned by jenkins.
5. Next, follow steps below, dont forget to update variables in swarm-agent according to you setup

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
