picoCTF <br>
crackme-py <br>

---

I started off using `wget` in the webshell to download the script then used `vim` to inspect it. <br><br>
Right at the top there’s an interesting line with a “secret” that is mentioned to be encrypted. <br><br>
A few more lines down there’s a note that says what to use to decrypt it. Hopefully it works! <br>
<br>
![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/db30d87e-bd1b-40f1-8f03-1860cc84ce22)

Once I found that I went to `CyberChef` and decrypted the secret with Rot47 as suggested and then got the flag. <br>
<br>
![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/b99f3d2f-ea89-4977-be3c-fc8218ffb38c)
