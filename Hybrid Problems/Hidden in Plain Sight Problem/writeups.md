
# 🕵️ Hidden in Plain Sight – Writeup  

## 🔍 Step 1: Extracting the Zip File  
The given file is **bugpwtl.zip**, but it requires a password to extract. And the extraction process should be in **7z-zip**.

![image](https://github.com/user-attachments/assets/de538038-7bc8-464d-ad3a-cccc6ccf2368)


The problem hints that the key is **"hidden in plain sight"** and derived from the **file name using a common cipher**.  

Since **Caesar cipher** is a commonly used simple shift cipher, we apply a **Caesar shift of 7 (backward)** to **"bugpwtl"**.
Which will give the password: **"unzipme"** .

![image](https://github.com/user-attachments/assets/77dea0fa-30fd-4970-b24e-2c80b92c996a)


This will extract a jpg image.

## 🔑 Step 2: Image metadata check

