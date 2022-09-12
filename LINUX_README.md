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
  
