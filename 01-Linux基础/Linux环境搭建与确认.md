# Linux 环境搭建与确认

## 学习目标
搭建并确认 Linux 实验环境可用。

## 实际操作
- 安装 VMware Workstation
- 安装 Ubuntu Server 24.04.4 LTS（2核 / 6GB / 40GB，NAT 网络）
- 启用 SSH 远程登录

## 验证结果
- 系统：Ubuntu 24.04.4 LTS（内核 6.8.0-139）
- IP：192.168.60.128（DHCP 动态）
- 网关：192.168.60.2
- Windows ping 虚拟机：0% 丢包
- SSH 远程登录：成功

## 遇到的问题
- Windows ping 不通虚拟机 → 排查后确认是深信服 VPN 服务干扰 VMware 虚拟网络 → 处理后恢复
- VMnet8 网卡偶发 169.254（未拿到地址）→ 禁用/启用网卡恢复

## 总结
环境是否正常 = 四块检查：虚拟机、系统、网络、SSH，全绿即正常。
