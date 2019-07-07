# Linux指令篇



## 1.如何输出指定进程(假设名为test)的Pid

ps -ef|grep 'test'|grep -v 'grep'|awk '{print $2}'|xargs kill -9

2.根据mysql db连接导出文件，统计连接数最多的ip

文件格式示例:

```
| 1139941234 | writeuser | 100.107.172.11:35124  | db_auto_schedule_sys      | Sleep   |       9 |   
| 1139941236 | writeuser | 100.107.172.11:35164  | db_auto_schedule_sys      | Sleep   |       9 |   
| 1139941239 | writeuser | 100.107.172.11:35181  | db_auto_schedule_sys      | Sleep   |       9 |   

```

less  connect.log |cut -d '|' -f 4|cut -d ':' -f 1|uniq -c|sort -n |tail