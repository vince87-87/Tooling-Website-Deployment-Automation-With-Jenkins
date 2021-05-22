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

# Initialize Jenkins

#Get admin password

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

#Login to browser https://jenkins-public-ip:8080

![image](https://user-images.githubusercontent.com/49937302/119210382-76964e00-bade-11eb-8b1d-ab1d1dfbbccf.png)

#Select Install Suggested plugins

![image](https://user-images.githubusercontent.com/49937302/119210395-84e46a00-bade-11eb-9a74-bab4be663f5c.png)

#Create admin account & URL which is the public dns name of the ec2 instance

![image](https://user-images.githubusercontent.com/49937302/119211005-4ea8e980-bae2-11eb-9f50-74148f60d7ab.png)

![image](https://user-images.githubusercontent.com/49937302/119211023-66806d80-bae2-11eb-9297-49e9a555fe18.png)

![image](https://user-images.githubusercontent.com/49937302/119211032-7c8e2e00-bae2-11eb-999e-3f59d00787ce.png)

# Configure Jenkins to retrieve source codes from GitHub repo using Webhooks

![image](https://user-images.githubusercontent.com/49937302/119211543-5ae27600-bae5-11eb-8388-8059b72fb851.png)

Payload: http://JENKIN-PUBLIC-IP:8080/github-webhook/

![image](https://user-images.githubusercontent.com/49937302/119243201-3515a980-bb97-11eb-9296-1d5dac633f0a.png)

Ensure last delivery is successful

![image](https://user-images.githubusercontent.com/49937302/119243229-6bebbf80-bb97-11eb-987e-d7eac1e12e96.png)

**If delivery failed under webhook, kindly check security group to allow any ip to access jenkins

![image](https://user-images.githubusercontent.com/49937302/119243265-bf5e0d80-bb97-11eb-93c9-5a67adf75994.png)

#Go to jenkins,new item:

Name: tooling_github

Freestyle project

![image](https://user-images.githubusercontent.com/49937302/119211718-61bdb880-bae6-11eb-94b2-f7f8fbb0d301.png)

#Enter github repo url & save

![image](https://user-images.githubusercontent.com/49937302/119243347-5f1b9b80-bb98-11eb-911f-4ede18608908.png)

#Run "Build now" & the console return successful

![image](https://user-images.githubusercontent.com/49937302/119243367-870aff00-bb98-11eb-90de-3f47621a1a52.png)

# Configure jenkin to trigger push automatically upon changes in repo

#go to configure, under build trigger, select "Github hook trigger for GITSCM Polling & File archive to : **

![image](https://user-images.githubusercontent.com/49937302/119243385-ca656d80-bb98-11eb-8c58-6783e3d8daf9.png)

#Change & commit read.md , build automatically trigger

![image](https://user-images.githubusercontent.com/49937302/119243448-65f6de00-bb99-11eb-8a7c-36a20014e7ce.png)

# Copy files to NFS server via ssh

#Dashboard, Manage jenkins, Manage plugins, publish over ssh , install without restart

![image](https://user-images.githubusercontent.com/49937302/119243527-1a90ff80-bb9a-11eb-9535-71c6763d1aa4.png)

![image](https://user-images.githubusercontent.com/49937302/119243539-3e544580-bb9a-11eb-96fa-7538fd4015d5.png)


