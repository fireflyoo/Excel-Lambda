# Excel-Lambda
收集excel365新出的lambda函数公式

``
公式一：字符串反转
strRev=LAMBDA(s,LET(n,LEN(s),IF(n<2,s,RIGHT(s,1)&strRev(LEFT(s,n-1)))))
``
