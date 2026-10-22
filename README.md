# poc-nuclei-templates

> 由个人漏洞 PoC 知识库 5316 篇笔记自动转换生成的 **Nuclei 漏扫模板**。

## 规模

| 目录 | 模板数 |
|---|---|
| templates/2024/ | 2345 |
| templates/2025/ | 2294 |
| templates/2026/ | 674 |
| templates/unknown/ | 0 |
| **合计** | **4813** |

另有 503 篇文档为纯分析文章/Python 脚本/无 HTTP 请求内容，未生成模板。

## 覆盖类型

SQL注入 / RCE / 任意文件上传 / 任意文件读取 / 信息泄露 / 未授权访问 / 弱口令 / XXE / SSRF / 反序列化 等，主要面向国内政务、教育、医疗、OA 等场景的自研与商用系统。

## 使用

```bash
# 全量
nuclei -t templates/ -u https://target

# 按年份/标签筛选
nuclei -t templates/2025/ -u https://target -tags sqli
```

## ⚠️ 命中条件推断说明

原文档「响应内容特征」多为截图，无法自动提取文本匹配规则，因此以下命中条件为**自动推断**，模板 `description` 中含 `[!] 推断说明` 标注，使用前建议人工核验：

- **常规请求**：使用「响应代码特征」中的状态码（缺失时推断为 200）作为命中条件
- **时间盲注类**（payload 含 SLEEP/WAITFOR/BENCHMARK 等）：推断为 `dsl: status_code == 200 && duration >= 5`
- **无 HTTP 方法的裸路径**：推断为 GET 请求

## 免责声明

本仓库模板仅供**授权安全测试与安全研究**使用。请勿对未授权目标进行扫描或利用，使用者对自身行为负责。
