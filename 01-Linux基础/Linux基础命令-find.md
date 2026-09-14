\# Linux 基础命令 - find 实操记录



\## 任务目的

学会用 find 在 Linux 文件系统中查找文件，理解运维中"找文件"的基本方式。



\## 使用的命令

\- find \~ -name "mytest.txt"   # 在家目录按名字找文件

\- find / -name "app.log"      # 从根目录全盘搜索（不存在）

\- find / -name "passwd"       # 验证 find 能否深入系统目录



\## 实际操作与输出

1\. find \~ -name "mytest.txt"

&#x20;  → /home/naqin/mytest.txt   （找到，返回完整路径）



2\. find \~ -name "app.log"

&#x20;  → 无输出                     （家目录里没有这个文件）



3\. find / -name "app.log"

&#x20;  → 大量 Permission denied    （没权限进的目录）

&#x20;  → 最终没找到



4\. find / -name "passwd"

&#x20;  → /etc/passwd               （系统文件被找到）



\## 遇到的问题 / 排查过程

问题：find / 出现一堆 Permission denied，我一度以为这是"没找到"的意思。



排查：

\- 用 ls /root 测试 → Permission denied

\- 发现 /root 是 root 用户专属目录，普通用户无权进入

\- find / -name "passwd" 能搜到 /etc/passwd，证明 find 会深入所有能进的目录



\## 结论（我的理解）

\- Permission denied = 没权限查看该目录，不代表里面没有

\- 无输出 = 能访问的所有目录里都没有，才是真的没有



\## 企业实际用途

运维在服务器上找配置文件、日志文件时用 find；

遇到 Permission denied 要能区分"没权限"和"真没有"，避免误判。



