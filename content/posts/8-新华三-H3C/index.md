---
title: 新华三-H3C
date: 2026-06-04
cover:
    image: ""
    caption: "" # 图片下方的说明
    hiddenInSingle: true            # 是否只在列表页显示，而在文章页内隐

categories:
  - 企业网络
tags:
  - H3C
---

企业网络设备厂商

<!--more--> 

## NTP时钟同步

1. 进入系统视图
2. 配置公共DNS 
3. 阿里云NTP服务器
4. 东八区北京时区
5. 退到用户视图
6. 查看NTP服务信息
7. 查看NTP服务信息

```bash
system-view
dns server 223.5.5.5
ntp-service unicast-server ntp1.aliyun.com
clock timezone BeiJing add 08:00:00
quit
display ntp-service status
display ntp-service sessions
```