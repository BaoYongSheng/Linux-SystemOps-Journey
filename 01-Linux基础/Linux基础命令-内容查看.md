\# Linux 基础命令 - 内容查看（cat / less / tail / grep）



\## 任务目的

学会查看文件内容的 4 个基本命令，理解各自适用场景。



\## 命令一览

\- cat 文件：显示全部内容（适合小文件）

\- less 文件：分页查看（适合大文件），空格下翻、b 上翻、q 退出

\- tail 文件：看末尾 10 行；tail -n N 文件：看末尾 N 行（日志最常用）

\- grep 关键字 文件：只显示包含关键字的行（排错最常用）



\## 实际操作与输出

1\. cat /etc/hostname

&#x20;  → ubuntu-server（主机名）

2\. cat /etc/os-release

&#x20;  → PRETTY\_NAME="Ubuntu 24.04.4 LTS"（系统版本）

3\. less /etc/services

&#x20;  → 分页查看；空格翻页、b 回翻、q 退出；

&#x20;  底部状态：开头 ":" 、中间百分比、末尾 "(END)"

4\. tail /etc/services

&#x20;  → 末尾 10 行；tail -n 3 → 最后 3 行

5\. grep ssh /etc/services

&#x20;  → ssh 22/tcp # SSH Remote Login Protocol



\## 遇到的问题（排错过程）

问题：grep ssh /etc/vices 报错 "No such file or directory"

排查：

\- 文件明明存在（之前 cat/less/tail 都成功过）

\- 对比命令与正确路径，发现拼写少打了 serv：/etc/vices → /etc/services

修复：重新输入 grep ssh /etc/services

验证：成功输出 ssh 22/tcp



\## 我的理解

\- cat 全输出（看小文件）

\- less 翻页（看大文件）

\- tail 看尾巴（看日志最新）

\- grep 筛关键字（从海量信息捞证据）

\- 排错首选 grep：精准；cat 全量太杂乱



\## 企业实际用途

\- 看配置：cat

\- 看大文件/文档：less

\- 看日志最新：tail

\- 日志/配置里找关键字：grep

\- 经验：终端操作必须英文输入法，否则按键/命令被输入法拦截



