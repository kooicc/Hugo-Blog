---
title: "Adobe软件屏蔽弹窗"
date: 2025-12-04
tags: ["Adobe"]
categories: "软件教程"
---

## 1. 卸载 Adobe Genuine Service (AGS)

   macOS：`/Library/Application Support/Adobe/AdobeGCClient` 

## 2. Clash等代理软件屏蔽Adobe规则  

```yml
- 'DOMAIN-SUFFIX,adobe.io,REJECT'
- 'DOMAIN-SUFFIX,adobestats.io,REJECT'
- 'DOMAIN-SUFFIX,cc-api.adobe.io,REJECT'
- 'DOMAIN-SUFFIX,auth.services.adobe.com,REJECT'
- 'DOMAIN-SUFFIX,ims-na1.adobelogin.com,REJECT'
- 'DOMAIN-SUFFIX,adobelogin.com,REJECT'
```

## 3. 利用防火墙（如Firewall App Blocker,火绒拦截）阻止Adobe联网

## 4. hosts域名屏蔽

  Windows以管理员身份打开CMD输入

  `notepad C:\Windows\System32\drivers\etc\host`

  macOS打开终端

  `sudo nano /etc/hosts`

```yml
127.0.0.1 adobe.io
127.0.0.1 adobestats.io
127.0.0.1 cc-api.adobe.io
127.0.0.1 auth.services.adobe.com
127.0.0.1 ims-na1.adobelogin.com
127.0.0.1 adobelogin.com
```
