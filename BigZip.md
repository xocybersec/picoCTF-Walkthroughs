picoCTF <br>
Big Zip
---

Description <br>
Unzip this archive and find the flag.

---

Let’s grab the zip file with `wget` and then unzip it.<br>
```
Unzip big-zip-files.zip
```
There are a lot of files that show up so I resort to using `grep` to find what I’m looking for much faster than I could manually.<br>
```
grep -R “picoCTF” big-zip-files
```
The `-R` option helps search for a word in all files within a directory and its subdirectories. <br>
The search term I used, `picoCTF`, is the format that the majority of flags are in on picoCTF. <br><br>
Just look at how many subdirectories that flag was buried in! <br>

![image](https://github.com/xocybersec/picoCTF-Walkthroughs/assets/91302698/0844d6e5-6eb9-4d2d-8270-174ef10fa911)

