# Excel-Lambda
收集excel365新出的lambda函数公式

```
#公式一：字符串反转(用了递归）
strRev=LAMBDA(s,LET(n,LEN(s),IF(n<2,s,RIGHT(s,1)&strRev(LEFT(s,n-1)))))  
#公式二：字符串反转(用了数组)
strRev=LAMBDA(s,LET(n,LEN(s),CONCAT(MID(s,SEQUENCE(n,,n,-1),1))))
```

```
#身份证校验
#其中MOD(2^SEQUENCE(17,,17,-1),11)),11)这段可以改成数组常量{7;9;10;5;8;4;2;1;6;3;7;9;10;5;8;4;2}
validID=LAMBDA(ID,MID("10X98765432",(MOD(SUM(MID(ID,SEQUENCE(17),1)*MOD(2^SEQUENCE(17,,17,-1),11)),11)+1),1)=RIGHT(ID))
validID=LAMBDA(ID,MID("10X98765432",(MOD(SUM(MID(ID,SEQUENCE(17),1)*{7;9;10;5;8;4;2;1;6;3;7;9;10;5;8;4;2}),11)+1),1)=RIGHT(ID))
```
