# 性能监控

## 进程分析

```sql
查看所有活动进程：
use master
go
exec sp_who 'active'
go

显示会话ID标识的特定进程
use master
go
exec sp_who '10'
go

--删除阻塞的进程
use master
go
kill 00
go
```