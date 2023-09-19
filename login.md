picoCTF <br>
login <br>
---  

Description <br>
My dog-sitter's brother made this website but I can't get in; can you help? <br>
login.mars.picoctf.net

---  

We start off at a login page that doesn’t show much else. Let’s try the easy `admin:admin` combo.. and we get an 'invalid password' alert. <br>
Does that mean the username is correct? I tried `user:user` as the input and got an 'invalid username' alert. <br>
That means 'admin' must be a valid username. My next step is to check the source code. <br>
Within the head tag there’s an imported script source called `index.js` so I click on the `Sources` tab in my browser’s dev toolbar to see what’s in that script. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/92df6e8a-80d8-4e99-99e7-d0ff94059c8e)

<br>

When trying to dissect the script, near the line with the `return` information I see something that catches my eye.. `btoa` which tells me that something is base64 encoded. <br>
I then decoded the input that looks like what I was looking for. <br><br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/2d226503-fdba-4185-8aa7-47e6a5d4729a)

<br>
"YWRtaW4" decoded is “admin” and “cGljb0NURns1M3J2M3JfNTNydjNyXzUzcnYzcl81M3J2M3JfNTNydjNyfQ” decoded was the flag.  <br><br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/79d078d1-c4e3-4494-ada2-28b814e097b1)
