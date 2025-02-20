
# 🕵️ Hidden in Plain Sight – Writeup  

## 🔍 Step 1: Extracting the Zip File  
The given file is **bugpwtl.zip**, but it requires a password to extract. And the extraction process should be in **7z-zip**. <br> <br>

![image](https://github.com/user-attachments/assets/de538038-7bc8-464d-ad3a-cccc6ccf2368) <br> <br>


The problem hints that the key is **"hidden in plain sight"** and derived from the **file name using a common cipher**.  

Since **Caesar cipher** is a commonly used simple shift cipher, we apply a **Caesar shift of 7 (backward)** to **"bugpwtl"**.
Which will give the password: **"unzipme"** . <br> <br>

![image](https://github.com/user-attachments/assets/77dea0fa-30fd-4970-b24e-2c80b92c996a) <br> <br>


This will extract a jpg image.

## 🔑 Step 2: Image metadata check

As in the question it is given that **the flag is somewhere encoded and the right methode will extract the flag** and also the jpg file name is **find_flag32** which will refer to the **base32** encryption. The encrypted text will be in metadata so for that use **exiftool**. You will get a text. Just decode it and get the flag!!!! <br> <br>

![image](https://github.com/user-attachments/assets/b0c9ecb2-863b-404e-8bca-3558aea1db90)  <br> <br>

  

![image](https://github.com/user-attachments/assets/69610fc8-49aa-4f6d-8070-1e98cbd618ac)
