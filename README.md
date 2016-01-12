# VTEX AWS ebextensions 

Collection of custom ebextensions.

## iis-log-removal.config
One-file configuration for elastic beanstalk windows environment that enable IIS log and clean old files.


### Tasks
* Enables IIS log
* Set log period to hourly
* Set log format to IIS
* Creates an scheduled task that deletes log files older than a specified date and time

### How to configure

Configure how long log files should live
```config
$logFilesTimeToLiveInHours = 1 
```

### Usage
Just put this file inside an folder named .ebextensions

### Customizations

This default version runs the task every 20 minutes, it can be changed in the container command named: 04_schedule_iis_removal-task.  

Other customizations are still possible, just modify as you want.

### Contributing
Conttibutions are always welcome.

## get_beanstalk_load_balancer.config
Gets the ELB in which the EC2 instance is attached to and the EC2 instance id

It will generate 2 files with those informations:

- `C:\tools\BeanstalkELBDNSName.dat` contains the Load Balancer DNS
- `C:\tools\EC2InstanceID.dat` contains the EC2 instance id

## install_chocolatey.config
Installs [Chocolatey](https://chocolatey.org/) package manager

## install_etcd.config
Installs [etcd](https://coreos.com/etcd/)

It defaults to **proxy mode**

### How to configure
The following are the default values. Modify them to customize the etcd proxy connection to your needs:
```
$discoverySRV = "vtexlab.com.br"
$clientURL = "http://127.0.0.1:4001"
```

Also, you can alter the whole `$params` variable to fully customize the etcd cluster
