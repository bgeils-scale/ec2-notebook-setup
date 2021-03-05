# ec2-notebook-setup

The following setup allows you to develop and train models in on an ec2 instance, while developing in your native chrome browser. 

1. Navigate to Okta and open AWS, change your role to one which allows EC2 instance creation. 
2. Create a new EC2 instance (I recommend Ubuntu 18 on a box that has a graphics card, this will depend on the size of your jobs, Step 4: Add storage - bump this up since the default is 8gb)
3. Create a private key, or download the one provided during instance creation. 
4. Set the security permissions on the box (change the default inbound port 22 to 'My IP' - be aware you need to change this every time you change locations however it's an extra layer of security that is worth it)
5. Set your `~/.ssh/config` as such. Replace Hostname and IdentityFile
```
Host myNewServer
  Hostname ec2-3-129-217-106.us-east-2.compute.amazonaws.com
  IdentityFile IdentityFile ~/.ssh/bgeils_aws_key.pem
  User ubuntu
  LocalForward 8001 localhost:8888
```
6. Login to your new EC2 box `ssh myNewServer` - press enter the first time when prompted with `Are you sure you want to continue connecting (yes/no/[fingerprint])?`
7. Install tmux
```
sudo apt update
sudo apt install tmux
```
8. 
