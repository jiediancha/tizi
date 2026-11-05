# 翻墙工具有哪些形态：客户端、内核、扩展和路由器面板

> 代理软件可以按安装位置和控制范围区分。桌面客户端、命令行内核、浏览器扩展与路由器面板承担的工作不同，软件本身也不等于线路服务。
> 依据:mihomo 客户端列表与 Chrome 扩展文档 · 最近核对 2026-11-03

## 不同形态装在哪里？

按软件运行的位置分类，比只按设备名称分类更能看清控制范围。

| 形态 | 安装或运行位置 | 文档里的项目或功能 |
| --- | --- | --- |
| 图形客户端 | 桌面或移动设备 | Clash Verge Rev、FlClash |
| 命令行内核 | 命令行环境 | mihomo |
| 浏览器扩展 | Chrome | 浏览器代理设置管理 |
| 路由器面板 | 嵌入式、Linux 或 OpenWrt 环境 | OpenClash、ShellCrash、OpenWrt-nikki |

这张表区分软件形态，没有给出线路。拿到软件后，仍需区分软件设置与所用服务，不能把项目名称当作连接来源。

## 客户端和内核差在哪？

图形客户端提供界面，内核也可以通过命令行使用。

Clash Verge Rev 的 Linux 文档写明，没有图形界面时使用 mihomo 内核二进制，通过命令行操作。是否需要图形界面，决定了使用方式的一部分。

流量如何接入是另一项信息。系统代理需要程序读取设置；TUN 则通过虚拟网卡处理 TCP 与 UDP。软件形态与流量接入方式不能混为同一个问题。

## 浏览器扩展管到哪里？

Chrome 的代理扩展功能管理的是浏览器自己的代理设置。

扩展需要在清单中声明 proxy 权限。由文档描述看，它管浏览器，不能把这项能力直接写成控制整个系统。

文档列出 direct、auto_detect、pac_script、fixed_servers、system 这些模式。

在 fixed_servers 中，未单独设置的协议会使用 fallbackProxy；没有回退设置则直连。bypassList 可以排除指定主机。

## 路由器面板在哪里查？

mihomo 客户端列表把路由器相关项目列在平台分类中，并标维护状态。

截至 2026-11-03，OpenWrt 分类列出多个项目，其中 OpenClash、ShellCrash 和 OpenWrt-nikki 均标为维护中。ShellCrash 也列在 Linux 分类。

名词解释把 OpenClash 描述为嵌入式或 Linux 平台的面板程序；ShellCrash 兼容多种内核；OpenWrt-nikki 是 OpenWrt 上的 mihomo 内核面板。

维护状态是列表标注，不能代替具体固件的兼容资料。文档没有说明这些项目的安装方法与固件兼容性。

形态比较可看[代理软件专题](https://www.jiediancha.com/topic/tool/)和[工具分类说明](https://www.jiediancha.com/tizi/)。

## 常见问题

**浏览器扩展等于系统代理吗？**

Chrome 的这项功能管理浏览器自身的代理设置。

**没有图形界面怎么办？**

Clash Verge Rev 的 Linux 文档指向 mihomo 命令行内核。

**维护中等于兼容我的固件吗？**

维护状态与具体固件兼容性是不同信息，列表标注不能替代兼容资料。

## 出处

- [mihomo 客户端及维护状态列表](https://wiki.metacubex.one/startup/client/client/)
- [Chrome 代理扩展文档](https://developer.chrome.com/docs/extensions/reference/api/proxy)
