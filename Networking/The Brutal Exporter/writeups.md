# 🤖Let's solve this problem step by step.
## 🔎As it is a network category problem, we are given with a *"easy_peasy.pcap"* file. Normally when we deal with some *".pcap"* we use *"wireshark"* tool as gui tool and *"tshark"* as well for command line. First, let's read the description and try to find some hint.
<img width="944" height="649" alt="image" src="https://github.com/user-attachments/assets/ee985533-1756-458a-a71d-a6a048de58c0" /> <br>
### 📑After reading the description we can assume that there is something we have to export and aslo the word *"suspicious"* we could found somewhere. And the *"brutal"* word was used for *"brute-force"*.

## 🏍️Let's open the pcap file in wireshark.
<img width="1893" height="926" alt="image" src="https://github.com/user-attachments/assets/eb3781bd-9712-4f8f-9f54-1b3ad5806906" /> <br>
### 🕷️After opening the pcap file in wireshark i found a file *"suspicious.7z"*. It's a 7z zip file. Now we have to export it. We can export it in various apporach. It was passed as http object we can export it from wireshark export object. Let's export the file.
<img width="1235" height="750" alt="image" src="https://github.com/user-attachments/assets/1d734185-a1a7-4924-a1ab-20ccbdad8036" /> 
<br> <br> <br> <br>
<img width="1295" height="785" alt="image" src="https://github.com/user-attachments/assets/fc0ae667-729b-4bd3-adbc-0696487cd85b" /> <br> <br>

## 🎃Another method to export the file is to use *"binwalk"* or *"foremost"*. Just let me show a little bit.
<img width="1093" height="537" alt="image" src="https://github.com/user-attachments/assets/509f0ac1-64bd-41d6-8a4e-5cd031b40ee9" /> <br>

### 🕵️You can use these commands to export all the embedded files.
```bash
#binwalk
binwalk -e easy_peasy.pcap

or,
#foremost
foremost easy_peasy.pcap
```
## ▶️Now as we get the zip file. Let's try to open it.
<img width="807" height="487" alt="image" src="https://github.com/user-attachments/assets/255f051c-4c42-4841-9297-9bfdc4b22a14" /> <br>

### 🕷️So it is password protected. As the description mentioned about *"brute-force"* so we have to crack the password. So, let's crack it.
## 🧨At first let's get the hash of this zip file with the tool *"7z2john"*.
```bash
7z2john suspicious.7z > hash.txt
```
### 😞Clean the hash if filename appears at first. Then use hashcat. <br> <br>
<img width="1898" height="492" alt="image" src="https://github.com/user-attachments/assets/cf8f6059-dae7-4994-9a35-878eba3bcc5d" />

## 📑Run hashcat:
```bash
hashcat -m 11600 -a 0 hash.txt /usr/share/wordlists/rockyou.txt
```
<img width="1896" height="126" alt="image" src="https://github.com/user-attachments/assets/fb94424e-4f2d-41f2-807a-c8336f27fdb0" />

### 🕷️So the password is: ***"crabwalk"***

## 🎃Let's unzip the zip file with the password.
```bash
7z x -pcrabwalk suspicious.7z
```
<img width="726" height="548" alt="image" src="https://github.com/user-attachments/assets/3d4f4d5f-7175-48cd-8ae0-1444cf1067ee" /> <br><br>
## 📑Here the unzippning data said that 3 files extracted but in the terminal you will see only two file.
<img width="547" height="102" alt="image" src="https://github.com/user-attachments/assets/27305577-9322-417c-baba-09ea24d45f23" /> <br><br>

## 🕷️But if you see the hidden files too there will be a hidden flag.
<img width="749" height="407" alt="image" src="https://github.com/user-attachments/assets/73592e43-3574-4cbb-87cb-04ed03e59e25" /> <br>

## 🧨That's how we will get the flag.
# 🚩Flag:
````bash
RCSC{0pen_exp0rt_unZ1p_br3ak_g3t_fl4g}
````
<br><br><br><br>

# ☢️Thank You☢️




















