# Task1.1 Using Metasploit to Compromise a Service 
## Scanning victem machine
```nmap -sV 192.168.56.101```

![image](https://github.com/user-attachments/assets/e92b3bfb-3e7d-4383-bcdc-caa4c5c4f23c)

### ProFTPD (FTP) service is chosen to be compromised on port 21
### Run metasploit and search for exploits on the service
![image](https://github.com/user-attachments/assets/a04d731d-96c9-4bee-9fe0-c7c35ff43d19)

## Set parameters and try to exploit the service
![image](https://github.com/user-attachments/assets/1e521d88-fc13-45a3-9209-cb6d7b860df7)

## Service is compromised and we are now on shell!
### Running some commands on the victem machine
![image](https://github.com/user-attachments/assets/7cbbe17d-d93b-4296-a6fe-239e6aeb2c20)

![image](https://github.com/user-attachments/assets/b10c49c1-c94b-43c3-acf1-6d00710de791)

# Task1.2 Compromising the Service Using a Custom Script
## Here is a simple script that will take the host and victem addresses and try to exploit the FTP service
## If successful, we should be on the shell
![image](https://github.com/user-attachments/assets/e5eac59b-1e23-434f-bd9c-449d945a0330)

## Running the script
![image](https://github.com/user-attachments/assets/d393cb09-27f9-4498-a88d-4daeb143ce35)

## And we are on the shell!
