\# GitHub 环境配置与排错记录



\## 学习目标

配置 Git 并 clone GitHub 仓库到本地



\## 实际操作

1\. 安装 Git for Windows

2\. 配置 user.name / user.email

3\. git clone 我的仓库



\## 现象

clone 报错：SSL certificate problem: unable to get local issuer certificate



\## 排查过程

\- 先查 git config --global --list → 配置干净

\- 查系统代理 → 无代理

\- 查系统时间 → 正确

\- 最后发现：开着 Watt Toolkit 加速器



\## 原因

加速器拦截 HTTPS 并替换证书，浏览器信任它，Git 不信任 → SSL 验证失败



\## 处理

git config --global http.sslVerify false（跳过证书验证，学习环境可用）



\## 验证

重新 clone 成功，README.md 和 01-Linux基础 已下载到本地



