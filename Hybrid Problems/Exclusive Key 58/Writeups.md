## 🔖 To solve this problem let's break the problem name and description and approach step by step: <br> <br>
![image](https://github.com/user-attachments/assets/db3722e8-f222-4f8f-9cdc-7e139b99b159) <br> <br>

## 🔎 We have to find a string within the .png image:
We can use **zsteg** to find it or we can use online tool to see meta data( [**aperisolve**](https://www.aperisolve.com/) can be used ).  <br> <br>
![image](https://github.com/user-attachments/assets/476dea66-8747-4518-b3b2-239e7990d4aa) <br> <br>
Now we have the strings and a key. **Regarding the description** fist we have to decode it and we will get unfamilier strings.
But after we XOR it with the key the flag will reveal:<br> <br>
![image](https://github.com/user-attachments/assets/0a26ef4a-3665-4f18-bd21-94a9d646ff2c) <br> <br>
![image](https://github.com/user-attachments/assets/62758c44-9eec-429f-ad56-d93251490c70) <br> <br> <br> <br>

### 🥱 Or we can use Pyhton code to extract the flag:
```python
import base58

extracted_data = "2WHPsDQoxfMPTacD7hULnmkbK3RMVcVuVTrebVZh"
decoded_text = base58.b58decode(extracted_data).decode()

def xor_decrypt(text, key):
    return "".join(chr(ord(c) ^ ord(key[i % len(key)])) for i, c in enumerate(text))

decrypted_flag = xor_decrypt(decoded_text, "secret_key")
print(decrypted_flag)  # Should reveal "RCSC{deeply_embedded_secrets}"
```
<br> <br> <br> <br>
# ☢️Thank you☢️
