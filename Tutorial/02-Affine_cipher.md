# Affine Cipher
## Encoding:
Given any plain text we first access all its alphabets and map then with our text space!
Given any [plain text](00-preliminaries.md#plain-text) we first access all its alphabets and map then with our [text space!](00-preliminaries.md#text-space) Now we will follow this line of code according to the [Encoding Method](00-preliminaries.md#encoding-function)!\
```python
from Affinecipher.dict import *
from Harrycipher.coverstion import conv

def encrypt(message,key):
  en=[]
  key=list(key)
  message=message.upper()
  lis=list(message)
  for i in range(len(lis)):
    if get_key(lis[i]) is not None:
     en.append(dict[(int(key[0]) * get_key(lis[i]) + int(key[1])) % 41])
    else:
      print("Error occured")
  
  return conv(en).capitalize()
```
In the above code encrypt() function takes message and key as argument and makes a empty list named en=[ ]. Then taking input of key(type string) it makes it a list. This is two digit key so list formed will have only two digits. We may use directly key[0] and key[1] method after that. No need to make key a list even as stated [earlier](01-Storing_data.md#actually-strings-are-immutable-that-cant-be-overwrite-like) that key is not gonna change its form after calculation.\
Although there is another easier way as we are not directly changing our string, rather just making a new list and string it there and changing it back to string. What about we just stick to string through out as follows:\
#### Sticking to Strings:
```python
def encrypt(message,key):
    en=""
    message=message.upper()
    for i in range(len(message)):
        if get_key(message[i]) is not None:
            en=en+(dict[(int(key[0])*get_key(message[i])+int(key[1]))%41])
        else:
            print("Error occured")
    return en.capitalize()

```
I think this is more easy and compact. Here message.upper() makes all the characters of the message in upper case then python can access keys corresponding the characters. \
Then we use for loop to append in list or concatinate strings respectively in the above codes using mathematical operations that is defined in the [encoding](00-preliminaries.md#encoding-function) of affine cipher if the symbols in our srting is not out of our text space or dictionary and if out of dictionary we print "Error Occured.". Finally returning a string with capitalize() case.\
Here we use two imports one to import our conetns from [dict.py](01-Storing_data.md#wrap-up-all-together-to-make-a-file-named-dictpy-if-you-want) file, other is to make a file for writing the code to convert list back to a string:
```python
def conv(message):
  str=""
  for i in message:
    str=str+i
  return str
```
Here we put it in conversion.py file in Harrycipher folder. from there hence we import conv() function.

## Decoding:
see methods [here](00-preliminaries.md#decoding-function). According to it, we have to creat a inverse function to invert out key[0].
#### Inversion:
```python
def inverse(a):
  for i in range(1,41):
    if (a*i)%41==1:
      return i
  else:
    return 0
```
Then we can write our decoding function code as follow:
```python
from Affinecipher.inverse import inverse
from Affinecipher.dict import *

def decryption(message,key):
  message=message.upper()
  a=inverse(int((key[0])))
  str=""
  for i in message:             
    x=get_key(i)
    x=(a*x-a*int(key[1]))%41
    str=str+dict[x]
    
  return str.capitalize()
```
Same concept as in case of encoding. 

Finally we need to make a gcd fucntion to ensure inverse exists: Hence we make it as follows:

#### GCD of two variables:
```python
def gcd(a,b):
  if a==0:
    if b>0:
      return b
    else:
      return -b
  elif b==0:
    if a>0:
      return a
    else:
      return -a
  else:
    return gcd(b,a%b)
```


[previous page](./01-Storing_data.md)\
[next page](./03-Final_output.md)
