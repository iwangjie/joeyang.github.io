# 设置JVM信息

```txt
总堆内存 = 年轻带堆内存 + 年老带堆内存 + 持久带堆内存
年轻带堆内存=对象刚创建出来时放在这里
年老带堆内存=对象在被真正会回收之前会先放在这里
持久带堆内存=class文件，元数据等放在这里
-Xmx      最大总堆内存，一般设置为物理内存的1/4
-Xms      初始总堆内存，一般将它设置的和最大堆内存一样大，这样就不需要根据当前堆使用情况而调整堆的大小了
-Xmn      年轻带堆内存，sun官方推荐为整个堆的3/8
-XX:PermSize=128m            持久带堆的初始大小
-XX:MaxPermSize=128m       持久带堆的最大大小
-XX:+UseParallelGC               使用并发内存回收 
-XX:+DisableExplicitGC          禁用System.gc()的显示内存回收
-Dfile.encoding=UTF-8 (eclipse默认的编码方式为操作系统内核的编码方式，在中文Windows下自然就是
-Dsun.jnu.encoding=UTF-8 GBK，但一般的text file为UTF-8格式，造成冲突，因此需要重新定义JVM的编码方式。)

-verbose:gc
-XX:+PrintGCDetails
-XX:+PrintGCDateStamps
-XX:+PrintGCTimeStamps(GC发生的时间)
-XX:+PrintGCApplicationStoppedTime(GC消耗了多少时间)
-XX:+PrintGCApplicationConcurrentTime(GC之间运行了多少时间)
-Xloggc:C:/Users/joe/Desktop/gc.log
```