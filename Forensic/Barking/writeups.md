# 🤖Let's solve the problem step by step. 
## 🎗️It's a very basic forensic challenge. When solving CTF challenges we must focus on the problem name and it's description. 
### 🎪Let's read the problem's description carefully. Here, in the description it is said that it's a "strange" file and talking about file's *"head"*. And there the word *"fix"* refers that the header of the file has to be fixed. If we do this, it's not finished there, we have to do something more to get the flag. <br>
##
<img width="898" height="422" alt="image" src="https://github.com/user-attachments/assets/d661c983-cb12-417a-97f6-651ab66f1a06" /> <br>
##
<img width="717" height="537" alt="image" src="https://github.com/user-attachments/assets/23194140-5d3c-4e97-b413-fc2a82bd3384" /> <br>
### 🥲No clue so far in metadata. As in a the description said something about header lets check the header of the file with *"hexedit"*. You can use other tools to check the header like *"Hxd"* in windos or *"I'm Hex"* etc...
##
## 🎗️Use hexedit to see the header
```bash
hexedit barking
```
<br> 
<img width="1853" height="387" alt="image" src="https://github.com/user-attachments/assets/216135a2-fd1c-48b5-aae3-6354e1db2df1" /><br>

### 🧨Here the header is showing GPN it was *"PNG"* and also the *"IHDR"* has changed to RHDI. That refers that its a png image and it's corrupted. If we see the PNG image header file structure it is like <br>
<img width="727" height="242" alt="image" src="https://github.com/user-attachments/assets/24afa6c8-9074-402a-a650-86d79041b9a8" /> <br>

### 🏍️Look closly and you will see that every four bit chunk *"first"* and *"fouth"* bit swaped with each other.

<img width="727" height="242" alt="image" src="https://github.com/user-attachments/assets/fbe95293-eb79-4406-a260-953d51ac75f4" />
<br> 

##

## 📑Now swap the bits to fix it. We can use *"python"* script to swap the bits.

```python
import sys

def swap_first_and_fourth_bytes(input_path, output_path):
    """
    Reads a file and swaps every 1st and 4th byte.
    """
    try:
        with open(input_path, 'rb') as f_in:
            content = f_in.read()
    except FileNotFoundError:
        print(f"Error: Input file not found at '{input_path}'")
        return

    modified_content = bytearray()
    
    # Process the file in chunks of 4 bytes
    for i in range(0, len(content), 4):
        chunk = bytearray(content[i:i+4])
        
        # If the chunk is a full 4 bytes, swap the 1st and 4th bytes
        if len(chunk) == 4:
            chunk[0], chunk[3] = chunk[3], chunk[0]
        
        modified_content.extend(chunk)

    with open(output_path, 'wb') as f_out:
        f_out.write(modified_content)
        
    print(f"Byte swapping complete. New file saved as '{output_path}'")

if __name__ == "__main__":
    if len(sys.argv) != 3:
        print("Usage: python swap_bytes.py <input_file> <output_file>")
        sys.exit(1)
        
    input_file = sys.argv[1]
    output_file = sys.argv[2]
    
    swap_first_and_fourth_bytes(input_file, output_file)
```
## 🏍️Save this scripts and run.

```bash
python3 swap_bytes.py barking barking.png
```
## 😊Now you will be able to see the image. This will be like this.

<img width="1428" height="617" alt="image" src="https://github.com/user-attachments/assets/8e81324b-a4db-44ce-b78a-c5a3ed233de4" />

##

### 🥲But We haven't get the flag yet. Flag format was *"RCSC{....}"*. In the description it was said that we have to do something more to get the flag. So as a png image we can see the lsb metadata of it by *"zsteg"* tool. So let's use it.
```bash
zsteg barking.png
```
<img width="640" height="102" alt="image" src="https://github.com/user-attachments/assets/c94996fd-b64c-4bfc-adc6-8193e0b7a3fe" /> <br>

## ☺️So that's how we will get the flag.

# 🚩Flag:
```bash
RCSC{b@s1c_1m@g3_f0r3ns1cs}
```
<br><br><br><br>

# ☢️Thank you☢️



