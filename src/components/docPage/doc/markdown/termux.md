# Termux 镜像使用帮助

> Termux 是一个运行于 Android 上的 terminal, 可以用来运行 Linux 应用。它不需要 root 权限，但因此它的所有文件都存储于 SD 卡上。

Termux 自带了 `apt` 包管理器，但是官方并不推荐直接使用 `apt` ，而是推荐 `pkg` 进行操作。

## 更换镜像

以下两种方式任选其一即可。

### 使用 termux-change-repo 工具

运行 `pkg in termux-tools`

安装后运行 `termux-change-repo` ，并按照提示，首先选择需要更改镜像的仓库，之后选择 "Mirrors by HIT" 并回车确认。

### 修改 sources.list

修改以下文件：

- $PREFIX/etc/apt/sources.list
- $PREFIX/etc/apt/sources.list.d/game.list
- $PREFIX/etc/apt/sources.list.d/science.list

> 因 Termux 运行于 SD 卡，所以无权访问真实的 `/` 目录，只能访问自己的“根目录”（ $PREFIX/ ）

```text
# sources.list
deb https://mirrors.hit.edu.cn/termux/apt/termux-main stable main

# game.list
deb https://mirrors.hit.edu.cn/termux/apt/termux-games games stable

# science.list
deb https://mirrors.hit.edu.cn/termux/apt/termux-science science stable
```
