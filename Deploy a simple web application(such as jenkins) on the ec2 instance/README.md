## Create an EC2 instance
- Create an EC2 instance with a security group having inbound rule for protocol 'custom TCP'and port '8080'

- Install Java JDK

```
sudo apt update
sudo apt install openjdk-17-jre
java --version
```
- Install Jenkins 

```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

