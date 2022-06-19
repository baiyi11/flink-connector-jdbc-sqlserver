# SQLServer SQL Connector

## En
The SQLServer SQL connector allows for reading data from and writing data into SQLServer.

1. Download the source code of the corresponding Flink version.

2. Choose the corresponding flink-connector-jdbc-sqlserver version and rename the flink-connector-jdbc.

3. Overwrite  ./flink/flink-connectors/flink-connector-jdbc directory.

4. Finally package.



## 中文
SQLServer SQL 连接器允许从SQLServer读取数据和将数据写入SQLServer。

1.下载相应flink版本源码。

2.选择相应flink-connector-jdbc-sqlserver版本并重命名flink-connector-jdbc。

3.覆盖./flink/flink-connctors/flink-connector-jdbc文件目录。

4.最后打包。

```
CREATE TABLE sc_goodsinfo(                                                
    timeid DATE,                            
    sku_id VARCHAR,                             
    sku_name VARCHAR,                                      
    sku_amt DECIMAL(18,2),                                   
    PRIMARY KEY (timeid,sku_id) NOT ENFORCED 
) WITH (                               
    'connector' = 'jdbc', 
    'driver' = 'com.microsoft.sqlserver.jdbc.SQLServerDriver',           
    'url' = 'jdbc:sqlserver://172.16.2.61:1433;DatabaseName=jh_app',                 
    'table-name'='sc_f_pay_goodsinfo',       
    'username' = '127.0.0.1',
    'password' = '123456'
    )          
