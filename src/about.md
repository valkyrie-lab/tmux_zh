# 关于文档

tmux 是一个终端复用工具，有三个主要功能：

- 保护会话：即使 ssh 连接断开，进程也不会丢失。
- 多端访问：不同的本地终端可以访问同一远端程序。
- 终端复用：类似窗口管理，聚合、操作多个终端程序。

// 截图

本文档主要介绍 tmux 的基本概念、使用方法，以及一些常用的配置。内容强烈参考 <https://github.com/tmux/tmux/wiki/Getting-Started>

在线阅读网址 <https://tmux.qaq.land>，本站使用 mdBook 构建，源码位于 <https://github.com/valkyrie-lab/tmux_zh>，欢迎您指出错误、帮助我们优化文档逻辑、或者提出其它宝贵的意见。

本作品采用 <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议 (CC BY-NC-SA 4.0)</a> 进行许可。

---

## 安装

> 同类型程序有 screen、zellij 等，如果系统不支持 tmux 或不合适，可以考虑其他替代品。

// 不同发行版
