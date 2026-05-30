# picoCTF 2026 Writeup
## MultiCode Challenge
- Challenge Information
- Solution
### Challenge Information 
```
Level: Easy 
Category: General Skills 

Description: 
We intercepted a suspiciously encoded message, but it’s clearly hiding a flag. No encryption, just multiple layers of obfuscation.
Can you peel back the layers and reveal the truth?

Hints:
1. The flag has been wrapped in several layers of common encodings such as ROT13, URL encoding, Hex, and Base64.
   Can you figure out the order to peel them back?
2. A tool like CyberChef can be interesting.
```
Challenge Link: https://learn.cylabacademy.org/library/710?event=79&page=2
### Solution
Base64:
```
NjM3NjcwNjI1MDQ3NTMyNTM3NDI2MTcyNjY2NzcyNzE1ZjcyNjE3MDMwNzE3NjYxNzQ1ZjM4MzQzODZlMzQzNjM2NmYyNTM3NDQ=
```
Base64 -> Hex:
```
637670625047532537426172666772715f72617030717661745f3871713033727372253744
```
Hex -> URL:
```
cvpbPGS%7Barfgrq_rap0qvat_848n466o%7D
```
URL -> ROT13:
```
cvpbPGS{arfgrq_rap0qvat_848n466o}
```
ROT13 -> Flag:
```
picoCTF{nested_enc0ding_848a466b}
```
