# how to config geth on ubuntu server

1 - 

  `` apt-get update``

  `` apt-get install zip unzip``

  `` apt-get install net-tools``

  `` apt-get install ncftp``


2 - copy `geth.service` into `/etc/systemd/system`  and run `systemctl systemd-reload` to load service

3 - confing firewall

  `` sudo ufw allow from {Specific IP for ssh to server}  proto tcp to any port 22 `` 

  `` sudo ufw allow from {Specific IP for rpc to server}  proto any to any port 8545 `` 

  `` sudo ufw allow from {Specific IP for WebSocket to server}  proto any to any port 8546 `` 

  `` sudo ufw allow 30311 ``

  `` sudo ufw enable `` 

  `` sudo ufw reload `` 

  `` sudo netstat -ntlp | grep LISTEN ``


4 - make following folders

  `` mkdir /data/eth `` 

  `` mkdir /data/backup`` 

5 - download latest geth from `https://geth.ethereum.org/downloads/` for linux

  `` unzip downloaded file `` 

  `` move geth file to /data/eth``

  `` chmod +x geth``


6 - copy `config.toml` into `/data/eth`


7 - create genesis.json

  `` cd /data/eth `` 

  ``./geth --datadir node init genesis.json``

 



