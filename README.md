Pi Reverse Tunnel
=================

Access your raspberry pi from anywhere in the world.

1) Setup a Digital Ocean (or Amazon AWS) virtual machine 
2) On your new virtual machine configure the firewall
`sudo ufw enable`
`sudo ufw allow 22`
`sudo ufw allow 2222`
3) On your new virtual machine also configure your /etc/ssh/sshd_config (feel free to use the sshd_config in this repo)
4) On your raspberry pi, run the command that setups up the reverse tunnel
`autossh -N -R 2222:localhost:22 root@{ip address of your virtual machine}

As long as your autossh command is running, you will be able to ssh into your pi via:
`ssh -p 2222 {pi user}@{virtual machine ip address}`

Voila!  You can access your pi.
