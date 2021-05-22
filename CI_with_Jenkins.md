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

# Configure Jenkins to retrieve source codes from GitHub using Webhooks



