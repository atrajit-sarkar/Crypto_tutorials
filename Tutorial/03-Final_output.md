# Final Output file
Now we will finally output our work in a affine_en.py file to take message input and key from user and encode and print it in the console:
```python
from Affinecipher.encrypt import encrypt
from Affinecipher.gcd import gcd

alp="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
num="0123456789"
special=" ,.?!"

print("Only use characters in the following list: ","\n", list(alp),'\n', list(num),'\n', list(special),'\n',"forget about case sensitiveness")

message=input("Enter the encrypted message: ")
message=message.upper()

for i in message:
  if i not in alp and i not in num and i not in special:
    raise TypeError(f"Invalid character {i} in the message")
key=input("Enter your key(two digit number, remeber 10th digit must be coprime with 41): ")

if gcd(int(key[0]),40)!=1:
  raise TypeError(f"{key[0]} is not coprime with 40")

print(f"Your encrypted message is \n {encrypt(message,key)}")
```
And below is the decoding file to take cipher text input and key from user and return plain text back.

```python
from Affinecipher.decrypt import decryption
from Affinecipher.gcd import gcd

alp="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
num="0123456789"
special=" ,.?!"

print("Only use characters in the following list: ","\n", list(alp),'\n', list(num),'\n', list(special),'\n',"forget about case sensitiveness")

message=input("Enter the encrypted message: ")
message=message.upper()

for i in message:
  if i not in alp and i not in num and i not in special:
    raise TypeError(f"Invalid character {i} in the message")
key=input("Enter your key(two digit number, remeber 10th digit must be coprime with 41): ")

if gcd(int(key[0]),40)!=1:
  raise TypeError(f"{key[0]} is not coprime with 40")

print(f"Your decrypted message is \n {decryption(message,key)}")
```
[previous page](./02-Affine_cipher.md)