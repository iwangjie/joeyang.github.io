# nodejs

模块分为原生模块和文件模块

原生模块：http，querystrin，dns，url，fs

文件模块引入：
相对路径：require('./test.js')
绝对路径：require('/app/js/test.js')

文件模块中，只有exports和module.exports对象暴露给该外部属性和方法，才能够通过返回的require对象调用。其他方法和属性无法获取。

统一将所需对象定义初始化，不建议在同一个文件内多次require同一个对象。

