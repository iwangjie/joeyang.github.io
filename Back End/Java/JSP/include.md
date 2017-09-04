# 引入文件

1. jsp机制：servlet容器，先将jsp转化成servlet，然后编译成.class文件，放置容器缓冲区【tomcat的work目录下】。

2.每次调用jsp时，服务器会读取编译好的servler.class，处理jsp的请求。

3.<%@ include file="page.jsp"%>

在servlet容器转化jsp为servlet时，将引入的jsp源码全部添加到当前jsp，一并转化成一个servlet，然后编译。【可以理解为整合一个servlet，一起编译，一次执行】

4.<jsp:include page="page.jsp"/>

发送请求给当前jsp，servlet调用当前jsp servlet编译后文件，到引用位置，调用编译后的page.jsp的servlet。class文件。【可以理解为，各自单独编译，互相调用编译的文件】,动态include的jsp文件独立性很强,是一个单独的jsp文件,需要使用的对象,页面设置,都必须有自己创建,当然,还好它和include它的页面的request范围是一致的。

```jsp
<jsp:include page="{relativeURL | <%= expression %>}"  flush="true|false" >
   <jsp:param name="parameterName" value="{parameterValue | <%= expression %>}" />
</jsp:include>
```