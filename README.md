# nwrfcsdk
Install SAP NW RFC SDK on Ubuntu 20.04.1 LTS

## Move nwrfcsdk directory
```bash
sap@master:~$ sudo apt-get install unzip
sap@master:~$ unzip nwrfc750P_7-70002752.zip -d out
sap@master:~$ sudo mkdir -p /usr/local/sap
sap@master:~$ sudo mv out/nwrfcsdk /usr/local/sap/
```

## Set SAPNWRFC_HOME
### bash
```bash
sap@master:~$ vim ~/.bashrc
```
```bash
export SAPNWRFC_HOME=/usr/local/sap/nwrfcsdk
```
```bash
sap@master:~$ source ~/.bashrc
```
### zsh
```bash
sap@master:~$ vim ~/.zshrc
```
```bash
export SAPNWRFC_HOME="/usr/local/sap/nwrfcsdk"
```
```bash
sap@master:~$ source ~/.bashrc
```

## Include lib directory
```bash
sap@master:~$ sudo su
root@master:~$ sudo su
root@master:~$ vim /etc/ld.so.conf.d/nwrfcsdk.conf
```
nwrfcsdk.conf content
```bash
/usr/local/sap/nwrfcsdk/lib
```

## Update linker cache and create the necessary links
```bash
root@master:~$ sudo ldconfig
```
