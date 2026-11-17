# my-docs

个人技术文档站，使用 MkDocs Material 编写，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

- 网站地址：https://yuquan66611.github.io/my-docs/
- 个人实验报告：[个人实验报告](report/README.md)

## 项目结构

```text
my-docs/
├── .github/workflows/deploy.yml   # 构建 + 部署工作流
├── docs/                          # 网站内容（四页）
├── report/                        # 作业报告与截图
├── mkdocs.yml                     # 站点与导航配置
├── requirements.txt               # 构建依赖
└── .gitignore
```

## 本地预览

```bash
python -m venv .venv
.\.venv\Scripts\Activate.ps1      # PowerShell；Git Bash 用 source .venv/Scripts/activate
python -m pip install -r requirements.txt
python -m mkdocs build --strict
python -m mkdocs serve            # 打开 http://127.0.0.1:8000/
```

推送 `docs/`、`mkdocs.yml`、`requirements.txt` 或工作流文件的改动到 `main`，会自动触发构建与部署。
