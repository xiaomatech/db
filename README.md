# db配置
- mysql
```
  yum install -y gperftools-libs Percona-Server-server-57 Percona-Server-tokudb-57 percona-toolkit percona-xtrabackup
```
- mongodb
```
  yum install -y gperftools-libs Percona-Server-MongoDB-server Percona-Server-MongoDB-mongos Percona-Server-MongoDB-tools
```

- 大表发布 gh-ost
```
    https://github.com/github/gh-ost/blob/master/doc/cheatsheet.md
    https://github.com/github/gh-ost/releases/download/v1.0.46/gh-ost-1.0.46-1.x86_64.rpm
```

- 慢日志分析
```
   慢日志入库 (pt-query-digest/anemometer)
```

- mysql 备份
```
  https://github.com/ShahriyarR/MySQL-AutoXtraBackup
  https://github.com/dotmanila/pyxbackup
  https://github.com/lustlost/ubackup
```

- SQL审核 发布 
```
  Inception
  https://github.com/cookieY/Yearning
```

- dbproxy

```
    https://github.com/Meituan-Dianping/DBProxy
    
    DBProxy是由美团点评公司技术工程部DBA团队（北京）开发维护的一个基于MySQL协议的数据中间层。它在奇虎360公司开源的Atlas基础上，修改了部分bug，并且添加了很多特性。目前DBProxy在美团点评广泛应用，包括美团支付、酒店旅游、外卖、团购等产品线，公司内部对DBProxy的开发全面转到github上，开源和内部使用保持一致。目前只支持MySQL（Percona）5.5和5.6。
    
    主要功能：
    
    读写分离
    从库负载均衡
    IP过滤
    分表
    DBA可平滑上下线DB
    自动摘除宕机的DB
    监控信息完备
    SQL过滤
    从库流量配置
    二、DBProxy相对于奇虎360公司开源Atlas的改进
    
    修改了部分bug并且新增了一些feature，详见release notes
    提供了丰富的监控信息，大量参数可配置化并且支持动态修改
    对原有的诸如日志等模块进行了优化，性能提升明显
    开源版本即为目前美团点评内部使用版本，并将一直对源码及其文档进行维护
    
```

- SQLAdvisor 输入SQL，输出索引优化建议
```
    https://github.com/Meituan-Dianping/SQLAdvisor/blob/master/doc/THEORY_PRACTICES.md
    
    wget https://raw.githubusercontent.com/xiaomatech/db/master/libsqlparser.so -O /usr/lib64/libsqlparser-debug.so
    wget https://raw.githubusercontent.com/xiaomatech/db/master/sqladvisor -O /usr/sbin/sqladvisor
    chmod a+x /usr/sbin/sqladvisor
    
    sqladvisor -h xx  -P xx  -u xx -p 'xx' -d xx -q "sql" -v 1
    
    echo '
    [sqladvisor]
    username=xx
    password=xx
    host=xx
    port=xx
    dbname=xx
    sqls=sql1;sql2;sql3....
    '>sql.cnf
    
    sqladvisor -f sql.cnf  -v 1
    
    
```
