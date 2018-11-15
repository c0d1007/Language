#Python进制转换（二进制、十进制和十六进制）实例
```
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# 2/10/16 base trans. wrote by srcdog on 20th, April, 2009
# ld elements in base 2, 10, 16.

import os,sys

# global definition
# base = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F]
base = [str(x) for x in range(10)] + [ chr(x) for x in range(ord('A'),ord('A')+6)]

# bin2dec
# 二进制 to 十进制: int(str,n=10) 
def bin2dec(string_num):
 return str(int(string_num, 2))

# hex2dec
# 十六进制 to 十进制
def hex2dec(string_num):
 return str(int(string_num.upper(), 16))

# dec2bin
# 十进制 to 二进制: bin() 
def dec2bin(string_num):
 num = int(string_num)
 mid = []
 while True:
 if num == 0: break
 num,rem = divmod(num, 2)
 mid.append(base[rem])

 return ''.join([str(x) for x in mid[::-1]])

# dec2hex
# 十进制 to 八进制: oct() 
# 十进制 to 十六进制: hex() 
def dec2hex(string_num):
 num = int(string_num)
 mid = []
 while True:
 if num == 0: break
 num,rem = divmod(num, 16)
 mid.append(base[rem])

 return ''.join([str(x) for x in mid[::-1]])

# hex2tobin
# 十六进制 to 二进制: bin(int(str,16)) 
def hex2bin(string_num):
 return dec2bin(hex2dec(string_num.upper()))

# bin2hex
# 二进制 to 十六进制: hex(int(str,2)) 
def bin2hex(string_num):
 return dec2hex(bin2dec(string_num))
以下代码用于实现十进制转二进制、八进制、十六进制：

# -*- coding: UTF-8 -*-

# Filename : test.py
# author by : www.jb51.net

# 获取用户输入十进制数
dec = int(input("输入数字："))

print("十进制数为：", dec)
print("转换为二进制为：", bin(dec))
print("转换为八进制为：", oct(dec))
print("转换为十六进制为：", hex(dec))
```

#try输出完整调试信息
```
#!/usr/bin/python
import sys
import traceback
import test1 
 
a=10
b=0
 
try:
    print test1.division(a,b)
except:
    print 'invoking division failed.'
    traceback.print_exc()
    sys.exit(1)
```
**样例输出：**
```
$python test2.py
execution python-2.5.1/python (enodeb/linux)
b eq 0
invoking division failed.
Traceback (most recent call last):
  File "test2.py", line 10, in <module>
    test1.division(a,b)
  File "/home/fesu/test1.py", line 6, in division
    sys.exit(1)
SystemExit: 1
```
**Print exception line**
```
try:
    code;
except Exception as e:
    exc_type, exc_obj, exc_tb = sys.exc_info();
    fname = os.path.split(exc_tb.tb_frame.f_code.co_filename)[1]
    print(exc_type, fname, exc_tb.tb_lineno)
```