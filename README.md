# castToOracle
mysql脚本转Oracle
Mysql 格式：
Replace Into tableName (col,col,col) Values (v1, v2, v3);

生成的Oracle：
Delete from table where id = XXX;
Insert into tableName (col,col,col) Values (v1, v2, v3);

如果字段超长，会自动生成存储过程
declare XXX clob  := '';
Begin
 Delete from table where id = XXX;
Insert into tableName (col,col,col) Values (v1, XXX, v3);
END
/
