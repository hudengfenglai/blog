# Algolia 搜索配置指南

## 注册 Algolia

1. **访问 https://www.algolia.com/**
2. **注册账号**（可使用 GitHub 登录）
3. **创建应用**
   - 点击 "Create Application"
   - 名称随意，如 "My Blog"
   - 选择合适的区域

## 创建索引

1. 进入应用后，点击左侧 "Search" → "Indices"
2. 点击 "Create Index"
3. 索引名称填写 `blog`（记住这个名称）
4. 其他保持默认即可

## 获取 API 密钥

1. 点击左侧 "Settings" → "API Keys"
2. 复制以下信息：
   - **Application ID**（应用 ID）
   - **Search-Only API Key**（搜索专用密钥，公开的）
3. ⚠️ **不要使用 Admin API Key**，只使用 Search-Only Key！

## 配置博客

在 `config/_default/params.yml` 中填写：

```yaml
algolia_search:
  enable: true
  appID: "你的Application ID"
  apiKey: "你的Search-Only API Key"
  indexName: "blog"
```

## 上传搜索索引

Hugo 会自动生成 `algolia.json` 文件，但需要手动上传到 Algolia。

### 方法一：使用 atomic-algolia（推荐）

1. **安装 atomic-algolia**
   ```bash
   npm install -g atomic-algolia
   ```

2. **在博客目录创建 `.env` 文件**
   ```bash
   cd blog
   npm init -y
   npm install dotenv
   ```

3. **创建 `atomic-algolia.config.json`**
   ```json
   {
     "appId": "你的Application ID",
     "apiKey": "你的Admin API Key",
     "indexName": "blog",
     "paths": ["public/algolia.json"]
   }
   ```

4. **每次部署前运行**
   ```bash
   npx atomic-algolia
   ```

### 方法二：GitHub Actions 自动上传

创建 `.github/workflows/algolia.yml`：

```yaml
name: Upload to Algolia

on:
  push:
    branches: [main]

jobs:
  algolia:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: |
          npm install
          npm install atomic-algolia

      - name: Upload to Algolia
        run: npx atomic-algolia
        env:
          ALGOLIA_APP_ID: ${{ secrets.ALGOLIA_APP_ID }}
          ALGOLIA_ADMIN_KEY: ${{ secrets.ALGOLIA_ADMIN_KEY }}
          ALGOLIA_INDEX_NAME: blog
```

在 GitHub 仓库设置中添加 secrets：
- `ALGOLIA_APP_ID`
- `ALGOLIA_ADMIN_KEY`

## 验证

1. 本地运行 `hugo`
2. 检查 `public/algolia.json` 是否生成
3. 在 Algolia Dashboard 的 Indices 页面查看是否有数据
4. 在博客中测试搜索功能

## 常见问题

### Q: 搜索没有结果
- 检查 algolia.json 是否生成
- 检查 API 密钥是否正确
- 检查索引名称是否匹配

### Q: atomic-algolia 报错
- 确保使用的是 Admin API Key
- 确保索引名称一致