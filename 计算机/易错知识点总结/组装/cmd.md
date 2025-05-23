# 🖥 Windows 基础网络与控制命令总结

---

## 📡 一、网络相关命令

### 1. `ipconfig` - 查看和管理 IP 配置

**作用：** 显示本地计算机的 IP 地址、子网掩码、默认网关等信息。

**常用参数：**

| 参数                | 说明                                  |
|---------------------|---------------------------------------|
| `/all`              | 显示完整网络配置信息（包括 MAC、DNS 等） |
| `/release`          | 释放当前 IP 地址                      |
| `/renew`            | 重新获取 IP 地址                      |
| `/flushdns`         | 清除 DNS 缓存                        |
| `/displaydns`       | 显示 DNS 缓存内容                    |

---

### 2. `ping` - 测试网络连通性

**作用：** 向目标主机发送 ICMP 数据包，测试网络是否畅通。

**常用参数：**

| 参数          | 说明                       |
| ----------- | ------------------------ |
| `-t`        | 持续 ping，直到手动停止（Ctrl + C） |
| `-n [次数]`   | 指定发送数据包次数                |
| `-l [大小]`   | 指定数据包大小（默认 32 字节）        |
| `-4` / `-6` | 使用 IPv4 或 IPv6 地址格式      |

**示例：**
```bash
ping www.baidu.com -n 4 -l 64
```

---

### 3. `tracert` - 路由跟踪

**作用：** 显示数据包从本机到目标主机所经过的路径（跳数）。

**示例：**
```bash
tracert www.baidu.com
```

---

### 4. `netstat` - 查看网络连接状态

**作用：** 显示网络连接、监听端口、路由表等信息。

**常用参数：**

| 参数      | 说明                         |
|-----------|------------------------------|
| `-a`      | 显示所有连接和监听端口       |
| `-n`      | 以 IP 形式显示地址和端口号   |
| `-o`      | 显示每个连接的进程 ID (PID)  |
| `-b`      | 显示每个连接对应的程序名（需管理员权限） |

**示例：**
```bash
netstat -ano
```

---

### 5. `nslookup` - DNS 诊断工具

**作用：** 用于查询域名的 IP 地址或测试 DNS 服务器。

**示例：**
```bash
nslookup www.google.com
```

---

### 6. `arp` - 查看/修改 ARP 缓存表

**常用参数：**

| 参数       | 说明                           |
|------------|--------------------------------|
| `-a`       | 显示 ARP 缓存内容              |
| `-d [IP]`  | 删除某个 IP 的 ARP 映射        |
| `-s IP MAC`| 手动添加 IP-MAC 映射（静态）  |

---

### 7. `route` - 查看和设置路由表

**示例：**
```bash
route print             # 查看路由表
route add 192.168.1.0 mask 255.255.255.0 192.168.0.1
```

---

## ⚙ 二、系统控制命令

### 1. `shutdown` - 关机/重启/注销

| 参数             | 说明                       |
|------------------|----------------------------|
| `/s`             | 关机                       |
| `/r`             | 重启                       |
| `/l`             | 注销当前用户               |
| `/t [秒]`        | 设置延迟时间（默认 30 秒） |
| `/a`             | 取消正在进行的关机操作     |

**示例：**
```bash
shutdown /s /t 10
```

---

### 2. `tasklist` - 显示当前运行的进程

**配合 `taskkill` 使用。**

**示例：**
```bash
tasklist
taskkill /PID 1234 /F
```

---

### 3. `net` 命令族（管理服务/共享/用户）

- `net user`：用户管理
- `net start` / `net stop`：启动或停止服务
- `net share`：管理共享资源

**示例：**
```bash
net user newuser /add
net share documents=C:\Users\Public\Documents
net start w32time
```

---

### 4. `systeminfo` - 查看系统详细信息

**作用：** 包括系统版本、内存、启动时间、补丁等信息。

---

### 5. `wmic` - WMI 命令行管理工具（适用于旧系统）

**示例：**
```bash
wmic cpu get name
wmic os get caption
```

---

## ✅ 小技巧：管理员运行 CMD

1. 在开始菜单中搜索 “cmd”
2. 右键 → 以管理员身份运行

---

📌 **推荐搭配使用：**
- `ipconfig /all` + `ping`：排查网络 IP 配置和连通性
- `netstat -ano` + `tasklist`：分析端口占用情况
- `tracert` + `nslookup`：排查外网连接慢的问题

