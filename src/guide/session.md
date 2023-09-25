# 会话

## 创建

外部执行 tmux 命令 `new-session` 或简写 `new`

```shell
$ tmux new
```

// 图

新建会话会自动创建一个窗口，自动创建的窗口中会自动创建一个窗格，窗格中运行终端解释器。

## 名称

session 名称默认是从 0 递增的数字，可以通过 `-s` 参数指定名称。

```shell
$ tmux new -s <session-name>
```

// 图

使用 `-A` 尝试创建会话，如果已经存在同名会话会直接依附

```shell
$ tmux new -A <session-name>
```

名称是唯一标识，不可重复。可以在创建后重命名

```shell
$ tmux rename-session -t <old-name> <new-name>
```

// 图

// 快捷键

// 内置命令

可以通过 `-n` 参数指定 0 号默认窗口的名称

```shell
$ tmux new -n <window-name>
```

// 图

## 依附

`attach` 或 `a` 依附上次使用且未被依附的会话

```shell
$ tmux attach
```

// 图

`-t` 指定会话名称作为目标

```shell
$ tmux attach -t <session-name>
```

默认同一会话可以被多个客户端同时依附，使用 `-d` 踢走别人（使其分离）进行独占

```shell
$ tmux attach -d
```

## 启动

默认启动进程是当前用户的 shell，可以设置为其它程序：

```shell
$ tmux new htop
```

传递参数的话需要用引号包裹

```shell
$ tmux new 'nano README.md'
```

或者使用 `--` 分隔

```shell
$ tmux new -- nano README.md
```

## 列表

`list-sessions` 或 `ls` 列出所有会话

```shell
$ tmux ls
```

// 图
