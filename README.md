# Study Notes Bot Repo

一个用于保存学习笔记的 GitHub 仓库。

这个仓库配合 AstrBot + Shipyard Neo 使用，目标是把我在学习过程中整理好的 Markdown 笔记，自动分类、自动创建目录，并提交到仓库中统一保存。

---

## 功能说明

这个仓库用于存放由 Bot 自动上传的学习笔记，主要流程如下：

1. 我在聊天中发送学习笔记
2. Bot 读取我提供的 Markdown 内容
3. Bot 自动判断主题并创建合适的目录
4. Bot 生成文件名并写入 Markdown 文件
5. Bot 自动提交并 push 到本仓库

---

## 输入格式

触发方式：

```text
上传学习笔记：
<Markdown 内容>
