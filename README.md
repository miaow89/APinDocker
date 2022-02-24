# remove Comment
> sudo vi /etc/sysctl.conf
net.ipv4.ip_forward=1
> sudo vi /etc/dhcpcd.conf
# add to the end of file
> denyinterfaces wlan0

# execute Command
> sudo curl -sSL https://get.docker.com | sh
> 
> sudo apt-get install libffi-dev libssl-dev -y
> 
> sudo apt-get install -y python python-pip
> 
> sudo pip install docker-compose
> 
> sudo docker build . --tag autowlan
> 
> sudo docker run --name autowlan_open --cap-add=NET_ADMIN --network=host  autowlan


