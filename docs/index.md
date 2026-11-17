# 我的技术文档

欢迎访问我的个人文档网站。本网站使用 MkDocs 构建，通过 GitHub Actions 自动部署到 GitHub Pages。

- 作者：yuquan66611
- 实践主题：静态文档自动部署

## 为什么做这个站

我是软件工程专业的学生，平时写过 Spring MVC 的课程项目、做过 Android 的 WebView 迁移，也用 Python 跑过数据挖掘实验。这些代码最后大多只存在本地电脑或课程群里，时间一长就找不到，也没有一个"给别人看"的入口。这次实践的目标很直接：把零散的 Markdown 笔记变成一个有固定网址、能持续更新、不需要手动上传的文档站。

## 本站结构

| 页面 | 内容 | 更新频率 |
| --- | --- | --- |
| [关于本项目](about.md) | 项目目标、技术组成、个人背景 | 很少改动 |
| [使用指南](guide.md) | 本地预览、构建、推送的操作步骤 | 流程变化时改 |
| [API 参考](api.md) | 文档示例接口的字段说明 | 接口调整时改 |

## 一句话原理

推送到 `main` 的 Markdown 会被 GitHub Actions 在一个干净的 Ubuntu 环境里用 MkDocs 编译成 `site/`，再作为 Pages 的构建产物发布。所以本地只需要写 `docs/`，`site/` 永远由机器生成。

```bash
# 本地三步：写、构建、预览
python -m mkdocs build --strict
python -m mkdocs serve
```

想了解具体操作，从[使用指南](guide.md)开始。
