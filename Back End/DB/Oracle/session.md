# 会话相关

```sql
1、查询oracle的连接数
select count(*) from v$session;
2、查询oracle的并发连接数
select count(*) from v$session where status='ACTIVE';

select count(*) from v$process --当前的连接数
select value from v$parameter where name = 'processes' --数据库允许的最大连接数

修改最大连接数:
alter system set processes = 300 scope = spfile;
```
