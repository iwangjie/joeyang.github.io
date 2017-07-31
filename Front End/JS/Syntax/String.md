# 字符串String

* 1、charCodeAt方法返回一个整数，代表指定位置字符的Unicode编码。 

```txt
strObj.charCodeAt(index) 
说明： 
index将被处理字符的从零开始计数的编号。有效值为0到字符串长度减1的数字。 
如果指定位置没有字符，将返回NaN。 
例如： 
var str = "ABC"; 
str.charCodeAt(0); 
结果：65 
```