# picoCTF 2026 Writeup
## ABSOLUTE NANO Challenge
- Challenge Information
- Solution
### Challenge Information 
```
Level: Medium 
Category: General Skills 

Description: 
You have complete power with nano.
Think you can get the flag?

Hints:
1. What can you do with nano?
```
Challenge Link: https://learn.cylabacademy.org/library/748?event=79&page=3
### Solution
1. First I ran the instance and logged in via "ssh -p 55264 ctf-player@crystal-peak.picoctf.net" on terminal and a password was provided for login "c4feea17"
2. The first command I ran was "ls" to see what files was inside the system, and the only file there was flag.txt
3. When I tried running cat flag.txt it said Permission Denied
4. So I checked what commands I could run by running "sudo -l" 
```
Matching Defaults entries for ctf-player on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User ctf-player may run the following commands on challenge:
    (ALL) NOPASSWD: /bin/nano /etc/sudoers
```
5. The key thing to look out for here is the bottom area where it says /bin/nano /etc/sudoers
6. After accessing that file at the bottom there was a line printing this 
```
ctf-player ALL=(ALL) NO-PASSWD: /bin/nano /etc/sudoers
```
7. I made use of this line and edit it to get permission to access the flag.txt file instead by replacing /etc/sudoers with flag.txt
8. After that I accessed the flag.txt by running this "sudo /bin/nano flag.txt"
9. Which presented the flag "picoCTF{n4n0_411_7h3_w4y_7fcf8f8d}"
