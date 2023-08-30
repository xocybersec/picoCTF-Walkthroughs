picoCTF
<br> GET aHEAD
<br><i>Find the flag being held on this server to get ahead of the competition</i>
<br><br><br>
Visiting the website that’s provided, there are two text boxes with a button in each box to press.
<br> My next step was to view the source code and see if there’s anything of interest.
<br> I notice that the methods of each button are different.
<br><br>
![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/71e82fca-6a7b-4375-9d8b-5e5045ef0913)

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/4e29b85d-05ee-47f2-8d4b-3f0c3bfe852a)

That gets my attention, so I fire up `burpsuite` to change the values and see what happens.
<br> With burp on and `foxy proxy` intercepting the requests, I send the request to the Repeater tab in burp.
<br> Via the Inspector part of burp I edit the header value to have ‘HEAD’ instead of ‘GET’ and the response shows the flag.

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/01e9ba59-171c-450b-9717-23637b76eb16)
