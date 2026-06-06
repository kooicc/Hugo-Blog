---
title: FreeBSD
date: 2026-06-05T01:16:53+08:00
cover:
    image: "FreeBSD-logo-dark.png"
    relative: true
    hidden: false
categories:
  - FreeBSD
tags:
  - FreeBSD
---

[FreeBSD](https://www.freebsd.org/zh-tw/) 是一个免费、开源、类 Unix 的操作系统，源自 BSD（伯克利软件发行版），以高性能、稳定可靠、安全性强著称。

<!--more-->

## 使用 Ports Collection  

![FRESH ports](https://www.freshports.org/images/freshports.jpg)  
> FreeBSD 用 Ports 来编译安装最新版软件

1. 查询软件包：<https://www.freshports.org/login.php>

2. 克隆 Ports 仓库

    `git clone https://git.FreeBSD.org/ports.git /usr/ports`

3. 更新 Ports

    ```bash
    cd /usr/ports
    git pull
    ```

4. 编译并安装 Hugo（示列）

    ```sh
    cd /usr/ports/www/gohugo
    make install clean
    ```

5. 清理旧版本
   Ports 的编译过程默认不会删除旧版本，建议每次更新后运行：

    ```sh
    pkg autoremove
    ```

## 更新系统软件

`pkg update && pkg upgrade`

### 使用代理

编辑*pkg.conf*文件末尾添加代理信息  

`ee /usr/local/etc/pkg.conf`

```sh
pkg_env: {
    HTTP_PROXY: "http://100.104.66.71:1081",
    HTTPS_PROXY: "http://100.104.66.71:1081",
    # socks5替换上面两行，启用下面一行
    # ALL_PROXY: "socks5h://127.0.0.1:7890"
}
```

### 使用国内镜像源

阿里云：<https://developer.aliyun.com/mirror/freebsd-pkg>

创建*FreeBSD.conf*文件进行源仓库配置

`ee /usr/local/etc/pkg/repos/FreeBSD.conf`  

FreeBSD 15  

```sh
FreeBSD-ports: {
  url: "http://mirrors.aliyun.com/freebsd-pkg/${ABI}/quarterly",
  mirror_type: "none",
  signature_type: "fingerprints",
  fingerprints: "/usr/share/keys/pkg",
  enabled: yes
}

FreeBSD-ports-kmods: {
  url: "http://mirrors.aliyun.com/freebsd-pkg/${ABI}/kmods_quarterly_${VERSION_MINOR}",
  mirror_type: "none",
  signature_type: "fingerprints",
  fingerprints: "/usr/share/keys/pkg",
  enabled: yes
}

FreeBSD-base: {
  url: "http://mirrors.aliyun.com/freebsd-pkg/${ABI}/base_release_${VERSION_MINOR}",
  mirror_type: "none",
  signature_type: "fingerprints",
  fingerprints: "/usr/share/keys/pkgbase-${VERSION_MAJOR}",
  enabled: yes
}
```

## bectl

bectl 是 FreeBSD 内置的 Boot Environment (引导环境) 管理命令，用于创建、切换和删除可独立启动的系统环境。

### 创建系统快照

1. 系统快照

   `bectl create system-backup`

2. 验证备份已创建

   `bectl list`

3. 查看备份占用的空间

   `bectl list -D`

### 恢复系统

1. 激活备份环境

`bectl activate system-backup`

2. 重启

`reboot`

3. 系统启动后，确认已在备份环境，Active 列为 NR。

`bectl list`

4. 删除指定备份

`bectl destroy system-backup`

## zfs snapshot

ZFS 快照是 ZFS 文件系统的核心功能，可以在秒级创建文件系统在某一时刻的只读副本，几乎不占用额外空间（只在文件变化后才记录差异）
