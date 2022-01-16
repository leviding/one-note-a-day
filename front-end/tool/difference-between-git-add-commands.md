# git add .，git add -A，git add -u，git add * 的区别与联系

## 考查知识点

- Git 的使用

## 导读

主要看开发中基础工具的使用熟练度，以及在使用过程中是有自己的总结思考还是能用就行。


## 题解

这几个命令在不同版本的 Git 中稍有差异。

**对于 Git Version 1.x：**

1. `git add .`：会将工作区中的新文件和对已有文件的修改提交至暂存区，但不包括被删除的文件。
2. `git add -u`：`git add --update` 的简写形式，它只会监控之前已被 `add` 的文件，即已被跟踪(tracked)的文件，即只会将被修改和被删除的文件提交至暂存区。而新文件因为未被跟踪(tracked)，所以不会被提交至暂存区。
3. `git add -A`：`git add --all` 的简写形式，属于 `git add .` 和 `git add -u` 的功能合集。

总结详见下图：

![image](https://user-images.githubusercontent.com/26959437/149653234-4ef85e4c-71ac-44ae-899d-3fdf871d19fc.png)

**对于 Git Version 2.x：**

`git add .` 和 `git add -A` 的功能变得完全相同，而新增了 `git add --ignore-removal .` 命令替代了旧版 `git add .` 的功能。其他命令功能不变。详见下图：

![image](https://user-images.githubusercontent.com/26959437/149653342-62bafce7-faab-4db3-ad70-7a0bf7e2a6db.png)

**`git add *`**：

`git add *` 表示添加当前目录下的所有文件，但不包括文件名以 `.` 符号开头的文件。这是 Shell 命令，git 只是接收文件列表。而 `git add .` 的功能与 `git add *` 基本相同，只是 `git add .` 会将文件名以 `.` 符号开头的文件也提交至暂存区。

---

> [[返回目录](./index.md)]
