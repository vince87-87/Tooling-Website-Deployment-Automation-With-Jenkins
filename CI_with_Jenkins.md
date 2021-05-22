# Tooling-Website-Deployment-Automation-With-Jenkins

# Setup Jenkins

Deploy EC2 instance using jenkins

![image](https://user-images.githubusercontent.com/49937302/119209490-76478400-bad9-11eb-960d-3795417443ce.png)

# Prerequsites

#Update Repo & Install JDK
sudo apt update -y
sudo apt install default-jdk-headless -y

![image](https://user-images.githubusercontent.com/49937302/119209608-39c85800-bada-11eb-8b47-7e62d6289157.png)


# Install Jenkins
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update -y
sudo apt-get install jenkins -y

![image](https://user-images.githubusercontent.com/49937302/119210012-a5abc000-badc-11eb-92fd-142b630f67a9.png)

# Verify Service Started

![image](https://user-images.githubusercontent.com/49937302/119210082-f9b6a480-badc-11eb-82f4-71662d28699a.png)

# Allow port 8080 on security group

![image](https://user-images.githubusercontent.com/49937302/119210160-79447380-badd-11eb-92d8-12f5b6e830b0.png)

