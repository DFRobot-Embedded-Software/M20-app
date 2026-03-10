# M20 应用注册中心

这是 M20 应用商店的**注册中心仓库**，负责维护应用索引和图标。

## 📁 仓库结构

```
M20-app/
├── apps_index.json          # 应用索引文件（必需）
├── icons/                   # 应用图标目录
│   └── hello_world.png     # 应用图标（按 app_id 命名）
└── README.md
```

**注意**：应用代码不在本仓库中，每个应用都有自己的独立 GitHub 仓库。

## 🏗️ 架构说明

### 注册中心（本仓库）
- **职责**：维护 `apps_index.json` 和 `icons/` 目录
- **内容**：应用元数据、图标、下载链接
- **更新**：通过 PR 提交新应用或更新现有应用信息

### 应用仓库（独立仓库）
- **职责**：存放应用的实际代码
- **结构**：每个应用一个独立的 GitHub 仓库
- **示例**：`M20-hello-world`、`M20-snake` 等

## 🚀 添加新应用

### 1. 创建应用仓库
为你的应用创建一个独立的 GitHub 仓库，例如 `M20-your-app`。

### 2. 在注册中心添加应用信息
Fork 本仓库，修改 `apps_index.json`：

```json
{
  "apps": [
    {
      "app_id": "your_app_id",
      "name": "应用名称",
      "version": "1.0.0",
      "description": "应用描述",
      "category": "分类",
      "author": "作者",
      "tags": ["标签1", "标签2"],
      "repo": "https://github.com/your-username/M20-your-app",
      "download": null,
      "icon_url": "icons/your_app_id.png",
      "main_file": "main.py"
    }
  ]
}
```

**字段说明**：
- `repo`: 应用的独立 GitHub 仓库 URL（必需）
- `download`: ZIP 下载直链（可选，优先使用 GitHub Release）
- `icon_url`: 图标路径（相对于注册中心仓库）
- `path`: **已废弃**，不再使用

### 3. 添加应用图标
将应用图标放到 `icons/your_app_id.png`，建议尺寸 256x256 或 512x512。

### 4. 提交 PR
提交 Pull Request，审核通过后应用会出现在应用商店中。

## 📝 应用索引格式

完整的 `apps_index.json` 格式：

```json
{
  "apps": [
    {
      "app_id": "hello_world",
      "name": "Hello World",
      "version": "1.0.0",
      "description": "应用描述",
      "category": "示例",
      "author": "M20 Team",
      "tags": ["示例", "入门"],
      "repo": "https://github.com/DFRobot-Embedded-Software/M20-hello-world",
      "download": null,
      "icon_url": "icons/hello_world.png",
      "main_file": "main.py",
      "homepage": "https://github.com/DFRobot-Embedded-Software/M20-hello-world"
    }
  ]
}
```

## 🎯 应用仓库结构

每个应用仓库应包含：
- `app.json` - 应用描述文件（必需）
- `main.py` - 主程序文件（必需）
- `pyproject.toml` - uv 依赖配置（如果使用 uv）
- `handlers.py` - 事件处理（可选）
- `ui.xml` - 界面定义（可选）

## 📚 更多信息

- [M20 应用开发指南](../M20-XML-GUI/README.md)
- [m20gui 框架文档](../M20-XML-GUI/m20gui/)
- [应用商店架构文档](../M20-XML-GUI/app_store/ARCHITECTURE.md)
