# Url Shortener

Link shortening service will convert long url in shortcode and redirect to actual url using short code url.

## Installation


#Prerequisite:-
Linux Ubuntu 16.04
Docker version 18.09.7
docker-compose version 1.24.1,
java "1.8.0_222"
maven 
ELK
 
## Step

##############Start ELK on Docker##############
Download the project from git , browse to folder /ELK_final_delivery.
**************Run the command**************

sysctl -w vm.max_map_count=262144 (NOTE*************)
docker-compose -f docker-compose-ELK.yml up -d

##############Start FileBeat on Host Machine(LINUX)##############
Install filebeat 

**************Run the command to install FileBeat**************
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.3.2-amd64.deb
sudo dpkg -i filebeat-7.3.2-amd64.deb
apt-get install apt-transport-https
apt update
apt install filebeat

**************Copy FileBeat configurations**************
Browse to /FileBeat_Linux_Delivery folder
Copy filebeat.yml to /etc/filebeat 

**************Start FileBeat Service**************
filebeat -e -c /etc/filebeat/filebeat.yml

##############Create Index in Kibana##############
Open link http://hostmachineip:5601 in a browser.
Click on Index Patterns
Click on Create index
Define Index Pattern as filebeat*
In the next page, click on @timestamp

## License
[Rsystem](https://www.rsystems.com/)
