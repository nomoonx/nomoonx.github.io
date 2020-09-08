---
layout: post
title: "Jarvis OJ 德军的密码"
tags: ctf write-up jarvis-oj crypto
---

瞎猜

题面是给了一个84位的二进制字符串，然后告诉了答案是12位的大写字母，密钥也是12位大写字母。

这种只能瞎猜咯。
7位二进制正好是ASCII的范围内，所以猜是不是二进制运算。

&,&#124;,^试下来，异或能过。

```
encryptedMsg = "000000000000000000000000000000000000000000000000000101110000110001000000101000000001"
encryptKey = 'WELCOMETOCFF'

result = ''
for i in range(len(encryptKey)):
    encryptedChar = encryptedMsg[7*i:7*i+7]
    encryptedASCII = int(encryptedChar,2)
    decryptedChar = chr(encryptedASCII ^ ord(encryptKey[i]))
    result+=decryptedChar
print(result)
```