# Tactical Fuzzing  -  SQLi

## SQL注入

核心思想：页面看起来是否需要调用存储的数据？

存在一些SQLi polyglots，即（Mathias Karlsson）;

``
SLEEP（1）/ *'或SLEEP（1）或'“或SLEEP（1）或”* /
``

在单引号上下文中工作，在双引号上下文中工作，在“直接查询”上下文中工作！

您还可以利用Seclists的大型模糊列表数据库（https://github.com/danielmiessler/SecLists）

##￼￼ SQL注射观察
盲目占主导地位，基于错误的可能性极小。

``
'％2Bbenchmark（3200，SHA1（1））％2B'
``


``
'+ BENCHMARK（40000000，SHA1（1337））+'
``

SQLMap是王道！
- 使用-l解析Burp日志文件。
- 将篡改脚本用于黑名单。
-  SQLiPy Burp插件很适合快速检测SQLmap。
Web服务中有大量注入！

## 最佳SQL注入资源

-  MySQL：
  -  [PentestMonkey的mySQL注入备忘单]（http://pentestmonkey.net/cheat-sheet/sql-injection/mysql-sql-injection-cheat-sheet）
  -  [Reiners mySQL注入Filter Evasion Cheatsheet]（https://websec.wordpress.com/2010/12/04/sqli-filter-evasion-cheat-sheet-mysql/）
-  MSQQL：
  -  [EvilSQL的错误/联盟/盲人MSSQL备忘单]（http://evilsql.com/main/page2.php）
  -  [PentestMonkey的MSSQL SQLi注入备忘单]（http://pentestmonkey.net/cheat-sheet/sql-injection/mssql-sql-injection-cheat-sheet）
-  ORACLE：
  -  [PentestMonkey的Oracle SQLi Cheatsheet]（http://pentestmonkey.net/cheat-sheet/sql-injection/oracle-sql-injection-cheat-sheet）
-  POSTGRESQL：
  -  [PentestMonkey的Postgres SQLi Cheatsheet]（http://pentestmonkey.net/cheat-sheet/sql-injection/postgres-sql-injection-cheat-sheet）
- 其他
  -  [访问SQLi Cheatsheet]（http://nibblesec.org/files/MSAccessSQLi/MSAccessSQLi.html）
  -  [PentestMonkey的Ingres SQL注入备忘单]（http://pentestmonkey.net/cheat-sheet/sql-injection/ingres-sql-injection-cheat-sheet）
  -  [Pentestmonkey的DB2 SQL注入备忘单]（http://pentestmonkey.net/cheat-sheet/sql-injection/db2-sql-injection-cheat-sheet）
  -  [Pentestmonkey的Informix SQL注入备忘单]（http://pentestmonkey.net/cheat-sheet/sql-injection/informix-sql-injection-cheat-sheet）
  -  [SQLite3注入备忘单]（https://sites.google.com/site/0x7674/home/sqlite3injectioncheatsheet）
  -  [Ruby on Rails（Active Record）SQL注入指南]（http://rails-sqli.org/）
