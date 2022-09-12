# Linux

cat /etc/*release* --> gives the linux version
ls /etc/*release* 


To download
-------------
wget <url> -O <file_name>
curl <url> -O <file_name>
  
Vi
--
h j k l [for the arrows in command mode]
h j l.  < up >
  k      down
  
  
y to copy and p to paste
/of --> to search 
/of --> and press 'n' to move to next occurance.
  
  
Package manager
  --------
  
  //doesn't install dependent packages. YUM installs all the dependent packages in order.
 
  rpm -i <package-name>//install
  rpm -e <package-name> //uninstall
  rpm -q <package-name> //search
  rpm -qa //list all installed rpm packages
  
  
  yum repolist //extra packages
  
  
  yum --showduplicates list ansible
  
  yum list ansible
  
  
  Srevice
  -------
  
  service httpd start
  systemctl start httpd
  systemctl stop httpd
  systemctl enable httpd
   systemctl disable httpd
  
  
  
  /etc/systemd/system
  --> to start the application as service.
  
  /usr/lib/systemd/system/my_app.service
  
  my_app.service [docker.service is configured as a systemctl command. you can see this when docker is installed.]
  ---------
  
  [service]
  ExecStart=/usr/bin/python3 /opt/code/my_app.py
  
  [install]
  WantedBy=multi-user.target  --> start when the system starts. after the 'multi-user.target' runlevel is started and do 'systemctl enable my_app'.
  
  
  systemctl daemon-reload
  
  systemctl start my_app
  

  
  Hypervisors
  ------------
  
  Type 1 --> No OS [vmware]
  Type 2 --> OS on top which a virtualization software is installed [oracle virtual box, vmware workstation [private]]

  osboxes.org - various images supported for virtual box to install OS.
  
  port forwarding --> forward ssh port from host to guest to make the guest vm reachable from other machines. [forward a port from host to guest].
  
    ssh root@127.0.0.1 -p 2222 // do it on the guest OS terminal [configure port forwarding in virtual server Networking option]
  
  Host only Network
  -----------------
  File > Host > Host Network Manager
    -> created a host-only network [private network] so that VMs in virtualbox can connect each otehr
  
    --> Settings -> Network -> Adapter -> Host oNly Network created earlier
  
  option1 : Enable IP forwarding in the host to enable internet connectivity for the VMs.
  option2 : Enable NAT on the second network adapter to enable internet connectivity for the VMs.
  
  NAT Network [VMs can access outside world]
  -----------
  refer image in folder
  
  Bridge Network [Outside systems can access VM]
  -----------
  
  Cloning - VM should be turned off to clone a VM.
    Adapter 1 --> NAT for network connectivity
    Adapter 2 --> Connect to Host Netwrok.
  
  
  
