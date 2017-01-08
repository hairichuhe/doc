# SQL简介
** 电脑没装mysql和Navicat Premium的同学，可以先访问mysql和Navicat Premium安装教程  [点击此处访问](http://www.wangxiaojun.top/mysqlinstall/mysqlinstall.html) **
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

## 本教程使用的sql文件
[websites](file/websites.sql)
[access_log](file/access_log.sql)
[apps](file/apps.sql)
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
(注解：相当于在表中建立一个游标，指定是第几行的数据。)
参考链接：[jbdc实例](http://www.yiibai.com/jdbc/navigate-result-sets.html)
[详情参考](http://wiki.jikexueyuan.com/project/jdbc/result-sets.html)

# SQL SELECT DISTINCT 语句
SELECT DISTINCT 语句用于返回唯一不同的值。
## SQL SELECT DISTINCT 语句
在表中，一个列可能会包含多个重复值，有时您也许希望仅仅列出不同（distinct）的值。

DISTINCT 关键词用于返回唯一不同的值。

## SQL SELECT DISTINCT 语法
```
SELECT DISTINCT column_name,colunm FROM table_name
```

## SELECT DISTINCT 实例
下面的 SQL 语句仅从 "Websites" 表的 "country" 列中选取唯一不同的值，也就是去掉 "country" 列重复值：
```
SELECT DISTINCT country FROM websites
```
![](img/4.png)

# SQL WHERE 子句
WHERE 子句用于过滤记录。

## SQL WHERE 语法
```
SELECT column_name,column_name FROM table_name FROM column_name operator value
```

## 示例演示
```
SELECT * FROM websites WHERE country="CN"
```
![](img/5.png)

## 文本字段 vs. 数值字段
sql使用单引号来环绕文本值（大部分的数据库系统也支持双引号）。
在上个实例中‘CN’文本字段使用了单引号。
如果是数值，请不要使用引号。
实例
```
SELECT * FROM websites WHERE id=1;
```
![](img/6.png)

## WHERE 子句中的运算符
下面的运算符可以在 WHERE 子句中使用：

- =	等于
- <>	不等于。注释：在 SQL 的一些版本中，该操作符可被写成 !=
- >	大于
- <	小于
- >=	大于等于
- <=	小于等于
- BETWEEN	在某个范围内
- LIKE	搜索某种模式
- IN	指定针对某个列的多个可能值

# SQL AND & OR 运算符
AND & OR 运算符用于基于一个以上的条件对记录进行过滤。

如果第一个条件和第二个条件都成立，则 AND 运算符显示一条记录。
如果第一个条件和第二个条件中只要有一个成立，则 OR 运算符显示一条记录。

## AND 运算符实例
下面的 SQL 语句从 "Websites" 表中选取国家为 "CN" 且alexa排名大于 "50" 的所有网站：
示例
```
SELECT * FROM websites WHERE country='CN' AND alexa>50;
```
![](img/7.png)

## OR运算实例
```
SELECT * FROM websites WHERE country='CN' OR country='USA';
```
![](img/8.png)

## 结合 AND & OR
您也可以把 AND 和 OR 结合起来（使用圆括号来组成复杂的表达式）。
下面的 SQL 语句从 "Websites" 表中选取 alexa 排名大于 "15" 且国家为 "CN" 或 "USA" 的所有网站：
```
SELECT * FROM websites WHERE alexa>15 AND (country='USA' OR country='CN');
```
![](img/9.png)

# SQL ORDER BY 关键字
ORDER BY 关键字用于对结果集进行排序。
ORDER BY 关键字用于对结果集按照一个列或者多个列进行排序。
ORDER BY 关键字默认按照升序对记录进行排序。如果需要按照降序对记录进行排序，您可以使用 DESC 关键字。

## SQL ORDER BY 语法
```
SELECT column_name,column_name FROM table_name ORDER BY column_name,column_name ASC|DESC;
```

## ORDER BY 实例
下面的 SQL 语句从 "Websites" 表中选取所有网站，并按照 "alexa" 列排序：
示例：
```
SELECT * FROM websites ORDER BY alexa ASC;
```


## ORDER BY DESC 实例
下面的 SQL 语句从 "Websites" 表中选取所有网站，并按照 "alexa" 列降序排序：
```
SELECT * FROM websites ORDER BY alexa DESC;
```
![](img/11.png)

## ORDER BY 多列
下面的 SQL 语句从 "Websites" 表中选取所有网站，并按照 "country" 和 "alexa" 列排序：
```
```
（理解：先是根据国家排序，排完然后在国家中再根据排名排序）
![](img/12.png)

# SQL INSERT INTO 语句
INSERT INTO 语句用于向表中插入新记录。

## SQL INSERT INTO 语法
INSERT INTO 语句可以有两种编写形式。
第一种形式无需指定要插入数据的列名，只需提供被插入的值即可：
```
INSERT INTO table-name VALUES (value1,value2.…);
```
第二种形式需要指定列名及被插入的值：
```
INSERT INTO table_name (column1,column2,…) VALUES (value1,value2,value3,…);
```

## 插入实例
```
INSERT INTO websites (name,url,alexa,country) VALUES ('百度','http://www.baidu.com','4','CN');
```
![](img/13.png)
** 注意当不指定列明的时候，插入的数据项的长度必须与列的长度相等！

## 在指定的列插入数据
我们也可以在指定的列插入数据。
下面的 SQL 语句将插入一个新行，但是只在 "name"、"url" 和 "country" 列插入数据（id 字段会自动更新）：
```
INSERT INTO websites (name,url,country) VALUES ('晓军博客','http://www.wangxiaojun.top','CN');
```
![](img/14.png)

# SQL UPDATE 语句
UPDATE 语句用于更新表中已存在的记录。

## sql update 语法

```
UPDATE table_name SET column1=value1,column2=value2,… WHERE some_column=somoe_value;
```
** 注意：请注意 SQL UPDATE 语句中的 WHERE 子句！
WHERE 子句规定哪条记录或者哪些记录需要更新。如果您省略了 WHERE 子句，所有的记录都将被更新！

## 实例
假设我们要把 "晓军博客" 的 alexa 排名更新为 5000，country 改为 USA。
我们使用下面的 SQL 语句：
```
UPDATE websites SET alexa='5000', country='USA' WHERE name='晓军博客';
```
![](img/15.png)

**　注意：在更新记录时要格外小心！在上面的实例中，如果我们省略了 WHERE 子句，如下所示：
```
UPDATE Websites
SET alexa='5000', country='USA'
```
执行以上代码会将 Websites 表中所有数据的 alexa 改为 5000，country 改为 USA。
执行没有 WHERE 子句的 UPDATE 要慎重，再慎重。

# SQL DELETE 语句
DELETE 语句用于删除表中的记录。

## SQL DELETE 语法
```
DELETE FROM table_name WHERE some_column=some_value;
```
**　注意：请注意 SQL DELETE 语句中的 WHERE 子句！
WHERE 子句规定哪条记录或者哪些记录需要删除。如果您省略了 WHERE 子句，所有的记录都将被删除！

## 实例
假设我们要从 "Websites" 表中删除网站名为 "百度" 且国家为 CN 的网站 。
我们使用下面的 SQL 语句：

```
DELETE FROM websites WHERE name='百度' AND country='CN';
```
![](img/16.png)

## 删除所有数据
您可以在不删除表的情况下，删除表中所有的行。这意味着表结构、属性、索引将保持不变：
```
DELETE FROM table_name；或者
DELETE * FROM table_name;
```
** 注意：在删除记录时要格外小心，因为您不能重来！

# SQL SELECT TOP, LIMIT, ROWNUM 子句
## SQL SELECT TOP 子句
SELECT TOP 子句用于规定要返回的记录的数目。
SELECT TOP 子句对于拥有数千条记录的大型表来说，是非常有用的。
** 注意：并非所有的数据库系统都支持 SELECT TOP 子句。

## 实例(mysql)
```
SELECT * FROM websites LIMIT 2;
```

![](img/17.png)
|| 理解：这个语法，就是是返回规定已经数目的集合，有三种是因为不同的数据库所用的语法不一样！

# SQL LIKE 操作符
LIKE 操作符用于在 WHERE 子句中搜索列中的指定模式。

## SQL like 语法
```
SELECT column_name FROM table_name WHERE column_name LIKE pattern;
```

## SQL LIKE 操作符实例
下面的 SQL 语句选取 name 以字母 "G" 开始的所有客户：
```
SELECT * FROM websites WHERE name LIKE 'G%';
```
![](img/18.png)

|| 提示："%" 符号用于在模式的前后定义通配符（缺省字母）。您将在下一章中学习更多有关通配符的知识。

下面的 SQL 语句选取 name 以字母 "k" 结尾的所有客户：
```
SELECT * FROM websites WHERE name LIKE '%k';
```
![](img/19.png)

下面的 SQL 语句选取 name 包含模式 "oo" 的所有客户：
```
SELECT * FROM websites WHERE name LIKE '%oo%';
```
![](img/20.png)

通过使用 NOT 关键字，您可以选取不匹配模式的记录。

下面的 SQL 语句选取 name 不包含模式 "oo" 的所有客户：
```
SELECT * FROM websites WHERE name NOT LIKE '%oo%';
```
![](img/21.png)

# SQL 通配符
通配符可用于替代字符串中的任何其他字符。
在 SQL 中，通配符与 SQL LIKE 操作符一起使用。

SQL 通配符用于搜索表中的数据。

在 SQL 中，可使用以下通配符：
- 
- % 	替代 0 个或多个字符
- _ 	替代一个字符
- [charlist] 	字符列中的任何单一字符
- [^charlist]或[!charlist] 	不在字符列中的任何单一字符

##　使用 SQL % 通配符
下面的 SQL 语句选取 url 以字母 "https" 开始的所有网站：
实例：
```
SELECT * FROM websites WHERE url LIKE 'https%';
```
![](img/22.png)

## 使用 SQL _ 通配符
下面的 SQL 语句选取 name 以一个任意字符开始，然后是 "oogle" 的所有客户：
```
SELECT * FROM websites WHERE name LIKE '_oogle';
```
![](img/23.png)
下面的 SQL 语句选取 name 以 "G" 开始，然后是一个任意字符，然后是 "o"，然后是一个任意字符，然后是 "le" 的所有网站：
```
SELECT * FROM websites WHERE name LIKE 'G_o_le';
```
![](img/24.png)

## 使用 SQL [charlist] 通配符
MySQL 中使用 REGEXP 或 NOT REGEXP 运算符 (或 RLIKE 和 NOT RLIKE) 来操作正则表达式。

下面的 SQL 语句选取 name 以 "G"、"F" 或 "s" 开始的所有网站：
```
SELECT * FROM websites WHERE name REGEXP '^[GFs]';
```
![](img/25.png)

下面的 SQL 语句选取 name 以 A 到 H 字母开头的网站：
```
SELECT * FROM websites WHERE name REGEXP '^[A-H]';
```
![](img/26.png)

下面的 SQL 语句选取 name 不以 A 到 H 字母开头的网站：
```
SELECT * FROM websites WHERE name REGEXP '^[^A-H]'
```
![](img/27.png)

# IN 操作符
IN 操作符允许您在 WHERE 子句中规定多个值。

sql in 语法
```
SELECT column_name FROM teble_name WHERE column_name IN （value1，value2,…);
```

## 实例
```
SELECT * FROM websites WHERE name IN ('Google','晓军博客');
```
![](img/28.png)

# SQL BETWEEN 操作符
BETWEEN 操作符用于选取介于两个值之间的数据范围内的值。
BETWEEN 操作符选取介于两个值之间的数据范围内的值。这些值可以是数值、文本或者日期。
## SQL BETWEEN 语法
```
SELECT column_name FROM table_name WHERE column_name BETWEEN value1 AND value2;
```

## 实例
下面的 SQL 语句选取 alexa 介于 1 和 20 之间的所有网站：
```
SELECT * FROM websites WHERE alexa BETWEEN '1' AND '20';
```
![](img/29.png)

## NOT BETWEEN 操作符实例
选择不在1到20之间的
```
SELECT * FROM websites WHERE alexa NOT BETWEEN 1 AND 20;
```
![](img/30.png)

## 带有 IN 的 BETWEEN 操作符实例
下面的 SQL 语句选取alexa介于 1 和 20 之间但 country 不为 USA 和 IND 的所有网站：
```
SELECT * FROM websites WHERE (alexa BETWEEN 1 AND 20) AND NOT country IN ('USA','IND');
```
![](img/31.png)

## 带有文本值的 BETWEEN 操作符实例
下面的 SQL 语句选取 name 以介于 'A' 和 'H' 之间字母开始的所有网站：
```
SELECT * FROM websites WHERE name BETWEEN 'A' AND 'H';
```
![](img/32.png)
** 注意：首字母！！匹配首字母！！

## 带有文本值的 NOT BETWEEN 操作符实例
```
SELECT * FROM websites WHERE name NOT BETWEEN 'A' AND 'H';
```
![](img/33.png)

## 示例表
下面是 "access_log" 网站访问记录表的数据，其中：
aid：为自增 id。
site_id：为对应 websites表的网站 id。
count：访问次数。
date：为访问日期。
![](img/34.png)

## 带有日期值的 BETWEEN 操作符实例
下面的 SQL 语句选取 date 介于 '2016-05-10' 和 '2016-05-14' 之间的所有访问记录：
```
SELECT * FROM access_log WHERE date BETWEEN '2016-05-10' AND '2016-05-14';
```
![](img/35.png)
** 注意：请注意，在不同的数据库中，BETWEEN 操作符会产生不同的结果！
在某些数据库中，BETWEEN 选取介于两个值之间但不包括两个测试值的字段。
在某些数据库中，BETWEEN 选取介于两个值之间且包括两个测试值的字段。
在某些数据库中，BETWEEN 选取介于两个值之间且包括第一个测试值但不包括最后一个测试值的字段。

因此，请检查您的数据库是如何处理 BETWEEN 操作符！

# SQL 别名
通过使用 SQL，可以为表名称或列名称指定别名。

基本上，创建别名是为了让列名称的可读性更强。

## 列的 SQL 别名语法
```
SELECT column_name AS alias_name FROM table_name;
```

## 表的sql别名语法
```
SELECT column_name FROM table_name AS alias_name;
```

## 列别名实例
下面的 SQL 语句指定了两个别名，一个是 name 列的别名，一个是 country 列的别名。提示：如果列名称包含空格，要求使用双引号或方括号：
```
SELECT name AS n,country AS c FROM websites;
```
![](img/36.png)

## 在下面的 SQL 语句中，我们把四个列（name、url、alexa 和 country）结合在一起，并创建一个名为 "site_info" 的别名：
```
SELECT name,CONCAT(url,', ',alexa,', ',country) AS site_info FROM websites;
```
![](img/37.png)

## 表的别名实例
下面的 SQL 语句选取 "菜鸟教程" 的所访问记录。我们使用 "Websites" 和 "access_log" 表，并分别为它们指定表别名 "w" 和 "a"（通过使用别名让 SQL 更简短）：
```
SELECT w.name,w.url,a.count,a.date FROM websites AS w,access_log AS a WHERE a.site_id=w.id AND w.name="晓军博客"
```
![](img/38.png)
![](img/39.png)

**　注意：在下面的情况下，使用别名很有用：
在查询中涉及超过一个表
在查询中使用了函数
列名称很长或者可读性差
需要把两个列或者多个列结合在一起

## SQL 连接(JOIN)
SQL join 用于把来自两个或多个表的行结合起来。
SQL JOIN 子句用于把来自两个或多个表的行结合起来，基于这些表之间的共同字段。
最常见的 JOIN 类型：SQL INNER JOIN（简单的 JOIN）。 SQL INNER JOIN 从多个表中返回满足 JOIN 条件的所有行。
## 实例
请注意，"Websites" 表中的 "id" 列指向 "access_log" 表中的字段 "site_id"。上面这两个表是通过 "site_id" 列联系起来的。
然后，如果我们运行下面的 SQL 语句（包含 INNER JOIN）：
```
SELECT websites.id,websites.name,access_log.count,access_log.date FROM websites INNER JOIN access_log ON websites.id=access_log.site_id
```
![](img/40.png)

## 不同的 SQL JOIN

在我们继续讲解实例之前，我们先列出您可以使用的不同的 SQL JOIN 类型：

    INNER JOIN：如果表中有至少一个匹配，则返回行
    LEFT JOIN：即使右表中没有匹配，也从左表返回所有的行
    RIGHT JOIN：即使左表中没有匹配，也从右表返回所有的行
    FULL JOIN：只要其中一个表中存在匹配，则返回行


## SQL INNER JOIN 关键字
INNER JOIN 关键字在表中存在至少一个匹配时返回行。

## INNER JOIN 语法
```
SELECT column_name FROM table1 INNER JOIN table2 ON table1.column_name=table2.column_name;
```
或者
```
SELECT column_name FROM table1 JOIN table2 ON table1.column_name=table2.column_name;
```

**　注意：INNER JOIN 和 JOIN 是相同的

## INNER JOIN 实例
```
SELECT websites.name,access_log.count,access_log.date
FROM websites
INNER JOIN access_log
ON websites.id=access_log.site_id
ORDER BY access_log.count;
```
![](img/41.png)
**　注释：INNER JOIN 关键字在表中存在至少一个匹配时返回行。如果 "Websites" 表中的行在 "access_log" 中没有匹配，则不会列出这些行。

# SQL LEFT JOIN 关键字
LEFT JOIN 关键字从左表（table1）返回所有的行，即使右表（table2）中没有匹配。如果右表中没有匹配，则结果为 NULL。

## SQL LEFT JOIN 语法
```
SELECT column_name FROM table1 LEFT JOIN table2 ON　table1.column_name=table2.column_name;
```

## SQL LEFT JOIN 实例
下面的 SQL 语句将返回所有网站及他们的访问量（如果有的话）。

以下实例中我们把 Websites 作为左表，access_log 作为右表：

```
SELECT websites.name,access_log.count,access_log.date
FROM websites
LEFT JOIN access_log
ON websites.id=access_log.site_id
ORDER BY access_log.count
DESC;
```
![](img/42.png)
**　注释：LEFT JOIN 关键字从左表（Websites）返回所有的行，即使右表（access_log）中没有匹配。

# SQL RIGHT JOIN 关键字
RIGHT JOIN 关键字从右表（table2）返回所有的行，即使左表（table1）中没有匹配。如果左表中没有匹配，则结果为 NULL。
## SQL RIGHT JOIN 语法
```
SELECT column_name FROM table1 RIGHT JOIN table2 ON table.column=table2.column;
```

## SQL RIGHT JOIN 实例
下面的 SQL 语句将返回网站的访问记录。

以下实例中我们把 access_log 作为左表，Websites 作为右表：
```
SELECT websites.name, access_log.count,access_log.date
FROM access_log
RIGHT JOIN websites
ON access_log.site_id=websites.id
ORDER BY access_log.count
DESC;
```
![](img/43.png)
** 注释：RIGHT JOIN 关键字从右表（Websites）返回所有的行，即使左表（access_log）中没有匹配。

## SQL FULL OUTER JOIN 关键字
FULL OUTER JOIN 关键字只要左表（table1）和右表（table2）其中一个表中存在匹配，则返回行.

FULL OUTER JOIN 关键字结合了 LEFT JOIN 和 RIGHT JOIN 的结果。

## SQL FULL OUTER JOIN 语法
```
SELECT column_name
FROM table1
FULL JOIN table2
ON table.column=table2.column
```

## SQL FULL OUTER JOIN 实例
下面的 SQL 语句选取所有网站访问记录。

MySQL中不支持 FULL OUTER JOIN，你可以在 SQL Server 测试以下实例。
```
SELECT websites.name,access_log.count,access_log.date
FROM websites
FULL JOIN access_log
ON websites.id=access_log.site_id
ORDER BY access_log.count 
DESC;
```
** 注释：FULL OUTER JOIN 关键字返回左表（Websites）和右表（access_log）中所有的行。如果 "Websites" 表中的行在 "access_log" 中没有匹配或者 "access_log" 表中的行在 "Websites" 表中没有匹配，也会列出这些行。

# SQL UNION 操作符
SQL UNION 操作符合并两个或多个 SELECT 语句的结果。
UNION 操作符用于合并两个或多个 SELECT 语句的结果集。

请注意，UNION 内部的每个 SELECT 语句必须拥有相同数量的列。列也必须拥有相似的数据类型。同时，每个 SELECT 语句中的列的顺序必须相同。

## SQL UNION 语法
```
SELECT column_name FROM　table
UNION
SELECT column_name FROM table
```
** 注释：UNION 结果集中的列名总是等于 UNION 中第一个 SELECT 语句中的列名。

## SQL UNION 实例
下面的 SQL 语句从 "Websites" 和 "apps" 表中选取所有不同的country（只有不同的值）：
```
SELECT country FROM websites
UNION
SELECT country FROM apps
ORDER BY country;
```
![](img/44.png)
**　注释：UNION 不能用于列出两个表中所有的country。如果一些网站和APP来自同一个国家，每个国家只会列出一次。UNION 只会选取不同的值。请使用 UNION ALL 来选取重复的值！

## SQL UNION ALL 实例
下面的 SQL 语句使用 UNION ALL 从 "Websites" 和 "apps" 表中选取所有的country（也有重复的值）：
```
SELECT country FROM websites
UNION ALL
SELECT country FROM apps
ORDER BY country;
```
![](img/45.png)

## 带有 WHERE 的 SQL UNION ALL
下面的 SQL 语句使用 UNION ALL 从 "Websites" 和 "apps" 表中选取所有的中国(CN)的数据（也有重复的值）：
```
SELECT country, name FROM Websites
WHERE country='CN'
UNION ALL
SELECT country, app_name FROM apps
WHERE country='CN'
ORDER BY country; 
```
![](img/46.png)

# SQL SELECT INTO 语句
通过 SQL，您可以从一个表复制信息到另一个表。

SELECT INTO 语句从一个表复制数据，然后把数据插入到另一个新表中。

** MySQL 数据库不支持 SELECT ... INTO 语句，但支持 INSERT INTO ... SELECT 。

当然你可以使用以下语句来拷贝表结构及数据： **

## mysql 创建新表并复制

### 语法
```
CREATE TABLE 新表 SELECT * FROM 旧表
```

### 实例
```
CREATE TABLE apps_beifen
SELECT * FROM apps
```
![](img/47.png)
![](img/48.png)


# SQL INSERT INTO SELECT 语句
通过 SQL，您可以从一个表复制信息到另一个表。

INSERT INTO SELECT 语句从一个表复制数据，然后把数据插入到一个已存在的表中。目标表中任何已存在的行都不会受影响。

## SQL INSERT INTO SELECT 语法
我们可以从一个表中复制所有的列插入到另一个已存在的表中：
```
ISNERT INTO tablue2 
SELECT * FROM table1
```
或者我们可以只复制希望的列插入到另一个已存在的表中：
```
INSERT INTO table2 (column_name)
SELECT column_name FROM table1
```
## SQL INSERT INTO SELECT 实例
复制 "apps" 中的数据插入到 "Websites" 中：
```
INSERT INTO websites (name,country)
SELECT app_name,country 
FROM apps;
```
![](img/49.png)
只复 QQ 的 APP 到 "Websites" 中：
```
INSERT INTO websites (name,country)
SELECT app_name,country
FROM apps
WHERE id=1;
SELECT * FROM websites;
```
![](img/50.png)

# SQL CREATE DATABASE 语句
## SQL CREATE DATABASE 语法
```
CREATE DATABASE dbname
```
## SQL CREATE DATABASE 实例
下面的 SQL 语句创建一个名为 "my_db" 的数据库：
```
CREATE DATABASE my_db;
```
![](img/51.png)

# SQL CREATE TABLE 语句
CREATE TABLE 语句用于创建数据库中的表。

表由行和列组成，每个表都必须有个表名。

## SQL CREATE TABLE 语法
```
CREATE TABLE table_name
(
column_name1 data_type(size)
column_name2 data_type(size)
column_name3 data_type(size)
)
```
column_name 参数规定表中列的名称。

data_type 参数规定列的数据类型（例如 varchar、integer、decimal、date 等等）。

size 参数规定表中列的最大长度。

## SQL CREATE TABLE 实例
现在我们想要创建一个名为 "Persons" 的表，包含五列：PersonID、LastName、FirstName、Address 和 City。

我们使用下面的 CREATE TABLE 语句：
```
CREATE TABLE person
(
personID int,
lastName varchar(255),
firstName varchar(255),
addRess varchar(255),
city varchar(255)
);
SELECT * FROM person;
```
PersonID 列的数据类型是 int，包含整数。

LastName、FirstName、Address 和 City 列的数据类型是 varchar，包含字符，且这些字段的最大长度为 255 个字符。

空的 "Persons" 表如下所示：
![](img/52.png)

# SQL 约束（Constraints）
SQL 约束用于规定表中的数据规则。

如果存在违反约束的数据行为，行为会被约束终止。

约束可以在创建表时规定（通过 CREATE TABLE 语句），或者在表创建之后规定（通过 ALTER TABLE 语句）。

## SQL CREATE TABLE + CONSTRAINT 语法
```
CREATE TABLE table_name
(
column_name1 data_type(size) constraint_name,
column_name2 data_type(size) constraint_name,
column_name3 data_type(size) constraint_name
)
```
在 SQL 中，我们有如下约束：

    NOT NULL - 指示某列不能存储 NULL 值。
    UNIQUE - 保证某列的每行必须有唯一的值。
    PRIMARY KEY - NOT NULL 和 UNIQUE 的结合。确保某列（或两个列多个列的结合）有唯一标识，有助于更容易更快速地找到表中的一个特定的记录。
    FOREIGN KEY - 保证一个表中的数据匹配另一个表中的值的参照完整性。
    CHECK - 保证列中的值符合指定的条件。
    DEFAULT - 规定没有给列赋值时的默认值。

在下面的章节，我们会详细讲解每一种约束。

## SQL NOT NULL 约束
NOT NULL 约束强制列不接受 NULL 值。

NOT NULL 约束强制字段始终包含
值。这意味着，如果不向字段添加值，就无法插入新记录或者更新记录。

下面的 SQL 强制 "P_Id" 列和 "LastName" 列不接受 NULL 值：

```
CREATE TABLE 
(
P_Id int NOT NULL,
LastName varchar(256) NOT NULL,
FristName varchar(256),
Address varchar(256),
City varchar(255)
)
```

# SQL UNIQUE 约束
UNIQUE 约束唯一标识数据库表中的每条记录。

UNIQUE 和 PRIMARY KEY 约束均为列或列集合提供了唯一性的保证。

PRIMARY KEY 约束拥有自动定义的 UNIQUE 约束。

请注意，每个表可以有多个 UNIQUE 约束，但是每个表只能有一个 PRIMARY KEY 约束。

## CREATE TABLE 时的 SQL UNIQUE 约束
下面的 SQL 在 "Persons" 表创建时在 "P_Id" 列上创建 UNIQUE 约束：

MySQL：
```
CREATE TABLE psersons
(
P_id int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
City varchar(255),
UNIQUE (P_id)
)
```

## ALTER TABLE 时的 SQL UNIQUE 约束

当表已被创建时，如需在 "P_Id" 列创建 UNIQUE 约束，请使用下面的 SQL：
```
ALERT TABLE Persons
ADD UNIQUE (P_Id)
```

##　撤销 UNIQUE 约束
如需撤销 UNIQUE 约束，请使用下面的 SQL：

MySQL：
```
ALTER TABLE person
DROP INDEX P_Id
```

# SQL PRIMARY KEY 约束
PRIMARY KEY 约束唯一标识数据库表中的每条记录。

主键必须包含唯一的值。

主键列不能包含 NULL 值。

每个表都应该有一个主键，并且每个表只能有一个主键。

##　CREATE TABLE 时的 SQL PRIMARY KEY 约束
下面的 SQL 在 "Persons" 表创建时在 "P_Id" 列上创建 PRIMARY KEY 约束：

MySQL：
```
CREATE TABLE Persons
(
P_Id int NOT NULL,
LastName varchar(255)NOT NULL,
Fristname varchar(255),
Address varchar(255),
City varchar(255),
PRIMARY KEY (P_Id)
)
```

## ALTER TABLE 时的 SQL PRIMARY KEY 约束
当表已被创建时，如需在 "P_Id" 列创建 PRIMARY KEY 约束，请使用下面的 SQL：

MySQL / SQL Server / Oracle / MS Access：
```
ALTER TABLE persons
ADD PRIMARY KEY (P_Id
```

##　撤销 PRIMARY KEY 约束
如需撤销 PRIMARY KEY 约束，请使用下面的 SQL：

MySQL：
```
ALTER TABLE persons
DROP PRIMARY KEY
```

# SQL FOREIGN KEY 约束
一个表中的 FOREIGN KEY 指向另一个表中的 PRIMARY KEY。

让我们通过一个实例来解释外键。请看下面两个表：

"Persons" 表：
![](img/53.png)
"Orders" 表：
![](img/54.png)


请注意，"Orders" 表中的 "P_Id" 列指向 "Persons" 表中的 "P_Id" 列。

"Persons" 表中的 "P_Id" 列是 "Persons" 表中的 PRIMARY KEY。

"Orders" 表中的 "P_Id" 列是 "Orders" 表中的 FOREIGN KEY。

FOREIGN KEY 约束用于预防破坏表之间连接的行为。

FOREIGN KEY 约束也能防止非法数据插入外键列，因为它必须是它指向的那个表中的值之一。

## CREATE TABLE 时的 SQL FOREIGN KEY 约束
下面的 SQL 在 "Orders" 表创建时在 "P_Id" 列上创建 FOREIGN KEY 约束：

MySQL：
```
CREATE TABLE orders
(
o_id int NOT NULL,
orderNo int NOT NULL,
P_Id int,
PRIMARY KEY (o_id),
FOREIGN KEY (p_id) REFERENCES persons(P_id)
)
```

## ALTER TABLE 时的 SQL FOREIGN KEY 约束
当 "Orders" 表已被创建时，如需在 "P_Id" 列创建 FOREIGN KEY 约束，请使用下面的 SQL：

MySQL / SQL Server / Oracle / MS Access：
```
ALTER TABLE orders
ADD FOREIGN KEY (P_id)
REFERENCES persons(p_id)
```

## 撤销 FOREIGN KEY 约束
如需撤销 FOREIGN KEY 约束，请使用下面的 SQL：

MySQL：
```
ALTER TABLE orders
DROP FORENGIN KEY orders
```

# SQL CHECK 约束


CHECK 约束用于限制列中的值的范围。

如果对单个列定义 CHECK 约束，那么该列只允许特定的值。

如果对一个表定义 CHECK 约束，那么此约束会基于行中其他列的值在特定的列中对值进行限制。

## CREATE TABLE 时的 SQL CHECK 约束
下面的 SQL 在 "Persons" 表创建时在 "P_Id" 列上创建 CHECK 约束。CHECK 约束规定 "P_Id" 列必须只包含大于 0 的整数。

MySQL：
```
CREATE TABLE persons
p_id int NOT NULL,
LastName varchar(255) NOT NULL,
FristName varchar(255),
Address varchar(255),
City varchar(255),
CHECK (P_Id>0)
```

## ALTER TABLE 时的 SQL CHECK 约束
当表已被创建时，如需在 "P_Id" 列创建 CHECK 约束，请使用下面的 SQL：

MySQL / SQL Server / Oracle / MS Access:
```
ALTER TABLE persons
ADD CHECK (P_Id>0)
```

## 撤销 CHECK 约束
如需撤销 CHECK 约束，请使用下面的 SQL：

MySQL：
```
ALTER TABLE persons
DROP CHECK persons
```

# SQL DEFAULT 约束
DEFAULT 约束用于向列中插入默认值。

如果没有规定其他的值，那么会将默认值添加到所有的新记录。

## CREATE TABLE 时的 SQL DEFAULT 约束
下面的 SQL 在 "Persons" 表创建时在 "City" 列上创建 DEFAULT 约束：

My SQL / SQL Server / Oracle / MS Access：
```
CREATE TABLE persons
(
p_id int NOT NULL,
LastName varchar（255）NOT NULL,
FirstName varchar(255),
Address varchar(255),
City varchar(255) DEFAULT 'shanghai'
)
```

## ALTER TABLE 时的 SQL DEFAULT 约束
当表已被创建时，如需在 "City" 列创建 DEFAULT 约束，请使用下面的 SQL：

MySQL：
```
ALTER TABLE persons
ALTER city SET DEFAULT 'shanghai'
```

## 撤销 DEFAULT 约束
如需撤销 DEFAULT 约束，请使用下面的 SQL：

MySQL：
```
ALTER TABLE persons
ALTER city DROP DEFAULT
```

## SQL CREATE INDEX 语句
CREATE INDEX 语句用于在表中创建索引。

在不读取整个表的情况下，索引使数据库应用程序可以更快地查找数据。

## 索引
您可以在表中创建索引，以便更加快速高效地查询数据。

用户无法看到索引，它们只能被用来加速搜索/查询。

**　注释：更新一个包含索引的表需要比更新一个没有索引的表花费更多的时间，这是由于索引本身也需要更新。因此，理想的做法是仅仅在常常被搜索的列（以及表）上面创建索引。

## SQL CREATE INDEX 语法
在表上创建一个简单的索引。允许使用重复的值：
```
CREATE INDEX index_name
ON table_name (column_name)
```

## SQL CREATE UNIQUE INDEX 语法
在表上创建一个唯一的索引。不允许使用重复的值：唯一的索引意味着两个行不能拥有相同的索引值。Creates a unique index on a table. Duplicate values are not allowed:
```
CREATE UNIQUE INDEX index_name
ON table_name (column_name)
```
** 注释：用于创建索引的语法在不同的数据库中不一样。因此，检查您的数据库中创建索引的语法。 

** 个人理解：索引就是增加一个排序规则，由原来的线性查找变为二分查找 **

## CREATE INDEX 实例


下面的 SQL 语句在 "Persons" 表的 "LastName" 列上创建一个名为 "PIndex" 的索引：
```
CREATE INDEX Pindex
ON psersons (LastName)
```
如果您希望索引不止一个列，您可以在括号中列出这些列的名称，用逗号隔开：
```
CREATE INDEX pindex
ON persons (LastName,FristName)
```

# SQL 撤销索引、撤销表以及撤销数据库
通过使用 DROP 语句，可以轻松地删除索引、表和数据库。

## DROP INDEX 语句
DROP INDEX 语句用于删除表中的索引。

## 用于 MySQL 的 DROP INDEX 语法：
```
ALTER TABLE table_name DROP INDEX index_name
```

## DROP TABLE 语句
DROP TABLE 语句用于删除表。
```
DROP TABLE table_name
```

## DROP DATABASE 语句
DROP DATABASE 语句用于删除数据库。
```
DROP DATABASE database_name
```

## TRUNCATE TABLE 语句
如果我们仅仅需要删除表内的数据，但并不删除表本身，那么我们该如何做呢？

请使用 TRUNCATE TABLE 语句：
```
TRUNCATE TABLE table_name
```

# ALTER TABLE 语句
ALTER TABLE 语句用于在已有的表中添加、删除或修改列。

## SQL ALTER TABLE 语法
如需在表中添加列，请使用下面的语法:
```
ALTER TABLE table_name
ADD column_name datatype
```
如需删除表中的列，请使用下面的语法（请注意，某些数据库系统不允许这种在数据库表中删除列的方式）：
```
ALTER TABLE table_name
DROP COLUMN column_name
```
要改变表中列的数据类型，请使用下面的语法：
My SQL / Oracle：
```
ALTER TABLE table_name
MODIFY COLUMN column_name datatype
```

## SQL ALTER TABLE 实例
请看 "Persons" 表：
![](img/55.png)
现在，我们想在 "Persons" 表中添加一个名为 "DateOfBirth" 的列。

我们使用下面的 SQL 语句：
```
ALTER TABLE persons
ADD dataofbirth data
```
请注意，新列 "DateOfBirth" 的类型是 date，可以存放日期。
现在，"Persons" 表将如下所示：
![](img/56.png)

## 改变数据类型实例
现在，我们想要改变 "Persons" 表中 "dataofbrith" 列的数据类型。

我们使用下面的 SQL 语句：
```
ALTER TABLE persons
ALTER COLUMN dataofbrith year
```
请注意，现在 "dateOfbirth" 列的类型是 year，可以存放 2 位或 4 位格式的年份。

## DROP COLUMN 实例
接下来，我们想要删除 "Person" 表中的 "DateOfBirth" 列。

我们使用下面的 SQL 语句：
```
ALTER TABLE persons
DROP COLUMN dataofbrith
```

# SQL AUTO INCREMENT 字段
Auto-increment 会在新记录插入表中时生成一个唯一的数字。
我们通常希望在每次插入新记录时，自动地创建主键字段的值。

我们可以在表中创建一个 auto-increment 字段。

## 用于 MySQL 的语法
下面的 SQL 语句把 "Persons" 表中的 "ID" 列定义为 auto-increment 主键字段：
```
CRATE TABLE persons
(
ID int NOT NULL ATUO_INCREMENT,
LastName varchar(255) NOT NULL,
FristName varchar(255),
Address varchar(255),
City varchar(255),
PRIMARY KEY (ID)
)
```
MySQL 使用 AUTO_INCREMENT 关键字来执行 auto-increment 任务。

默认地，AUTO_INCREMENT 的开始值是 1，每条新记录递增 1。

要让 AUTO_INCREMENT 序列以其他的值起始，请使用下面的 SQL 语法：

```
ALTER TABLE persons AUTO_INCREMENT=100
```
要在 "Persons" 表中插入新记录，我们不必为 "ID" 列规定值（会自动添加一个唯一的值）：
```
INSERT INTO persons (FirstName,LastName)
VALUES ('Lars','Monsen')
```
上面的 SQL 语句会在 "Persons" 表中插入一条新记录。"ID" 列会被赋予一个唯一的值。"FirstName" 列会被设置为 "Lars"，"LastName" 列会被设置为 "Monsen"。

# SQL 视图（Views）
视图是可视化的表。

本章讲解如何创建、更新和删除视图。
## SQL CREATE VIEW 语句
在 SQL 中，视图是基于 SQL 语句的结果集的可视化的表。

视图包含行和列，就像一个真实的表。视图中的字段就是来自一个或多个数据库中的真实的表中的字段。

您可以向视图添加 SQL 函数、WHERE 以及 JOIN 语句，也可以呈现数据，就像这些数据来自于某个单一的表一样。

## SQL CREATE VIEW 语法
```
CREATE VIEW view_name AS
SELECT column_name
FROM table_name
WHERE condition
```
** 注释：视图总是显示最新的数据！每当用户查询视图时，数据库引擎通过使用视图的 SQL 语句重建数据。
## SQL CREATE VIEW 实例
下面的视图是从websites中选出country为CN的数据，这个视图用下面的sql创建
```
CREATE VIEW webcn AS
SELECT id,name,url,country
FROM websites
WHERE country='CN';
```：
![](img/57.png)
我们可以像这样查询上面视图
```
SELECT * FROM webcn;
```
![](img/58.png)

## SQL 更新视图

### SQL CREATE OR REPLACE VIEW 语法
```
CREATE OR REPLACE VIEW view_name AS
SELECT column_name
FROM table_name
WHERE condition
```
现在想像webcn增加alexa字段
```
CREATE OR REPLACE VIEW webcn AS
SELECT id,name,url,alexa,country
FROM websites
WHERE country='CN'
```
![](img/59.png)

## SQL 撤销视图
您可以通过 DROP VIEW 命令来删除视图。
### sql撤销视图语法
```
DROP VIEW view_name;
```

# SQL Date 函数
## SQL 日期（Dates）
当我们处理日期时，最难的任务恐怕是确保所插入的日期的格式，与数据库中日期列的格式相匹配。

只要您的数据包含的只是日期部分，运行查询就不会出问题。但是，如果涉及时间部分，情况就有点复杂了。

在讨论日期查询的复杂性之前，我们先来看看最重要的内建日期处理函数。

## MySQL Date 函数
下面列出了 MySQL 中最重要的内建日期函数：

### NOW() 	返回当前的日期和时间
now 实例
```
SELECT NOW(),CURDATE(),CURTIME()
```
![](img/60.png)

表格中引用实例
```
CREATE TABLE orders
(
orderId int NOT NULL,
productName varchar(255) NOT NULL,
orderDate datetime NOT NULL DEFAULT NOW(),
PRIMARY KEY (orderId)
)
```
![](img/61.png)
请注意，OrderDate 列规定 NOW() 作为默认值。作为结果，当您向表中插入行时，当前日期和时间自动插入列中。

现在，我们想要在 "Orders" 表中插入一条记录：
```
INSERT INTO orders (productName)
VALUES ('webthreat');
SELECT * FROM orders;
```
![](img/62.png)
** 应用提示：创建时间可以用now记录 **

### CURDATE() 	返回当前的日期
同now();

### CURTIME() 	返回当前的时间
同now();

### DATE() 	提取日期或日期/时间表达式的日期部分
实例：
演示数据
![](img/63.png)
下面是 SELECT 语句：
```
SELECT productName,DATE(orderDate) AS orderDate
FROM orders
```
![](img/64.png)

### EXTRACT()
	EXTRACT() 函数用于返回日期/时间的单独部分，比如年、月、日、小时、分钟等等。
语法
```
EXTRACT(unit FROM data)
```
date 参数是合法的日期表达式。unit 参数可以是下列的值：
Unit 值
MICROSECOND
SECOND
MINUTE
HOUR
DAY
WEEK
MONTH
QUARTER
YEAR
SECOND_MICROSECOND
MINUTE_MICROSECOND
MINUTE_SECOND
HOUR_MICROSECOND
HOUR_SECOND
HOUR_MINUTE
DAY_MICROSECOND
DAY_SECOND
DAY_MINUTE
DAY_HOUR
YEAR_MONTH

实例：
演示数据
![](img/63.png)

下面是 SELECT 语句：
```
SELECT EXTRACT(YEAR FROM orderDate) AS year,
EXTRACT(MONTH FROM orderDate) AS month,
EXTRACT(DAY FROM orderDate) AS day
FROM orders
```
![](img/65.png)

### DATE_ADD() 	向日期添加指定的时间间隔

语法：
```
DATA_ADD (data,INTERVAL expr type)
```
date 参数是合法的日期表达式。expr 参数是您希望添加的时间间隔。
type 参数可以是下列值：
Type 值
MICROSECOND
SECOND
MINUTE
HOUR
DAY
WEEK
MONTH
QUARTER
YEAR
SECOND_MICROSECOND
MINUTE_MICROSECOND
MINUTE_SECOND
HOUR_MICROSECOND
HOUR_SECOND
HOUR_MINUTE
DAY_MICROSECOND
DAY_SECOND
DAY_MINUTE
DAY_HOUR
YEAR_MONTH

实例：
示例数据
![](img/66.png)
现在，我们想要向 "OrderDate" 添加 45 天，这样就可以找到付款日期。

我们使用下面的 SELECT 语句：
```
SELECT orderId,DATE_ADD(orderDate,INTERVAL 45 DAY)
FROM orders
```
![](img/67.png)

### DATE_SUB()
DATE_SUB() 函数从日期减去指定的时间间隔。
语法：
```
DATE_SUB(date,INTERVAL expr type)
```
date参数是合法的日期表达式，expr参数是您希望添加的时间间隔。
type 参数可以是下列值：
Type 值
MICROSECOND
SECOND
MINUTE
HOUR
DAY
WEEK
MONTH
QUARTER
YEAR
SECOND_MICROSECOND
MINUTE_MICROSECOND
MINUTE_SECOND
HOUR_MICROSECOND
HOUR_SECOND
HOUR_MINUTE
DAY_MICROSECOND
DAY_SECOND
DAY_MINUTE
DAY_HOUR
YEAR_MONTH

实例：
示例数据
![](img/66.png)
现在，我们想要向 "OrderDate" 减去 5 天。

我们使用下面的 SELECT 语句：
```
SELECT orderId,DATE_SUB(orderDate,INTERVAL 5 DAY) AS beforedata
FROM orders
```
![](img/68.png)

### DATEDIFF() 	返回两个日期之间的天数
语法：
```
DATEDIFF(date1,date2)
```
date1 和 date2 参数是合法的日期或日期/时间表达式。

** 注释：只有值的日期部分参与计算。
实例：
下面是SELECT语句：
```
SELECT DATEDIFF('2016-12-11','2016-12-10') AS diff
```
![](img/69.png)

### DATE_FORMAT() 	用不同的格式显示日期/时间
语法：
```
DATE_FROMAT(date,format)
```
date 参数是合法的日期。format 规定日期/时间的输出格式。

可以使用的格式有：
格式 	描述
%a 	缩写星期名
%b 	缩写月名
%c 	月，数值
%D 	带有英文前缀的月中的天
%d 	月的天，数值（00-31）
%e 	月的天，数值（0-31）
%f 	微秒
%H 	小时（00-23）
%h 	小时（01-12）
%I 	小时（01-12）
%i 	分钟，数值（00-59）
%j 	年的天（001-366）
%k 	小时（0-23）
%l 	小时（1-12）
%M 	月名
%m 	月，数值（00-12）
%p 	AM 或 PM
%r 	时间，12-小时（hh:mm:ss AM 或 PM）
%S 	秒（00-59）
%s 	秒（00-59）
%T 	时间, 24-小时（hh:mm:ss）
%U 	周（00-53）星期日是一周的第一天
%u 	周（00-53）星期一是一周的第一天
%V 	周（01-53）星期日是一周的第一天，与 %X 使用
%v 	周（01-53）星期一是一周的第一天，与 %x 使用
%W 	星期名
%w 	周的天（0=星期日, 6=星期六）
%X 	年，其中的星期日是周的第一天，4 位，与 %V 使用
%x 	年，其中的星期一是周的第一天，4 位，与 %v 使用
%Y 	年，4 位
%y 	年，2 位

实例

下面的脚本使用 DATE_FORMAT() 函数来显示不同的格式。我们使用 NOW() 来获得当前的日期/时间：
```
SELECT DATE_FORMAT(NOW(),'%b %d %Y %h:%i %p') AS date1,
DATE_FORMAT(NOW(),'%m-%d-%Y') AS date2,
DATE_FORMAT(NOW(),'%d %b %y') AS date3,
DATE_FORMAT(NOW(),'%d %b %Y %T:%f') AS date4
```
![](img/70.png)

## SQL Date 数据类型
MySQL 使用下列数据类型在数据库中存储日期或日期/时间值：

    DATE - 格式：YYYY-MM-DD
    DATETIME - 格式：YYYY-MM-DD HH:MM:SS
    TIMESTAMP - 格式：YYYY-MM-DD HH:MM:SS
    YEAR - 格式：YYYY 或 YY
** 注释：当您在数据库中创建一个新表时，需要为列选择数据类型！

## SQL 日期处理
如果不涉及时间部分，那么我们可以轻松地比较两个日期！

假设我们有如下的 "Orders" 表：
![](img/71.png)
现在，我们希望从上表中选取 OrderDate 为 "2008-11-11" 的记录。

我们使用下面的 SELECT 语句：
```
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```
结果集如下所示：
![](img/72.png)
现在，假设 "Orders" 表如下所示（请注意 "OrderDate" 列中的时间部分）：
![](img/73.png)
如果我们使用和上面一样的 SELECT 语句
```
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```
那么我们将得不到结果！这是由于该查询的日期不含有时间部分。

提示：如果您希望使查询简单且更易维护，那么请不要在日期中使用时间部分！

# SQL NULL 值
NULL 值代表遗漏的未知数据。

默认地，表的列可以存放 NULL 值。

本章讲解 IS NULL 和 IS NOT NULL 操作符。
如果表中的某个列是可选的，那么我们可以在不向该列添加值的情况下插入新记录或更新已有的记录。这意味着该字段将以 NULL 值保存。

NULL 值的处理方式与其他值不同。

NULL 用作未知的或不适用的值的占位符。

** Note注释：无法比较 NULL 和 0；它们是不等价的。
## SQL 的 NULL 值处理

请看下面的 "Persons" 表：
![](img/74.png)
假如 "Persons" 表中的 "Address" 列是可选的。这意味着如果在 "Address" 列插入一条不带值的记录，"Address" 列会使用 NULL 值保存。

那么我们如何测试 NULL 值呢？

无法使用比较运算符来测试 NULL 值，比如 =、< 或 <>。

我们必须使用 IS NULL 和 IS NOT NULL 操作符。

## SQL IS NULL
我们如何仅仅选取在 "Address" 列中带有 NULL 值的记录呢？

我们必须使用 IS NULL 操作符：
```
SELECT * FROM person
WHERE addRess IS NULL
```
结果集如下所示：
![](img/75.png)
** 提示：请始终使用 IS NULL 来查找 NULL 值。

## SQL IS NOT NULL
我们如何仅仅选取在 "Address" 列中不带有 NULL 值的记录呢？

我们必须使用 IS NOT NULL 操作符：
```
SELECT * FROM person
WHERE addRess IS NOT NULL
```
![](img/76.png)

# SQL NULL 函数
SQL ISNULL()、NVL()、IFNULL() 和 COALESCE() 函数

请看下面的 "Products" 表：
![](img/77.png)
假如 "UnitsOnOrder" 是可选的，而且可以包含 NULL 值。

我们使用下面的 SELECT 语句：
```
SELECT ProductName,UnitPrice*(UnitsInStock+UnitsOnOrder)
FROM Products
```
在上面的实例中，如果有 "UnitsOnOrder" 值是 NULL，那么结果是 NULL。

微软的 ISNULL() 函数用于规定如何处理 NULL 值。

NVL()、IFNULL() 和 COALESCE() 函数也可以达到相同的结果。

在这里，我们希望 NULL 值为 0。

下面，如果 "UnitsOnOrder" 是 NULL，则不会影响计算，因为如果值是 NULL 则 ISNULL() 返回 0：

MySQL

MySQL 也拥有类似 ISNULL() 的函数。不过它的工作方式与微软的 ISNULL() 函数有点不同。

在 MySQL 中，我们可以使用 IFNULL() 函数，如下所示：
```
SELECT ProductName,UnitPrice*(UnitsInStock+IFNULL(UnitsOnOrder,0))
FROM Products
```
或者我们可以使用 COALESCE() 函数，如下所示：
```
SELECT ProductName,UnitPrice*(UnitsInStock+COALESCE(UnitsOnOrder,0))
FROM Products
```

# SQL 通用数据类型
数据库表中的每个列都要求有名称和数据类型。Each column in a database table is required to have a name and a data type.

SQL 开发人员必须在创建 SQL 表时决定表中的每个列将要存储的数据的类型。数据类型是一个标签，是便于 SQL 了解每个列期望存储什么类型的数据的指南，它也标识了 SQL 如何与存储的数据进行交互。

下面的表格列出了 SQL 中通用的数据类型：
数据类型 	描述
CHARACTER(n) 	字符/字符串。固定长度 n。
VARCHAR(n) 或
CHARACTER VARYING(n) 	字符/字符串。可变长度。最大长度 n。
BINARY(n) 	二进制串。固定长度 n。
BOOLEAN 	存储 TRUE 或 FALSE 值
VARBINARY(n) 或
BINARY VARYING(n) 	二进制串。可变长度。最大长度 n。
INTEGER(p) 	整数值（没有小数点）。精度 p。
SMALLINT 	整数值（没有小数点）。精度 5。
INTEGER 	整数值（没有小数点）。精度 10。
BIGINT 	整数值（没有小数点）。精度 19。
DECIMAL(p,s) 	精确数值，精度 p，小数点后位数 s。例如：decimal(5,2) 是一个小数点前有 3 位数小数点后有 2 位数的数字。
NUMERIC(p,s) 	精确数值，精度 p，小数点后位数 s。（与 DECIMAL 相同）
FLOAT(p) 	近似数值，尾数精度 p。一个采用以 10 为基数的指数计数法的浮点数。该类型的 size 参数由一个指定最小精度的单一数字组成。
REAL 	近似数值，尾数精度 7。
FLOAT 	近似数值，尾数精度 16。
DOUBLE PRECISION 	近似数值，尾数精度 16。
DATE 	存储年、月、日的值。
TIME 	存储小时、分、秒的值。
TIMESTAMP 	存储年、月、日、小时、分、秒的值。
INTERVAL 	由一些整数字段组成，代表一段时间，取决于区间的类型。
ARRAY 	元素的固定长度的有序集合
MULTISET 	元素的可变长度的无序集合
XML 	存储 XML 数据

## SQL 数据类型快速参考手册


然而，不同的数据库对数据类型定义提供不同的选择。

下面的表格显示了各种不同的数据库平台上一些数据类型的通用名称：
![](img/78.png)

** 注释：在不同的数据库中，同一种数据类型可能有不同的名称。即使名称相同，尺寸和其他细节也可能不同！ 请总是检查文档！

# SQL 用于各种数据库的数据类型
Microsoft Access、MySQL 和 SQL Server 所使用的数据类型和范围。

## MySQL 数据类型

在 MySQL 中，有三种主要的类型：Text（文本）、Number（数字）和 Date/Time（日期/时间）类型。

### Text 类型：
![](img/79.png)

### Number 类型：
![](img/80.png)

*这些整数类型拥有额外的选项 UNSIGNED。通常，整数可以是负数或正数。如果添加 UNSIGNED 属性，那么范围将从 0 开始，而不是某个负数。

### Date 类型：
![](img/81.png)
*即便 DATETIME 和 TIMESTAMP 返回相同的格式，它们的工作方式很不同。在 INSERT 或 UPDATE 查询中，TIMESTAMP 自动把自身设置为当前的日期和时间。TIMESTAMP 也接受不同的格式，比如 YYYYMMDDHHMMSS、YYMMDDHHMMSS、YYYYMMDD 或 YYMMDD。

# SQL 函数
SQL 拥有很多可用于计数和计算的内建函数。

## SQL Aggregate 函数
SQL Aggregate 函数计算从列中取得的值，返回一个单一的值。

有用的 Aggregate 函数：

    AVG() - 返回平均值
    COUNT() - 返回行数
    FIRST() - 返回第一个记录的值
    LAST() - 返回最后一个记录的值
    MAX() - 返回最大值
    MIN() - 返回最小值
    SUM() - 返回总和

## SQL Scalar 函数
SQL Scalar 函数基于输入值，返回一个单一的值。

有用的 Scalar 函数：

    UCASE() - 将某个字段转换为大写
    LCASE() - 将某个字段转换为小写
    MID() - 从某个文本字段提取字符
    LEN() - 返回某个文本字段的长度
    ROUND() - 对某个数值字段进行指定小数位数的四舍五入
    NOW() - 返回当前的系统日期和时间
    FORMAT() - 格式化某个字段的显示方式

# AVG() 函数
AVG() 函数返回数值列的平均值。

## AVG() 函数返回数值列的平均值。
```
SELECT AVG(column_name) FROM table_name
```

## 演示数据库
![](img/82.png)

## SQL AVG() 实例
下面的 SQL 语句从 "access_log" 表的 "count" 列获取平均值：
```
SELECT AVG(count) AS avg FROM access_log
```
![](img/83.png)
下面的 SQL 语句选择访问量高于平均访问量的 "site_id" 和 "count"：
```
SELECT site_id,count
FROM access_log
WHERE count>(SELECT AVG(count) FROM access_log)
```
![](img/84.png)

# SQL COUNT() 函数
COUNT() 函数返回匹配指定条件的行数。

## SQL COUNT(column_name) 语法
COUNT(column_name) 函数返回指定列的值的数目（NULL 不计入）：
```
SELECT COUNT(column_name)FROM table_name;
```

## SQL COUNT(*) 语法
COUNT(*) 函数返回表中的记录数：
```
SELECT COUNT(*) FORM table_name;
```

## SQL COUNT(DISTINCT column_name) 语法
COUNT(DISTINCT column_name) 函数返回指定列的不同值的数目：
```
SELECT COUNT(DISTINCT column_name)FROM table_name;
```
** 注释：COUNT(DISTINCT) 适用于 ORACLE 和 Microsoft SQL Server，但是无法用于 Microsoft Access。

## SQL COUNT(column_name) 实例
下面的 SQL 语句计算 "access_log" 表中 "site_id"=3 的总访问量：
```
SELECT COUNT(count) as nums
FROM access_log
WHERE site_id=3
```
![](img/85.png)

## SQL COUNT(*) 实例
下面的 SQL 语句计算 "access_log" 表中总记录数：
```
SELECT COUNT(*) AS nums
FROM access_log
```
![](img/86.png)


## SQL COUNT(DISTINCT column_name) 实例
下面的 SQL 语句计算 "access_log" 表中不同 site_id 的记录数：
```
SELECT COUNT(DISTINCT site_id) AS nums
FROM access_log
```
![](img/87.png)

# SQL FIRST() 函数
FIRST() 函数返回指定的列中第一个记录的值。

## MySQL 语法
```
SELECT column_name FROM table_name
ORDER BY column_name ASC
LIMIT 1;
```

实例：
```
SELECT name AS FristSite
FROM websites
ORDER BY name ASC
LIMIT 1
```
![](img/88.png)

# SQL LAST() 函数
LAST() 函数返回指定的列中最后一个记录的值。

MySQL 语法
```
SELECT column_name FROM table_name
ORDER BY column_name DESC
LIMIT 1;
```
实例
```
SELECT name FROM websites
ORDER BY name DESC
LIMIT 1
```
![](img/89.png)

# MAX() 函数
MAX() 函数返回指定列的最大值。

## MAX() 函数返回指定列的最大值。
```
SELECT MAX (column_name) FROM table_name
```

## SQL MAX() 实例
下面的 SQL 语句从 "Websites" 表的 "alexa" 列获取最大值：
```
SELECT MAX(alexa) FROM websites
```
![](img/90.png)

# MIN() 函数
MIN() 函数返回指定列的最小值。

## MIN() 语法
```
SELECT MIN(column_name) FROM table_name
```

## MIN() 语法
下面的 SQL 语句从 "Websites" 表的 "alexa" 列获取最小值：
```
SELECT MIN(alexa) FROM websites
```
![](img/91.png)

# SUM() 函数

SUM() 函数返回数值列的总数。

## SQL SUM() 语法
```
SELECT SUM(column_name) FROM table_name
```

## 实例：
```
SELECT SUM(count) FROM access_log
```
![](img/92.png)


# SQL GROUP BY 语句
GROUP BY 语句可结合一些聚合函数来使用
GROUP BY 语句用于结合聚合函数，根据一个或多个列对结果集进行分组。

## SQL GROUP BY 语法
```
SELECT column_name ,aggretate_function(column_name)
FROM  table_name
WHERE column_name poerator value
GROUP BY column
```

## GROUP BY 简单应用
统计 access_log 各个 site_id 的访问量：

实例：
```
SELECT site_id, SUM(count) AS nums
FROM access_log 
GROUP BY site_id
```
![](img/93.png)

## SQL GROUP BY 多表连接
实例：
```
SELECT websites.name,count(access_log.aid) 
AS nums
FROM access_log 
LEFT JOIN websites
ON access_log.site_id=websites.id
GROUP BY websites.name
```
![](img/94.png)

# SQL HAVING 子句
在 SQL 中增加 HAVING 子句原因是，WHERE 关键字无法与聚合函数一起使用。

HAVING 子句可以让我们筛选分组后的各组数据。
## SQL HAVING 语法
```
SELECT column_name, aggregate_function(column_name)
FROM table_name
WHERE column_name operator value
GROUP BY column_name
HAVING aggregate_function(column_name) operator value;
```

## 演示数据库
![](img/95.png)
![](img/96.png)

## SQL HAVING 实例
现在我们想要查找总访问量大于 200 的网站。

我们使用下面的 SQL 语句：
```
SELECT websites.name,websites.url,SUM(access_log.count)
AS nums
FROM (access_log INNER JOIN websites
ON access_log.site_id=websites.id)
GROUP BY websites.name
HAVING SUM(access_log.count) > 200
```
![](img/97.png)
现在我们想要查找总访问量大于 200 的网站，并且 alexa 排名小于 200。

我们在 SQL 语句中增加一个普通的 WHERE 子句：
```
SELECT websites.name,SUM(access_log.count) AS nums
FROM websites 
INNER JOIN access_log
ON websites.id=access_log.site_id
WHERE websites.alexa<200
GROUP BY websites.name
HAVING SUM(access_log.count)>200;
```
![](img/98.png)

# UCASE() 函数
UCASE() 函数把字段的值转换为大写。

## SQL UCASE() 语法
```
SELECT UCASE(column_name) FROM table_name;
```

## SQL UCASE() 实例
下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "url" 列，并把 "name" 列的值转换为大写：

```
SELECT UCASE(name) AS site_title,url
FROM websites;
```
![](img/99.png)

# LCASE() 函数
LCASE() 函数把字段的值转换为小写。
## SQL LCASE() 语法
```
SELECT LCASE(column_name) FROM table_name
```

## SQL LCASE() 实例
下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "url" 列，并把 "name" 列的值转换为小写：
```
SELECT LCASE(name) AS site_title,url FROM websites;
```
![](img/100.png)

# SQL MID() 函数
MID() 函数用于从文本字段中提取字符。

## SQL MID() 语法
```
SELECT MID(column_name,start[,length]) FORM table_name;
```

参数	  描述
column_name	必需。要提取字符的字段。
start	必需。规定开始位置（起始值是 1）。
length	可选。要返回的字符数。如果省略，则 MID() 函数返回剩余文本。

## SQL MID() 实例
下面的 SQL 语句从 "Websites" 表的 "name" 列中提取前 4 个字符：
```
SELECT MID(name,1,4) AS shortTitle FROM websites
```
![](img/101.png)

# LEN() 函数
LEN() 函数返回文本字段中值的长度。

## SQL LEN() 语法
```
SELECT LEN(column_name) FROM table_name
```

** MySQL 中函数为 LENGTH():**
```
SELECT LENGTH(column_name) FORM table_name;
```

## SQL LEN() 实例
下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "url" 列中值的长度：
```
SELECT name,LENGTH(url) AS urlLength FROM websites
```
![](img/102.png)

# ROUND() 函数
ROUND() 函数用于把数值字段舍入为指定的小数位数。

## SQL ROUND() 语法
```
SELECT ROUND(column_name,decimals) FROM table_name
```


参数	描述
column_name	必需。要舍入的字段。
decimals	必需。规定要返回的小数位数。

## SQL ROUND() 实例

ROUND(X)： 返回参数X的四舍五入的一个整数。
```
SELECT ROUND(-1.44) AS round
UNION ALL
SELECT ROUND(-1.58)
UNION ALL
SELECT ROUND(1.58)
```
![](img/103.png)

ROUND(X,D)： 返回参数X的四舍五入的有D为小数的一个数字。如果D为0，结果将没有小数点或小数部分。
```
SELECT ROUND(1.298,1) AS ROUd
UNION ALL
SELECT ROUND(1.298,0)
```
![](img/104.png)

# NOW() 函数
NOW() 函数返回当前系统的日期和时间。

## SQL NOW() 语法
```
SELECT NOW() FROM table_name
```

## SQL NOW() 实例
下面的 SQL 语句从 "Websites" 表中选取 name，url，及当天日期：
```
SELECT name ,url ,NOW() AS date
FROM websites
```
![](img/105.png)

# FORMAT() 函数
FORMAT() 函数用于对字段的显示进行格式化。

## SQL FORMAT() 语法
```
SELECT FORMAT(column,format) FROM table_name;
```
参数	描述
column_name	必需。要格式化的字段。
format	必需。规定格式。

## SQL FORMAT() 实例
下面的 SQL 语句从 "Websites" 表中选取 name, url 以及格式化为 YYYY-MM-DD 的日期：
```
SELECT name,url,DATE_FORMAT(NOW(),'%Y-%m-%d') AS date
FROM websites
```
![](img/106.png)

# SQL 快速参考
![](img/107.png)

# SQL 主机
如果您想要您的网站存储数据在数据库并从数据库显示数据，您的 Web 服务器必须能使用 SQL 语言访问数据库系统。
如果您的 Web 服务器托管在互联网服务提供商（ISP，全称 Internet Service Provider），您必须寻找 SQL 主机计划。
最常见的 SQL 主机数据库是 MySQL、MS SQL Server 和 MS Access。
您可以在 Windows 和 Linux/UNIX 操作系统上运行 SQL 主机数据库。
下面是操作系统上对应运行的数据库系统的概览。
## MS SQL Server
在 Windows 和 Linux 操作系统上运行。
## MySQL
在 Windows, Mac OS X 和 Linux/UNIX 操作系统上运行。
## MS Access（只建议用于小型网站）
只在 Windows OS 上运行。

## SQL 总结
本 SQL 教程已经向您讲解了用来访问和处理数据库系统的标准计算机语言。
我们已经学习了如何使用 SQL 在数据库中执行查询、获取数据、插入新的记录、删除记录以及更新记录。
我们已经学习了如何通过 SQL 创建数据库、表、索引，以及如何撤销它们。
我们已经学习了 SQL 中最重要的 Aggregate 函数。
SQL 是一种与数据库系统协同工作的标准语言，这些数据库系统包括 MS SQL Server、IBM DB2、Oracle、MySQL 和 MS Access 等等。