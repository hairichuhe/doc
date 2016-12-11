# SQL简介
	SQL 是用于访问和处理数据库的标准的计算机语言。
    SQL，指结构化查询语言，全称是 Structured Query Language。
    SQL 让您可以访问和处理数据库。
    SQL 是一种 ANSI（American National Standards Institute 美国国家标准化组织）标准的计算机语言。

## SQL能做什么

    SQL 面向数据库执行查询
    SQL 可从数据库取回数据
    SQL 可在数据库中插入新的记录
    SQL 可更新数据库中的数据
    SQL 可从数据库删除记录
    SQL 可创建新数据库
    SQL 可在数据库中创建新表
    SQL 可在数据库中创建存储过程
    SQL 可在数据库中创建视图
    SQL 可以设置表、存储过程和视图的权限

## SQL 是一种标准 - 但是...
虽然 SQL 是一门 ANSI（American National Standards Institute 美国国家标准化组织）标准的计算机语言，但是仍然存在着多种不同版本的 SQL 语言。

然而，为了与 ANSI 标准相兼容，它们必须以相似的方式共同地来支持一些主要的命令（比如 SELECT、UPDATE、DELETE、INSERT、WHERE 等等）。
## 在您的网站中使用 SQL
1.数据库
2.SQL（入库）
3.server（服务器语言）
4.html/css
##　RDBMS
RDBMS 指关系型数据库管理系统，全称 Relational Database Management System。

RDBMS 是 SQL 的基础，同样也是所有现代数据库系统的基础，比如 MS SQL Server、IBM DB2、Oracle、MySQL 以及 Microsoft Access。

RDBMS 中的数据存储在被称为表的数据库对象中。

表是相关的数据项的集合，它由列和行组成。

# SQL语法
## 数据库表
一个数据库通常包含一个或多个表。每个表由一个名字标识（例如:"Websites"）,表包含带有数据的记录（行）。

在本教程中，我们在 MySQL 的 RUNOOB 数据库中中创建了 Websites 表，用于存储网站记录。

## SQL 语句
您需要在数据库上执行的大部分工作都由 SQL 语句完成。

下面的 SQL 语句从 "Websites" 表中选取所有记录：
```
SELECT＊FROM　Websites;
```
*请注意：SQL对大小写不敏感，SELECT与SELECT是相同的。*

## SQL语句后面的分号？
有些数据库要求SQL语句末端用分号。
分号是每条sql的标准分法。

## 一些重要的SQL命令
- SELECT-从数据库中提取数据
- UPDATE-更新数据库中的数据
- DELETE-删除数据库中数据
- INSERTINTO-向数据库中插入新数据
- CREATEDATABALE-创建新数据库
- ALTERDATABALE-变更（修改）数据库
- DROPTABLE-删除表
- CREATEINDEX-创建索引（搜索键）
- DROP INDEX-删除索引

# SQLSELECT语句
SELECT 语句用于从数据库中选取数据。

## SQL SELECT 语句
SELECT 语句用于从数据库中选取数据。

结果被存储在一个结果表中，称为结果集。

## SQL SELECT 语法
```
SELECT cloumn_name,cloumn_name FROM table-name;

SELECT * FORM table_name;
```

## 演示数据库 
本教程，我们将使用Websites表的数据，数据库连接工具，我们用的是Navicat Premium，下面是Websites表的数据
![](img/1.png)

## SELECT Column 实例
下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "country" 列：
```
SELECT name,country FROM websites
```
![](img/2.png)

## SELECT * 实例
下面的 SQL 语句从 "Websites" 表中选取所有列：
```
SELECT * websites
```
![](img/3.png)

## 结果集中的导航
大多数数据库软件系统都允许使用编程函数在结果集中进行导航，比如：Move-To-First-Record、Get-Record-Content、Move-To-Next-Record 等等。
()