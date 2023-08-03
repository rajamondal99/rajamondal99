# First you need to open port 22 for ssh connection


1 To open port 22 in Ubuntu, you can follow these steps:

- Check if the UFW firewall is enabled.
  
 ```sudo ufw status```
 
- If the UFW firewall is not enabled, you can enable it by running the following command:

```sudo ufw enable```

- Allow the SSH port 22 through the firewall.
```sudo ufw allow 22```
Verify that the SSH port is open.

```sudo ufw status verbose```

The output of the sudo ufw status verbose command should show that the SSH port is open.

Here is an example of the output of the ```sudo ufw status verbose``` command:

```
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To Action From
-- ------ ----
22/tcp ALLOW IN Anywhere
22/tcp (v6) ALLOW IN Anywhere (v6)
```

The 22/tcp ALLOW IN Anywhere line indicates that the SSH port is open and that connections are allowed from anywhere.

Once you have opened port 22, you should be able to connect to your Ubuntu server using SSH.

Here is an example of how to connect to your Ubuntu server using SSH:

ssh username@hostname
Replace username with your username and hostname with the hostname or IP address of your Ubuntu server.




# Next you have to install openssh-server


To connect to another Ubuntu system on the same network using SSH (Secure Shell), you need to follow these steps:

1. Enable SSH on the remote Ubuntu system:
   - Open a terminal on the remote system.
   - Install the OpenSSH server if it's not already installed:
     ```
     sudo apt update
     sudo apt install openssh-server
     ```
   - Once installed, the SSH service should start automatically. If not, start it with:
     ```
     sudo service ssh start
     ```
   - Verify that the SSH service is running:
     ```
     sudo service ssh status
     ```
   - Note down the IP address or hostname of the remote Ubuntu system.

2. Connect to the remote Ubuntu system from your local Ubuntu system:
   - Open a terminal on your local system.
   - Use the `ssh` command followed by the username and the IP address (or hostname) of the remote system to initiate the connection:
     ```
     ssh remote_username@remote_ip_address
     ```
     Replace `remote_username` with the username on the remote system and `remote_ip_address` with the IP address or hostname of the remote system.

   - If it's the first time you're connecting to the remote system, you'll be prompted to add the remote system's fingerprint to your known hosts. Type `yes` to proceed.
   - You will then be asked for the remote user's password. Enter the password associated with the username you provided.
   - If everything is correct, you should now be logged in to the remote Ubuntu system via SSH.

That's it! You are now connected to the remote Ubuntu system using SSH. You can execute commands on the remote system, transfer files using `scp`, or use any other SSH-related functionality. Remember to properly secure your SSH connections by using strong passwords or, preferably, public key authentication.


