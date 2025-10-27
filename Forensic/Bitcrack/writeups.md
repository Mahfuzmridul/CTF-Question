# 🤖Let's solve this problem.
## 🔎There was a 7z zip file which contains a *".dd"* file named *"bitcrack.dd"*. It mainly comes from bitlocker. You can read about bitlocker if you search in google or asking AI. Mainly *"bitcrack.dd"* is a password protected disk dump file. So, at first we have to crack the password by bruteforce password attack. If we are able to get the password we can mount it in windows easily. Description has a hint about password.
<img width="781" height="602" alt="image" src="https://github.com/user-attachments/assets/f70b8d4c-c855-4a39-8137-b36ca6eb7bdc" />

##

### 1️⃣First let's try to mount it in windows by *"OSFMount"* tool. It's a very useful tool to mount any disk dump file. You can download it from **[here](https://www.osforensics.com/tools/mount-disk-images.html)**

### 🏍️To mount with OSFMount go through the instruction.
<img width="1022" height="547" alt="image" src="https://github.com/user-attachments/assets/0384c545-dbda-4380-8f8d-69b3b1549088" /> <br><br>
<img width="608" height="542" alt="image" src="https://github.com/user-attachments/assets/2d7c217d-702e-4cce-a110-2658f7c354e7" /><br><br>
### 🏍️Go to *"This PC"* of you windows and you will see a new drive has been emerged.
<img width="1351" height="267" alt="image" src="https://github.com/user-attachments/assets/ead242c9-0e06-47a1-9651-96f69b3a32cf" /><br>
### 🕵️But without the password we cannot open the local disk we mounted.
## 🕷️So let's crack the password.
### 🔎To do that we can simply create a hash i am using *"bitlocker2john"* to create the hash.
```bash
 bitlocker2john -i bitcrack.dd > bitcrack.hash
```
### 🤖A file bitcrack.hash will be created with the hashes.
```bash
cat bitcrack.hash
```
<img width="1907" height="486" alt="image" src="https://github.com/user-attachments/assets/5257a940-d7a3-4581-8e33-b55e46ad3bbc" />

### 🔎Use this hash or you can use other one. Keep this hash only in bitcrack.hash and use password cracking tool *"john"* or *"hashcat"*.

<img width="1692" height="272" alt="image" src="https://github.com/user-attachments/assets/a6545ecb-7625-465b-9996-92a377e4e21b" />

