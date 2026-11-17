# API 参考

以下接口仅用于文档展示，不提供真实服务。写这一页的目的是练习接口文档的常见写法：请求行、参数表、返回示例、错误码。

## 查询文档列表

- 请求方法：GET
- 请求路径：/api/docs
- 功能：返回文档条目列表。

### 请求参数

| 参数 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| page | int | 否 | 页码，默认 1 |
| size | int | 否 | 每页条数，默认 20，最大 100 |
| keyword | string | 否 | 按标题模糊匹配 |

### 返回示例

```json
{
  "items": [
    {"id": 1, "title": "使用指南"}
  ],
  "page": 1,
  "size": 20,
  "total": 4
}
```

### 错误码

| 状态码 | 含义 | 处理方式 |
| --- | --- | --- |
| 400 | 参数非法（如 size 超过 100） | 按参数表校验后重试 |
| 404 | 文档不存在 | 检查 id 是否已删除 |
| 500 | 服务端异常 | 记录请求 ID 后联系维护者 |

## 调用示例

```bash
curl -s "https://example.com/api/docs?page=1&size=20"
```

```python
import json
import urllib.request

with urllib.request.urlopen("https://example.com/api/docs?page=1") as resp:
    data = json.load(resp)

print(len(data["items"]), "条文档")
```

回到[首页](index.md)，或查看[关于本项目](about.md)。
