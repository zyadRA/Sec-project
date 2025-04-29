# Introduction
## As we have successfuly exploited the victem machine by compromising ProFTPD (FTP) service in phase1
![image](https://github.com/user-attachments/assets/2e05644a-4c37-44b0-b07c-0664e4051ea0)
### We can start researching and proposing a defensive strategy to mitigate this attack
# Research
## Vulnerability Description
### ProFTPD 1.3.5 contains a remote code execution vulnerability via the mod_copy module which allows remote attackers to read and write to arbitrary files via the site cpfr and site cpto commands.
# Proposal
### After looking at possible solutions, we found that upgrading the version of proFTPD to 1.3.6rc1 or later prevents this exploit
# Execution
## On Metasploitable3
### We start by checking the current version of proftpd that has the vulnerability
![image](https://github.com/user-attachments/assets/5f8f79dc-ab62-4df0-b409-06143e633184)
### Backup the configuration
![image](https://github.com/user-attachments/assets/429205ef-5376-47a7-8706-2ff08ca628ac)
### Updated version of proftpd was transfered to Metasploitable3 from another vm
### install updated version https://github.com/proftpd/proftpd/archive/refs/tags/v1.3.8.tar.gz
### Old version is stopped and newer version was configured and started running
```
./configure --prefix=/opt/proftpd
make
sudo make install
sudo /opt/proftpd/sbin/proftpd
```
### Checking the new version
![image](https://github.com/user-attachments/assets/3e15a056-a7bf-4069-b8c3-3a8431b79394)
## On Kali
### After updating the service to a newer version(1.3.8), lets try the attack again
### Just before trying the attack, I ran a portscan and we can see that the ftp service is open, however the version has changed from 1.3.5
![image](https://github.com/user-attachments/assets/557b572f-ee63-467e-a0a9-74940bd1efd4)
### Running the attack
![image](https://github.com/user-attachments/assets/24bf195c-989b-4727-a41c-0a2818dc551f)
### This time we didn't get a shell meaning the exploit failed since the service was updated
# Reflection
### After updating the vulnerable service we found that our attack stopped working.
### Meaning that our defensive strategy has actually worked and is effective in preventing exploiting the mod_copy module.
