# 登陆方式

```txt
sqlplus有几种登陆方式 比如：
1.C: > sqlplus "/as sysdba"   --以操作系统权限认证的oracle sys管理员登陆
2.C: > sqlplus /nolog             --不在cmd或者terminal当中暴露密码的登陆方式
SQL> conn /as sysdba
&
SQL> conn sys/password as sysdba
3.C: > sqlplus scott/tiger      --非管理员用户登陆
4.C: > sqlplus scott/tiger@orcl    --非管理员用户使用tns别名登陆
5.C: > sqlplus sys/password@orcl as sysdba --管理员用户使用tns别名登陆
6.C: > sqlplus                       --不显露密码的登陆方式
Enter user-name：sys
Enter password：password as sysdba     --以sys用户登陆的话 必须要加上 as sysdba 子句
```