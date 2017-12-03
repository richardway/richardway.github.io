---
title: "SQL Language"
date: 2017-12-03 16:21
---

[TOC]

本文记录一些数据库操作的SQL语法。
### 1. 创建表
``` SQL
->CREATE TABLE <table_name>
(
  <colunm_name_1> <type_1>,
  <column_name_2> <type_2>,
  <column_name_3> <type_3>,
  ....
); 
```
### 2. 插入记录
``` SQL
->INSERT INTO <table_name> VALUES ([null], [''], [123], ['abced']);
->INSERT INTO <table_name> (列名...) VALUES (列值..)
MySQL还有另外一种方式：
->INSERT INTO <table_name> SET column_name_1='', column_name_2=123...;
```
### 3. 查询记录
``` SQL
# 选出所有列
->SELECT * from <table_name> WHERE <conditions>

# 选出指定列
->SELECT <column_name_1>, <column_name_2>... from <table_name> WHERE <conditions>

# 联表查询
->SELECT * from <table_name_1> <join_type> <table_name_2> WHERE <conditions>

join_type: join, natural join, inner join, left join, right join
```
### 4. 修改表的名称：
``` SQL
->ALTER TABLE <table_old> RENAME <table_new>;
```
### 5. 修改表的属性名称和类型：
``` SQL
# 如果只修改列属性，可以用modify
->ALTER TABLE <table_name> MODIFY <column_name> <type>;

# 如果需要同时修改列名，使用change
->ALTER TABLE <table_name> CHANGE <column_name_old> <colunm_name_new> <type>;
```
### 6. 添加/删除属性：
``` SQL
->ALTER TABLE <table_name> ADD COLUMN <column_name>;

->ALTER TABLE <table_name> DROP COLUMN <column_name>;
```
### 7. 添加/删除主键约束:
``` SQL
->ALTER TABLE <table_name> ADD CONSTRAINT PRIMARY KEY(<attribute>);

->ALTER TABLE <table_name> DROP PRIMARY KEY;
```
### 8. 添加主键自增，设置自增起始值
指定了主键自增以后，插入记录时就可以将主键值设为null，数据库会自动自增
``` SQL
->ALTER TABLE <table_name> ADD COLUMN <column_name> <type> auto_increment PRIMARY KEY;

->ALTER TABLE <table_name> auto_increment=100;
```
### 9. 删除表
``` SQL
# 删除内容和定义，并释放空间
->DROP TABLE <table_name>; 

# 删除内容保留定义，并释放空间，速度快，不可回滚
->TRUNCATE TABLE <table_name>;

# 删除内容保留定义，不释放空间，一条条记录删除，可以回滚
->DELETE FROM <table_name>
->DELETE FROM <table_name> where [条件]
```
### 10. 其他常用语句:
``` SQL
->show databases;      #显示所有的数据库
->use <database_name>; #选择某个数据库
->show tables;         #显示当前选择的数据库下所有的表
->describe <table_name>;#显示该表定义：所有字段（属性）及其类型
```
