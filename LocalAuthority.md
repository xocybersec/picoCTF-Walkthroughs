picoCTF<br>
Local Authority
---

Description<br>
Can you get the flag?<br>
Go to [this](saturn.picoctf.net:50920) website and see what you can discover.<br>
saturn.picoctf.net:50920

---

The initial page is a login page, so I opened up the browser dev tools and tried the standard `admin:admin` on the page to see if I get access. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/234a25c1-f4e0-4746-9cf9-b57557b0863b)

Before submitting the credentials, the source code shows that I’d be redirected to a `login.php` page. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/bfe6b480-1190-4e9c-9ac0-c386017bce7f)

Unfortunately, the creds didn’t work but I did get some valuable information on the page I was brought to. <br>
Looks like there’s a script referenced and I’ll check that out in a minute. <br>
There’s also an `admin.php` page that I would be redirected to. I tried to go to that page but got an <i>Access Forbidden</i> message. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/3ff59449-5a0e-4082-85da-538e1d758f84)

After that I went to the `Sources` tab to look at the `secure.js` script and this is what I found. <br>
Looks like I had the username right, but could this really be the password needed? <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/863295af-98b2-470f-8f48-82cafb965129)

I also made note of this section that mentioned a hash in case I needed to dig further. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/c1356b95-3968-4248-af1f-0ef5476c5ccd)

After entering `admin:strongPassword098765` the login was successful and the page revealed the flag. <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/ad1ed702-5a25-4189-ae10-6b6e5350c401)
