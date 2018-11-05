---
layout: post
title:  "Python - string check"
date:   2018-11-05
categories: [python]
tags: [2018, python, string, hangul, symbol]
---

파이썬을 이용하여 string의 특정 문자 있는지 확인
======================================

특정 symbol 확인
--------------------------------------
~~~
import re
def check_symbol(text):
    parse = re.sub('[-+=$.#?:@%^&*()]', '', text)
    if not len(text) == len(parse):
        return True
    return False
~~~
re.sub('[-+=$.#?:@%^&*()]', '', text) 에서 [] 안에 있는 symbol들 제거하고 return

한글이 있는지 확인
--------------------------------------
~~~
import re
def check_hangul(text):
    hangul = re.compile('[^ ㄱ-ㅣ가-힣]+') 
    result = hangul.sub('', text)
    if len(result) < 1:
        return False
    return True
~~~

string이 숫자가 맞는지 확인
--------------------------------------
~~~
string txt
txt.isdigit()
~~~