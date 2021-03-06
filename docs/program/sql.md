### 索引文件失效情况

![mysql-index](..\images\mysql-index.png)

### Mysql

名词解释：聚簇索引/非聚簇索引、回表、索引覆盖、最左匹配、索引下推

日志：binlog、redolog、undolog、慢日志和错误日志

explain、hyperloglog

MVCC

#### 查找mysql存储过程的错误方法

通过select方式打印信息

 -- SELECT @sqlstr; 

调用存储过程的方法：call 存储过程名称(传入的参数)     call proc_test("绝心是凉白开","www.found5.com")

**mysql中“1271 - Illegal mix of collations for operation 'like'”错误解决方法**

将sql语句改成like binary '%中文%'后