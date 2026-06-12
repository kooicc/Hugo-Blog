---
title: 新华三-H3C
date: 2026-06-04
lastmod: 2026-06-11
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

## 会话数限制
<!-- ========== 重要提示 ========== -->
<!-- 大尺寸 -->
<div style="padding: 16px 20px; margin: 20px 0; border-left: 5px solid #ef4444; background: #fef2f2; border-radius: 8px; font-size: 16px;">
  <div style="font-weight: bold; margin-bottom: 10px; color: #ef4444; font-size: 18px;">🔴 重要提示（大）</div>
  <div>这是重要的大尺寸提示内容，适合强调非常关键的信息。</div>
</div>

<!-- 中尺寸 -->
<div style="padding: 12px 16px; margin: 16px 0; border-left: 4px solid #ef4444; background: #fef2f2; border-radius: 6px; font-size: 15px;">
  <div style="font-weight: bold; margin-bottom: 8px; color: #ef4444; font-size: 16px;">🔴 重要提示（中）</div>
  <div>这是重要的中尺寸提示内容，适合常规的重要提醒。</div>
</div>

<!-- 小尺寸 -->
<div style="padding: 8px 12px; margin: 12px 0; border-left: 3px solid #ef4444; background: #fef2f2; border-radius: 4px; font-size: 14px;">
  <div style="font-weight: bold; margin-bottom: 4px; color: #ef4444; font-size: 14px;">🔴 重要提示（小）</div>
  <div>这是重要的小尺寸提示内容，适合嵌入段落中的提醒。</div>
</div>

<!-- ========== 注意提示 ========== -->
<!-- 大尺寸 -->
<div style="padding: 16px 20px; margin: 20px 0; border-left: 5px solid #3b82f6; background: #eff6ff; border-radius: 8px; font-size: 16px;">
  <div style="font-weight: bold; margin-bottom: 10px; color: #3b82f6; font-size: 18px;">📝 注意提示（大）</div>
  <div>这是注意的大尺寸提示内容，适合重点说明。</div>
</div>

<!-- 中尺寸 -->
<div style="padding: 12px 16px; margin: 16px 0; border-left: 4px solid #3b82f6; background: #eff6ff; border-radius: 6px; font-size: 15px;">
  <div style="font-weight: bold; margin-bottom: 8px; color: #3b82f6; font-size: 16px;">📝 注意提示（中）</div>
  <div>这是注意的中尺寸提示内容，适合常规说明。</div>
</div>

<!-- 小尺寸 -->
<div style="padding: 8px 12px; margin: 12px 0; border-left: 3px solid #3b82f6; background: #eff6ff; border-radius: 4px; font-size: 14px;">
  <div style="font-weight: bold; margin-bottom: 4px; color: #3b82f6; font-size: 14px;">📝 注意提示（小）</div>
  <div>这是注意的小尺寸提示内容，适合补充说明。</div>
</div>

<!-- ========== 提示/技巧 ========== -->
<!-- 大尺寸 -->
<div style="padding: 16px 20px; margin: 20px 0; border-left: 5px solid #10b981; background: #f0fdf4; border-radius: 8px; font-size: 16px;">
  <div style="font-weight: bold; margin-bottom: 10px; color: #10b981; font-size: 18px;">💡 提示（大）</div>
  <div>这是提示的大尺寸内容，适合重点推荐的好方法。</div>
</div>

<!-- 中尺寸 -->
<div style="padding: 12px 16px; margin: 16px 0; border-left: 4px solid #10b981; background: #f0fdf4; border-radius: 6px; font-size: 15px;">
  <div style="font-weight: bold; margin-bottom: 8px; color: #10b981; font-size: 16px;">💡 提示（中）</div>
  <div>这是提示的中尺寸内容，适合常规小技巧。</div>
</div>

<!-- 小尺寸 -->
<div style="padding: 8px 12px; margin: 12px 0; border-left: 3px solid #10b981; background: #f0fdf4; border-radius: 4px; font-size: 14px;">
  <div style="font-weight: bold; margin-bottom: 4px; color: #10b981; font-size: 14px;">💡 提示（小）</div>
  <div>这是提示的小尺寸内容，适合简短建议。</div>
</div>

<!-- ========== 警告提示 ========== -->
<!-- 大尺寸 -->
<div style="padding: 16px 20px; margin: 20px 0; border-left: 5px solid #f59e0b; background: #fffbeb; border-radius: 8px; font-size: 16px;">
  <div style="font-weight: bold; margin-bottom: 10px; color: #f59e0b; font-size: 18px;">⚠️ 警告（大）</div>
  <div>这是警告的大尺寸内容，适合强调严重的风险。</div>
</div>

<!-- 中尺寸 -->
<div style="padding: 12px 16px; margin: 16px 0; border-left: 4px solid #f59e0b; background: #fffbeb; border-radius: 6px; font-size: 15px;">
  <div style="font-weight: bold; margin-bottom: 8px; color: #f59e0b; font-size: 16px;">⚠️ 警告（中）</div>
  <div>这是警告的中尺寸内容，适合常规警告提醒。</div>
</div>

<!-- 小尺寸 -->
<div style="padding: 8px 12px; margin: 12px 0; border-left: 3px solid #f59e0b; background: #fffbeb; border-radius: 4px; font-size: 14px;">
  <div style="font-weight: bold; margin-bottom: 4px; color: #f59e0b; font-size: 14px;">⚠️ 警告（小）</div>
  <div>这是警告的小尺寸内容，适合简短警示。</div>
</div>

https://www.nntb.no/~dreibh/system-tools/#binary-package-installation
https://zdl.im/resource?id=44a4579a-9d70-444e-9b6b-4cd21d2f3289
