## Step-by-step guide for installing Jenkins on Ubuntu 24.04 LTS

**Step 1: Update Your System**

`sudo apt update && sudo apt upgrade -y`


**Step 2: Install Java**

- Jenkins needs to install Java (Java 11 or 17).

`sudo apt install openjdk-17-jdk -y`


- Verify:
`java -version`


**Step 3: Add Jenkins Repository**

- Jenkins isn’t included in the default Ubuntu repositories, so add its official repo

`curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null`

- Now add the Jenkins repo:

`echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null`


**Step 4: Install Jenkins**

`sudo apt update`

`sudo apt install jenkins -y`

**Step 5: Start & Enable Jenkins Service**

`sudo systemctl start jenkins`
`sudo systemctl enable jenkins`
`sudo systemctl status jenkins`

**Step 6: Open Firewall**

- Jenkins runs on port 8080 by default.

`sudo ufw allow 8080`
`sudo ufw reload`

**Step 7: Access Jenkins in Browser**

http://192.168.10.42:8080 (Replace with your IP address)


**Step 8: Unlock Jenkins**

- Get the initial admin password:

`sudo cat /var/lib/jenkins/secrets/initialAdminPassword`

**Step 9: Install Suggested Plugins**

- On first launch, Jenkins asks to install plugins.
- Choose Install suggested plugins (recommended).

**Step 10: Create Admin User & Start Using Jenkins**
- Set up your first admin user
- Configure URL (in production update with domain)
- Jenkins is ready

  **Step 11: Create ssimple pipeline**

  - click on **New Item**
  - Select **pileline**
  - click on **ok**
  - Click on **pipeline script**
  - From right side Select syntax **Hellow word**
  - Click on **Apply**
  - Click on **Build**

  **Cehck console output**

  <img width="520" height="298" alt="Screenshot 2025-08-16 191134" src="https://github.com/user-attachments/assets/84d4e2c7-b931-46a2-8767-37fed245f66e" />

  **Check build history**

  <img width="863" height="164" alt="Screenshot 2025-08-16 191834" src="https://github.com/user-attachments/assets/7c6311a9-c555-4a15-be4e-de72310b02cc" />

