# Web SQL Database

我们经常在数据库中处理大量结构化数据，html5引入Web SQL Database概念，它使用 SQL 来操纵客户端数据库的 API，这些 API 是异步的，规范中使用的方言是SQLlite，悲剧正是产生于此，Web SQL Database规范页面有着这样的声明:

```txt
This document was on the W3C Recommendation track but specification work has stopped. The specification reached an impasse: all interested implementors have used the same SQL backend (Sqlite), but we need multiple independent implementations to proceed along a standardisation path.
```

```txt
这个文档曾经在W3C推荐规范上，但规范工作已经停止了。目前已经陷入了一个僵局：目前的所有实现都是基于同一个SQL后端（SQLite），但是我们需要更多的独立实现来完成标准化。

也就是说这是一个废弃的标准了，
由于Web SQL Database规范已经被废弃，原因说的很清楚，当前的SQL规范采用SQLite的SQL方言，而作为一个标准，这是不可接受的，每个浏览器都有自己的实现这还搞毛的标准。这样浏览器兼容性就不重要了，估计慢慢会被遗忘。
```

## 三个核心方法

* openDatabase：这个方法使用现有数据库或新建数据库来创建数据库对象
* transaction：这个方法允许我们根据情况控制事务提交或回滚
* executeSql：这个方法用于执行SQL 查询

openDatabase

我们可以使用这样简单的一条语句，创建或打开一个本地的数据库对象

```js
var db = openDatabase('testDB', '1.0', 'Test DB', 2 * 1024 * 1024);
```

openDatabase接收五个参数：

```log
数据库名字
数据库版本号
显示名字
数据库保存数据的大小（以字节为单位 )
回调函数（非必须)
```

如果提供了回调函数，回调函数用以调用 changeVersion() 函数，不管给定什么样的版本号，回调函数将把数据库的版本号设置为空。如果没有提供回调函数，则以给定的版本号创建数据库。

transaction

transaction方法用以处理事务，当一条语句执行失败的时候，整个事务回滚。方法有三个参数

```txt
包含事务内容的一个方法
执行成功回调函数（可选）
执行失败回调函数（可选）
```

```js
db.transaction(function (context) {
           context.executeSql('CREATE TABLE IF NOT EXISTS testTable (id unique, name)');
           context.executeSql('INSERT INTO testTable (id, name) VALUES (0, "Byron")');
           context.executeSql('INSERT INTO testTable (id, name) VALUES (1, "Casper")');
           context.executeSql('INSERT INTO testTable (id, name) VALUES (2, "Frank")');
         });
```

executeSql

executeSql方法用以执行SQL语句，返回结果，方法有四个参数

```txt
查询字符串
用以替换查询字符串中问号的参数
执行成功回调函数（可选）
执行失败回调函数（可选）
```

```js
db.transaction(function (context) {
           context.executeSql('SELECT * FROM testTable', [], function (context, results) {
            var len = results.rows.length, i;
            console.log('Got '+len+' rows.');
               for (i = 0; i < len; i++){
              console.log('id: '+results.rows.item(i).id);
              console.log('name: '+results.rows.item(i).name);
            }
         });
```

```log
executeSql执行成功后进入成功的回调函数，而回调函数有一个参数为result，而这个result就是查询出来的数据集。其数据类型为 SQLResultSet，其中最重要的属性—SQLResultSetRowList 类型的 rows 是数据集的“行”，rows 有两个属性：length、item，因此，获取查询结果的某一行某一列的值 ：result.rows[i].item[fieldname]
```