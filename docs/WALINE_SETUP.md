# Waline 评论系统配置指南

## 快速部署 Waline

### 方法一：Vercel 部署（推荐）

1. ** Fork Waline 仓库**
   - 访问 https://github.com/walinejs/waline
   - 点击 Fork 按钮

2. **在 Vercel 导入项目**
   - 访问 https://vercel.com/new
   - 导入你 Fork 的仓库

3. **配置环境变量**
   在 Vercel 项目设置中添加以下环境变量：

   | 变量名 | 说明 | 获取方式 |
   |--------|------|----------|
   | `LEAN_ID` | LeanCloud App ID | 见下方 |
   | `LEAN_KEY` | LeanCloud App Key | 见下方 |
   | `LEAN_MASTER_KEY` | LeanCloud Master Key | 见下方 |
   | `LEAN_SERVER` | LeanCloud 服务地址 | 见下方 |
   | `SECURE_DOMAINS` | 安全域名 | `hudengfenglai.github.io` |

4. **获取 LeanCloud 凭证**
   - 注册 https://www.leancloud.app/
   - 创建应用（选国际版）
   - 在「设置」→「应用凭证」中获取 ID 和 Key

5. **部署**
   - 点击 Deploy 按钮
   - 等待部署完成
   - 获取分配的域名（如 `xxx.vercel.app`）

### 方法二：Railway 部署

1. 参考 https://waline.js.org/guide/deploy/railway.html

## 配置博客

部署完成后，在 `config/_default/params.yml` 中填写：

```yaml
waline:
  enable: true
  serverURL: "https://你的域名.vercel.app"  # 填入你的 Waline 地址
```

## 验证

1. 访问你的博客
2. 打开一篇文章
3. 在底部应该能看到评论框
4. 尝试提交一条评论测试

## 常见问题

### Q: 评论不显示
- 检查 `serverURL` 是否正确
- 检查浏览器控制台是否有错误
- 确保 Waline 服务已正常部署

### Q: 如何管理评论
- 访问 `https://你的域名.vercel.app/ui` 管理评论