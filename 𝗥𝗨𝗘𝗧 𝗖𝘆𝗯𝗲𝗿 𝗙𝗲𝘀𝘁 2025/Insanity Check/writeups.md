# 🕵️This is a very basic challenge. Let's solve this quickly.
## 🤖If we go to the discord server we will see the section ```rules```, and in this section we will see there is written ```WHAT RULES?``` 

<img width="1465" height="796" alt="image" src="https://github.com/user-attachments/assets/2d455876-6c55-497c-987d-ff44a44ec3d3" />


### 🔎If we copy this text and paste it to an editor like ```sublime text```, we will see zero-width character is embedded. So let's get a python code and decode this.

# 🕷️Python Code: 
```python
# Paste your text between the triple quotes below
text = """
WHAT RULES​‌​‌​​‌​​‌​​​​‌‌​‌​‌​​‌‌​‌​​​​‌‌​‌‌‌‌​‌‌​‌‌​​​‌​​​‌‌​​‌‌​‌‌‌​​‌‌​‌‌‌​‌​​​‌​‌‌‌‌‌​​‌‌​​​​​‌‌​​‌‌​​‌​‌‌‌‌‌​‌‌​‌‌​​​‌‌‌​‌​‌​‌‌​​​‌‌​‌‌​‌​‌‌​‌​‌‌‌‌‌​‌‌‌​​​​​‌‌​‌‌​​​‌​​​​​​​‌‌‌‌​​‌​​‌‌​​‌‌​‌‌‌​​‌​​‌‌‌‌‌​‌?
"""
# Zero-width character → bit mapping
ZW_MAP = {
    "\u200b": "0",  # zero-width space
    "\u200c": "1",  # zero-width non-joiner
    "\u200d": "",  # separator / ignore
    "\ufeff": "",  # ignore
}
def extract_bits(s):
    return "".join(ZW_MAP.get(ch, "") for ch in s)
def bits_to_text(bits):
    output = []
    for i in range(0, len(bits), 8):
        byte = bits[i : i + 8]
        if len(byte) == 8:
            output.append(chr(int(byte, 2)))
    return "".join(output)
bits = extract_bits(text)
decoded = bits_to_text(bits)
print("\nDecoded text:")
print(decoded)

```
# 🧨Output:

<img width="591" height="161" alt="image" src="https://github.com/user-attachments/assets/f4cba95f-cc1e-4a21-8b84-32985ce733d0" />

## 🚩So the Flag:
```bash
RCSC{b3st_0f_luck_pl@y3r}
```
<br><br><br><br>
# ☢️Thank You☢️


