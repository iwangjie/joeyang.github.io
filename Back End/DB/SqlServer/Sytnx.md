# 简单语句

## 字段操作

```sql
修改字段名：
EXEC sp_rename 'HistoryMsg.temp','msgContent'

添加新字段：
alter table HistoryMsg ADD fullAmount ntext
```

## 表相关查询

```sql
查数据库所有表：
select * from sysobjects where type='U' and name like '%historymsg%';

查询表字段的名称：
Select name from syscolumns Where ID=OBJECT_ID('HistoryMsg');

查询表的所有表字段的详细信息：
select * from information_schema.columns where TABLE_NAME like lower('%HistoryMsg');
```