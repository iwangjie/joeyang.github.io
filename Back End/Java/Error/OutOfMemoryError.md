# java.lang.OutOfMemoryError: PermGen space

* PermGen space的全称是Permanent Generation space,是指**内存的永久保存区域**,这块内存主要是被JVM存放Class和Meta信息的,Class在被Loader时就会被放到PermGen space中, 

* 它和**存放类实例**(Instance)的Heap区域不同,**GC(Garbage Collection)**不会在主程序运行期对PermGen space进行清理，所以如果你的应用中有很多CLASS的话,就很可能出现**PermGen space**错误, 

* 这种错误常见在web服务器对JSP进行**pre compile**的时候。如果你的WEB APP下都用了大量的第三方jar, 其大小超过了jvm默认的大小(4M)那么就会产生此错误信息了。 

* 解决方法： 手动设置MaxPermSize大小修改TOMCAT_HOME/bin/catalina.sh在