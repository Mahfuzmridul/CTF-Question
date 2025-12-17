# 🤖Let's solve this problem step by step.
## 🔎Always read the *`description`* and *`problem name`* before working on given files. Most of the problems hints and next steps are given in the description.

<img width="825" height="705" alt="image" src="https://github.com/user-attachments/assets/a3687c7b-549b-41f9-88df-ed09ef16ae5b" /> <br><br>

### 🕷️As a networking challenge a `.pcapng` file named `annoying.pcapng` has given. Open this file on wiresherk to analyze the protocols. In the description there mentioned about a `convo`, So atfirst let's check `TCP` portocol. In wireshark follow TCP stream.

## 

<img width="906" height="395" alt="image" src="https://github.com/user-attachments/assets/ca926247-3d31-4044-b84e-9c87354ca863" /> <br><br>

##

<img width="1306" height="739" alt="image" src="https://github.com/user-attachments/assets/21a0b85f-11e9-4020-abfb-b3878f643ec9" />

### 🧨Let's check those TCP Stream one by one:

<img width="1283" height="725" alt="image" src="https://github.com/user-attachments/assets/d319117c-624d-490c-8ac9-634feed61fa9" />

##

<img width="1264" height="688" alt="image" src="https://github.com/user-attachments/assets/8b919c0b-88fa-40fb-8dfc-a8aa32356dbd" />

##

<img width="1277" height="707" alt="image" src="https://github.com/user-attachments/assets/cf5c4074-f480-47d8-9d8f-e4724d2fece6" />

##

<img width="1272" height="640" alt="image" src="https://github.com/user-attachments/assets/2da8438a-ea9a-4825-a32d-e87495c84ecd" />

## 🕷️Here it is saying that something has been sent. So let's check the previous stream.

<img width="1270" height="630" alt="image" src="https://github.com/user-attachments/assets/ff20ca6a-7302-44fc-97b3-8c3e2c861c03" />

## 🔎Here look at the first header. It's the header of a `wav` file. As the question is all about noisy something, let's download this wav file.

<img width="1293" height="713" alt="image" src="https://github.com/user-attachments/assets/4dd06d35-c47b-44bb-924e-010b5b231cf6" />

## 🤖When in the tpc stream this type of situation comes we can download it easily. Let's see the steps.

<img width="1276" height="654" alt="image" src="https://github.com/user-attachments/assets/3987259a-31f4-49d1-b6ee-f5cfae1c5a70" />

## 🧨Make it raw give an extension of `.wav` and save.

<img width="1285" height="715" alt="image" src="https://github.com/user-attachments/assets/b3e8b3ef-37ac-43fc-a415-03f29fcc7a99" />

## 

<img width="1337" height="733" alt="image" src="https://github.com/user-attachments/assets/f0a40e91-0449-4642-9259-ad5b9a47c287" />

## 🔎Listen to it and it's a `QSSTV` wav file. Now to decrypt the qsstv wav file you can go to my another writeup. I am giving its link below.

<img width="955" height="242" alt="image" src="https://github.com/user-attachments/assets/b5a3660c-e374-49e9-908d-8df963c1a64f" />

# 🕵️How to decode SSTV with QSSTV ([Link](https://github.com/Mahfuzmridul/CTF-Question/blob/main/Steganography/Suspicious%20Image/writeups.md)) (Another Writeups)

## 🚩Decode the audio and you will get an image. The flag image will be like this: 

<img width="1672" height="642" alt="flag" src="https://github.com/user-attachments/assets/e9496c2d-5c78-46d5-83da-e324b3ba3c80" />

# 🚩Final flag:
```
RCSC{unable_to_hide_failed_to_encrypt}
```
<br><br><br><br>
# ☢️Thank You☢️
