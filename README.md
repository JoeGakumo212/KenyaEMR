Solving tomcat9 Upgrade error

sudo gedit /lib/systemd/system/tomcat9.service

a)	comment out: #SyslogIdentifier=tomcat9

b)	Add these two lines as show below;

StandardOutput=append:/var/log/tomcat9/catalina.out
StandardError=append:/var/log/tomcat9/catalina.out

c)	 Under [Service], add the following line:
ReadWritePaths=/var/lib/OpenMRS/

Save Changes

sudo systemctl daemon-reload
sudo systemctl restart tomcat9
