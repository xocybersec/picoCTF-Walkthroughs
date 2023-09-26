picoCTF <br>
unpackme.py
---
Description <br>
Can you get the flag?Reverse engineer this Python program.  <br>
https://artifacts.picoctf.net/c/49/unpackme.flag.py <br>

---
Let’s grab that file with `wget` to the webshell and open it up with `vim` to see what we’re working with. <br>
```
import base64
from cryptography.fernet import Fernet

payload = b'gAAAAABkzWGSzE6VQNTzvRXOXekQeW4CY6NiRkzeImo9LuYBHAYw_hagTJLJL0c-
kmNsjY33IUbU2IWlqxA3Fpp9S7RxNkiwMDZgLmRlI9-lGAEW-_i72RSDvylNR3QkpJW2JxubjLUC5VwoVgH62wxDuYu1rRD5KadwTADdABqsx2MkY6fKNTMCYY09Se6yjtRBftfTJUL-LKz2bwgXNd6O-
WpbfXEMvCv3gNQ7sW4pgUnb-gDVZvrLNrug_1YFaIe3yKr0Awo0HIN3XMdZYpSE1c9P4G0sMQ=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
exec(plain.decode())    
```
There’s a lot of base64 encoding going on mixed in with some Fernet cryptography. <br>
I didn’t know about Fernet, so I asked my friend Google and here is what Google told me about it. <br><br>
Fernet guarantees that a message encrypted using it cannot be manipulated or read without the key. <br>
Fernet is an implementation of symmetric (also known as “secret key”) authenticated cryptography. <br>

I couldn’t decode the payload at the beginning of the program in hopes of seeing what it was, unfortunately. <br>
I also didn’t have the Fernet key so I tried thinking of some way to reverse engineer the program. <br>
Then it hit me, since the last line was executing the program.. <br>
Encoding the key, applying Fernet to that to encrypt it and lastly decrypting it all. <br>
My idea was to have it print what was stored instead of executing it. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/9b14eff3-5874-4d86-93e7-0861899058e2)

After changing `exec` to `print` and running the program once more, that was the fix! <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/d6a90ced-0341-48d1-b643-88ba74fd40d8)


