# 使用指南

## 日常更新流程

1. 修改 docs 目录中的 Markdown 文件。
2. 在本地预览并检查页面及链接。
3. 提交修改并推送到 main 分支。
4. 在 Actions 页面查看构建与部署状态。
5. 打开网站检查内容是否更新。

## 常用命令

- python -m mkdocs serve：本地预览。
- python -m mkdocs build --strict：构建网站并严格检查警告。

## 一次完整的本地验证

```bash
# 1. 进入仓库，激活虚拟环境
cd my-docs
.\.venv\Scripts\Activate.ps1

# 2. 严格构建：有断链、缺页会直接失败
python -m mkdocs build --strict

# 3. 本地预览，逐个检查四页导航、表格和代码块
python -m mkdocs serve
```

## 目录约定

| 路径 | 是否提交 | 说明 |
| --- | --- | --- |
| `docs/` | 提交 | 网站源码，所有内容都在这里改 |
| `mkdocs.yml` | 提交 | 站点名称、主题、导航配置 |
| `site/` | 不提交 | 构建产物，由 `build` 生成，已写入 `.gitignore` |
| `report/` | 提交 | 作业报告与截图 |

## 容易踩的两个坑

1. `nav` 中的路径是相对于 `docs/` 的，写成 `index.md` 而不是 `docs/index.md`；写成后者会在严格构建时直接报找不到文件。
2. 只改 `report/` 或 `README.md` 不会触发部署工作流，因为 `on.push.paths` 只监听了 `docs/**`、`mkdocs.yml`、`requirements.txt` 和工作流自身。这是设计如此，不是故障。

回到[首页](index.md)看站点概览，或查看[API 参考](api.md)。
