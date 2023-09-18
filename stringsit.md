picoCTF <br>
strings it<br>
---

Description <br>
Can you find the flag in `file` without running it? <br>
https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings

---

I used their webshell for this one and first started off with downloading the file with `wget`. <br><br>
After that I wanted to see if I could just `grep` the flag by using their standard “picoCTF“ format but that didn’t return any results.. <br><br>
Next, I took a peek at the code with `vim` to see if maybe just the flag was encoded or what was going on. <br><br>
After seeing it wasn’t in plain text I decided to use the command `strings` to help and then pipe that to `grep`. <br><br>

```
strings strings | grep “picoCTF”
```
That returned the flag!<br><br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/bab98670-c514-4257-ac02-6aa65ad035fe)
