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

* 2.substring 方法 

定义和用法 
substring 方法用于提取字符串中介于两个指定下标之间的字符。 

语法 
stringObject.substring(start,stop) 

参数 描述 
start 必需。一个非负的整数，规定要提取的子串的第一个字符在 stringObject 中的位置。 
stop 可选。一个非负的整数，比要提取的子串的最后一个字符在 stringObject 中的位置多 1。如果省略该参数，那么返回的子串会一直到字符串的结尾。 

返回值 
一个新的字符串，该字符串值包含 stringObject 的一个子字符串，其内容是从 start 处到 stop-1 处的所有字符，其长度为 stop 减 start。 

说明 
substring 方法返回的子串包括 start 处的字符，但不包括 end 处的字符。 
如果 start 与 end 相等，那么该方法返回的就是一个空串（即长度为 0 的字符串）。 
如果 start 比 end 大，那么该方法在提取子串之前会先交换这两个参数。 
如果 start 或 end 为负数，那么它将被替换为 0。 

2.substr 方法 

定义和用法 
substr 方法用于返回一个从指定位置开始的指定长度的子字符串。 

语法 
stringObject.substr(start [, length ]) 

参数 描述 
start 必需。所需的子字符串的起始位置。字符串中的第一个字符的索引为 0。 
length 可选。在返回的子字符串中应包括的字符个数。 

说明 
如果 length 为 0 或负数，将返回一个空字符串。 
如果没有指定该参数，则子字符串将延续到stringObject的最后。 