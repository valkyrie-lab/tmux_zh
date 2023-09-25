# Asciinema 录屏

Asciinema 是基于命令行的录屏工具，我们这里用它来录制操作，便于在文档中展示。

```shell
$ doas apk add asciinema
```

[**官方教程**](https://asciinema.org/docs/usage) 并不复杂，我们只用到其中的三个部分：

## 1. 开始录制

```shell
$ asciinema rec <filename.cast>
```

调整录制终端大小为 80x24，如

```shell
$ asciinema rec --cols 80 --rows 24 <filename.cast>
```

使用 `--stdin` 执行命令录制键盘输入（以后会显示按键）

```shell
$ asciinema rec --stdin <filename.cast>
```

## 2. 结束录制

输入 `$ exit` 或按下 <kbd>CTRL</kbd> + <kbd>d</kbd> 结束录像。

如果录制时使用的进程结束，也会自动结束录制。所以在录制 tmux 内部操作时，可以先创建好会话

```shell
$ tmux new -s terminal-capture
```

使用 `-c` 执行命令进入会话

```shell
$ asciinema rec -c "tmux attach -t terminal-capture"
```

这样 <kbd>CTRL</kbd> + <kbd>b</kbd> <kbd>d</kbd> 分离会话时，录制会自动结束。

<div id="test"></div>

结束后可以先在本地预览，不过可以跳过此步，直接在网页里看也挺好。

```shell
$ asciinema play <filename.cast>
```

## 3. 嵌入网页

使用官方支持的网页播放器：<https://github.com/asciinema/asciinema-player>

```html
<link rel="stylesheet" type="text/css" href="cast/asciinema-player.css" />
<script src="cast/asciinema-player.min.js"></script>
<!-- 组件一页引入一次就行 -->

<div id="demo-1"></div>
<div id="demo-2"></div>
<!-- 若干，放入文中对应位置 -->

<script>
  AsciinemaPlayer.create("cast/demo-1.cast", document.getElementById("demo-1"));
  AsciinemaPlayer.create("cast/demo-1.cast", document.getElementById("demo-2"));
</script>
<!-- 写在页尾 -->
```

直接在 Markdown 里对应位置写 HTML 的标签就行，注意

1. DOM 要写在 script 前面
2. DOM 的 ID 要和脚本里的对应
3. 使用的 `xxx.cast` 是相对路径



<link rel="stylesheet" type="text/css" href="asciinema-player.css" />
<script src="asciinema-player.min.js"></script>

<script>
  AsciinemaPlayer.create("test.cast", document.getElementById("test"));
</script>
