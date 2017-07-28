# IIFE （Imdiately Invoked Function Expression 立即执行的函数表达式）

### 那么为什么要 IIFE？

* 传统的方法啰嗦，定义和执行分开写；
* 传统的方法直接污染全局命名空间（浏览器里的 global 对象，如 window）

### 函数表达式----Function Expression - var test = function() {}; 
* 函数表达式中的函数可以为匿名函数，也可以有函数名，但是该函数实际上不能直接使用，只能通过表达式左边的变量 a 来调用。 
> 
`var a = function(){  
  alert('Function expression');  
}  
var b = new a();`

### 函数声明----Function Declaration - function test() {};
* 函数声明时必须有函数名。
>
`function a(){  
  alert('Function declaration');  
}  
a();
`

* 这是一个匿名函数
`function () {}`

匿名函数在console下会报错。console的执行和报错如下：
`SyntaxError: Unexpected token (`

* 通过一元操作符+变成了函数表达式。也可以使用 - ~ ！等其他一元运算符或者括号，目的是为了引导解析器，指明运算符附近是一个表达式。以下是三种经典方式 ：

`+function () {   
  
};` 
  
`(function () {  
  
}); `
  
`void function() {  
  
};`

* 函数表达式通过 末尾的() 来调用并运行。就是一个IIFE。