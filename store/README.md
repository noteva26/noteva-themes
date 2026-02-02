# Noteva 主题集市 - 提交指南

本目录用于第三方主题开发者提交主题索引，让您的主题出现在 Noteva 官方主题集市中。

## 📋 提交方式

在 `store/` 目录下创建以您的主题名称命名的文件夹，并在其中放置 `theme.json` 文件。

**目录结构示例：**
```
store/
  your-theme-name/
    theme.json
    preview.png (可选)
```

## 📝 theme.json 格式说明

```json
{
  "short": "your-theme-name",
  "name": "主题显示名称",
  "version": "1.0.0",
  "description": "主题功能描述",
  "author": "作者名称",
  "url": "https://github.com/your-username/your-theme-repo",
  "preview": "preview.png",
  "requires": {
    "noteva": ">=0.0.8"
  }
}
```

## 🔑 必填字段

| 字段 | 说明 | 示例 |
|------|------|------|
| `short` | 主题唯一标识符（建议使用小写字母和连字符） | `"my-awesome-theme"` |
| `name` | 主题显示名称 | `"我的超棒主题"` |
| `version` | 主题版本号（遵循语义化版本） | `"1.0.0"` |
| `description` | 主题功能描述 | `"简洁优雅的博客主题"` |
| `author` | 作者名称 | `"Your Name"` |
| `url` | **主题仓库地址（必填）** | `"https://github.com/you/repo"` |
| `requires.noteva` | **支持的 Noteva 版本（必填）** | `">=0.0.8"` |

## 🎨 可选字段

| 字段 | 说明 | 示例 |
|------|------|------|
| `preview` | 主题预览图文件名 | `"preview.png"` |

## ⚠️ 重要提示

### 关于 `url` 字段
- **必须填写**您的主题 GitHub 仓库地址
- 用户将从此仓库的 Releases 下载主题编译后的文件
- 请确保仓库中有可用的 Release 版本（包含编译后的 dist 目录）

### 关于 `requires.noteva` 字段
- **必须填写**主题支持的 Noteva 最低版本
- 支持的格式：
  - `">=0.0.8"` - 大于等于 0.0.8
  - `"<=0.1.0"` - 小于等于 0.1.0
  - `">0.0.7"` - 大于 0.0.7
  - `"<0.2.0"` - 小于 0.2.0
  - `"0.0.8"` - 精确版本
- ⚠️ **如果用户的 Noteva 版本不满足要求，主题将无法安装和切换**

### 关于预览图
- 推荐尺寸：1200x630 或 16:9 比例
- 格式：PNG 或 JPG
- 文件大小：建议小于 500KB

## 📦 发布流程

1. **开发主题**：在您自己的 GitHub 仓库中开发主题（基于 Next.js）
2. **编译主题**：运行 `pnpm run build` 生成 dist 目录
3. **创建 Release**：在您的仓库中创建 Release，上传主题压缩包（包含 dist、theme.json、preview.png 等）
4. **提交索引**：Fork 本仓库，在 `store/` 目录下添加您的 `theme.json` 和 `preview.png`
5. **提交 PR**：提交 Pull Request，等待审核

## 📚 完整示例

```json
{
  "short": "default",
  "name": "Noteva 默认主题",
  "version": "0.0.8",
  "description": "Noteva 官方默认主题，简洁优雅",
  "author": "Noteva Team",
  "url": "https://github.com/noteva26/noteva-themes",
  "preview": "preview.png",
  "requires": {
    "noteva": ">=0.0.8"
  }
}
```

## 🎨 主题开发要求

- 基于 Next.js 14+ 开发
- 使用 Noteva SDK 提供的 API
- 编译后的文件必须包含在 Release 中
- 提供清晰的安装和使用说明

## 🤝 贡献

欢迎提交您的主题到 Noteva 官方集市！如有问题，请在 Issues 中提出。

---

**注意**：官方主题源代码直接放在仓库根目录，第三方主题索引放在 `store/` 目录。
