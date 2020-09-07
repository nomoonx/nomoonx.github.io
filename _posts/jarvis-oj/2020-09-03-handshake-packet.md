---
layout: post
title: "Jarvis OJ 握手包"
tags: ctf write-up jarvis-oj
---

把包下下来，然后用aircrack-ng解一下。没有用特别的dictionary，只用了kali自带的。
```
aircrack-ng -w /usr/share/dict/wordlist-probable.txt wifi.cap.d4e4d22bc8fe925bf0ccb9382056ce8e 
```

Result:
![result](/assets/jarvis-oj/handshake.png)

把得到的密码填进去就好。