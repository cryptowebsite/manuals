# The basic `firewalld` settings

## Remove `dhcpv6-client` service
```shell
sudo firewall-cmd --permanent --remove-service=dhcpv6-client
sudo firewall-cmd --reload
```

## Remove default `22` port from `ssh` service
```shell
sudo firewall-cmd --permanent --service=ssh --remove-port=22/tcp
sudo firewall-cmd --reload
```

## Add port to ssh service
```shell
sudo firewall-cmd --permanent --service=ssh --add-port=<NEW_SSH_PORT>/tcp
sudo firewall-cmd --reload
```

## Drop rest ingress traffic
```shell
sudo firewall-cmd --permanent --set-target=DROP
sudo firewall-cmd --reload
```

## Set default ethernet interface into public zone
```shell
sudo firewall-cmd --permanent --zone=public --change-interface=<ETH_INTERFACE>
sudo firewall-cmd --reload
```

## Get the list of services
```shell
sudo firewall-cmd --get-services
```

## Create custom service
```shell
sudo firewall-cmd --new-service=<NEW_SERVICE_NAME>
```

## Add service
```shell
sudo firewall-cmd --permanent --add-service=<NEW_SERVICE_NAME>
sudo firewall-cmd --reload
```

## Get list of ports in the service
```shell
sudo firewall-cmd --permanent --get-ports --service=ssh
```
