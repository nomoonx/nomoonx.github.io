---
layout: post
title: "Jarvis OJ A Piece Of Cake"
tags: ctf write-up jarvis-oj crypto
---

暴力猜一下先

里面有看到一个单独的`x`，先当作a来处理

然后句首的`nit`,假装是`the`

文中有个32位的单词估测就是flag。所以可以猜它前面的两个单词是`flag is`。

然后不停更新对照表慢慢猜其他的字母。

中间用到了一个[猜词网站](https://wordfinder.yourdictionary.com/letter-words/3-ends-an/)

```
encryptedString = 'nit yqmg mqrqn bxw mtjtm nq rqni fiklvbxu mqrqnl xwg dvmnzxu lqjnyxmt xatwnl, rzn nit uxnntm xmt zlzxuuk mtjtmmtg nq xl rqnl. nitmt vl wq bqwltwlzl qw yivbi exbivwtl pzxuvjk xl mqrqnl rzn nitmt vl atwtmxu xamttetwn xeqwa tsftmnl, xwg nit fzruvb, nixn mqrqnl ntwg nq gq lqet qm xuu qj nit jquuqyvwa: xbbtfn tutbnmqwvb fmqamxeevwa, fmqbtll gxnx qm fiklvbxu ftmbtfnvqwl tutbnmqwvbxuuk, qftmxnt xznqwqeqzluk nq lqet gtamtt, eqdt xmqzwg, qftmxnt fiklvbxu fxmnl qj vnltuj qm fiklvbxu fmqbtlltl, ltwlt xwg exwvfzuxnt nitvm twdvmqwetwn, xwg tsivrvn vwntuuvatwn rtixdvqm - tlftbvxuuk rtixdvqm yivbi evevbl izexwl qm qnitm xwvexul. juxa vl lzrlnvnzntfxllvldtmktxlkkqzaqnvn. buqltuk mtuxntg nq nit bqwbtfn qj x mqrqn vl nit jvtug qj lkwnitnvb rvquqak, yivbi lnzgvtl twnvnvtl yiqlt wxnzmt vl eqmt bqefxmxrut nq rtvwal nixw nq exbivwtl.'

checkMap={
    'a':'g',
    'b':'c',

    'd':'v',
    'e':'m',
    'f':'p',
    'g':'d',

    'i':'h',
    'j':'f',
    'k':'y',
    'l':'s',
    'm':'r',
    'n':'t',

    'p':'q',
    'q':'o',
    'r':'b',
    's':'x',
    't':'e',
    'u':'l',
    'v':'i',
    'w':'n',
    'x':'a',
    'y':'w',
    'z':'u',
}

result = ''
c={}
step=ord('x')-ord('o')
for i in range(len(encryptedString)):
    a=encryptedString[i]
    if a in checkMap:
        result+=checkMap[a]
    else:
        result+=a
print(result)
```