picoCTF<br>
patchme.py
---

Description<br>
Can you get the flag?<br>
Run this Python program in the same directory as this encrypted flag.<br>

---

Started off grabbing the files to the webshell with `wget` then checked out the python script with `nano`. <br>
Inspecting the code, the first thing that caught my eye was the IF statement mentioning the user password. <br>
It’s saying that if the password entered is equal to what is in the code then the flag will be printed. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/a7aa85f8-932d-4dd2-89e3-4b5210fa536d)

This is what we get after combining the lines. <br>
```
ak98-=90adfjhgj321sleuth9000
```
I ran the script and entered the password at the prompt and the flag was printed out. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/6364d996-da16-45dc-90b2-2f8f2ad597de)

