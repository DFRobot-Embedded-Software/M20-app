# M20 应用商店 - GitHub 应用模板

这是一个 GitHub 应用仓库的模板，你可以基于此创建自己的应用商店。

## 📁 仓库结构

```
m20-apps/
├── apps_index.json          # 应用索引文件（必需）
├── apps/                   # 应用目录
│   └── hello_world/        # 示例应用
│       ├── app.json
│       ├── main.py
│       ├── handlers.py
│       ├── ui.xml
│       └── icon.png
└── README.md
```

## 🚀 快速开始

1. **Fork 或克隆这个仓库**
2. **修改 `apps_index.json`** 添加你的应用
3. **在 `apps/` 目录下创建你的应用**
4. **推送到 GitHub**
5. **在应用商城中配置仓库 URL**

详细说明请参考 `GITHUB_SETUP.md`。

## 📝 应用索引格式

`apps_index.json` 格式：

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
      "path": "apps/your_app_id",
      "icon": "icon.png",
      "main_file": "main.py",
      "tags": ["标签1", "标签2"]
    }
  ]
}
```

## 🎯 应用结构

每个应用需要包含：
- `app.json` - 应用描述文件（必需）
- `main.py` - 主程序文件（必需）
- `handlers.py` - 事件处理（可选）
- `ui.xml` - 界面定义（可选）
- `icon.png` - 应用图标（可选）

## 📚 更多信息

- [M20 应用开发指南](../README.md)
- [GitHub 设置指南](../GITHUB_SETUP.md)
