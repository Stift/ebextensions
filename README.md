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

## install_chocolatey.config
Installs [Chocolatey](https://chocolatey.org/) package manager
