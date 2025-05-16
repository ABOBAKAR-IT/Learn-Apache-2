# SignIn to Server

```
ssh ubuntu@<Ip_address>

```
-> enter required pass code to login to server.

# install Apache2 
```
sudo apt install apache2

```
-> Don't install Apache2 on local Machine. 

# check Apache2 Status
```sudo systemctl status apache2``` 
# enable the service to start on boot
```sudo systemctl enable apache2```
# disable the service to start on boot
```sudo systemctl disable apache2```
# start the service
```sudo systemctl start apache2```
# stop the service
```sudo systemctl stop apache2```
# restart the service
```sudo systemctl restart apache2```

# enable mood proxy
```sudo a2enmod proxy```
# enable mood proxy_http
```sudo a2enmod proxy_http```
# enable mood proxy_balancer
```sudo a2enmod proxy_balancer```
# enable mood proxy_connect
```sudo a2enmod proxy_connect```
 
# create configration file for site
```
cd /etc/appche2/site-available  \n
touch abobakar.me.conf
```
# open file in vim mod
```sudo vim abobakar.me.conf```

# write the config file
```
<VirtualHost *:80>
    ServerName abobakar.me
    ServerAlias www.abobakar.me
    ProxyPreserveHost On
    ProxyPass / http://localhost:3000/
    ProxyPassReverse / http://localhost:3000/
<VirtualHost>
```

# enable the site
```sudo a2ensite abobakar.me.conf```
# disable the site
```sudo a2dissite abobakar.me.conf```

# restart apache2
```sudo systemctl restart apache2```


# Remove Apache2
```
sudo apt remove --purge apache^C

```
