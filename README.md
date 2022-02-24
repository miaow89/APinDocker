## remove Comment
#### net.ipv4.ip_forward=1

~~~
sudo vi /etc/sysctl.conf
~~~

## add to the end of file
#### denyinterfaces wlan0

~~~
sudo vi /etc/dhcpcd.conf
~~~

## execute Command
~~~
sudo curl -sSL https://get.docker.com | sh
sudo apt-get install libffi-dev libssl-dev -y
sudo apt-get install -y python python-pip
sudo pip install docker-compose
~~~
~~~
sudo docker build . --tag autowlan
sudo docker run -d --name autowlan_open --cap-add=NET_ADMIN --network=host  autowlan
~~~
## execute Command with WEP

~~~
sudo docker run -d --name autowlan_wep --cap-add=NET_ADMIN --network=host -v $(pwd)/confs/hostapd_confs/wep.conf:/etc/hostapd/hostapd.conf autowlan
~~~


## execute Command with WPA2

~~~
sudo docker run -d --name autowlan_wpa2 --cap-add=NET_ADMIN --network=host -v $(pwd)/confs/hostapd_confs/wpa2.conf:/etc/hostapd/hostapd.conf autowlan
~~~

## Create and run container (stop with Ctrl+C)
~~~
docker-compose -f <yml file name> up
~~~
## Create and run container in the background
~~~
docker-compose -f <yml file name> up  -d
~~~
## Stop a container in the background
~~~
docker-compose -f <yml file name> down
~~~
#### Read logs of a container in the background
~~~
docker-compose -f <yml file name> logs
~~~

