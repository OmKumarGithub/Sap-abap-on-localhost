# How to get SAP logon username and password?

Well the answer is you can develop your own server which could be running sap. To do so follow the steps 


## Minimum Requirement 
- 8 CPUs 
- 32GB RAM
- 150GB Disk

First We are going to install some vm virtual machines (recommended: VM Workstation Pro or Oracle VMBox)

Then we are going to install Linux (any) on it (recommended: NetNist Debian or Alpine for minimal space).

The Linux which you are going to install should be of x86 architecture Because SAP runs on x86 architecture if you are going to install any other architecture Linux then you should download QEMU on that Linux, which you just downloaded. On that you can run QEMU, the thing is QEMU basically do bit translations. So there will be an extra layer which will be doing bit translation on the system which is heavily loaded when running SAP we want to avoid that because of that we would install at X86 Architecture Linux

After installing Linux Open SSH From host system

Then install Docker And run this command

```docker pull sapse/abap-cloud-developer-trial```


After downloading the image you have to build the image then run this command



```docker run --stop-timeout 3600 -i --name a4h -h vhcala4hci -p 3200:3200 -p 3300:3300 -p 8443:8443 -p 30213:30213 -p 50000:50000 -p 50001:50001 sapse/abap-cloud-developer-trial -skip-limits-check```


After this open SAP logon on your host system and create a connection with
- username: DEVELOPER
- password: ABAPtr2022#00



## Refrences
- https://hub.docker.com/r/sapse/abap-cloud-developer-trial
- https://www.youtube.com/watch?v=xXldsgqnBm4&t=987s&ab_channel=SAPBasisWizard
- https://www.youtube.com/watch?v=rhFLfwZzlGA&ab_channel=AverageLinuxUser
