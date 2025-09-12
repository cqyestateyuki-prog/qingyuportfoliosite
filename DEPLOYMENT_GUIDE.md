# 网站部署指南

本指南将帮助您将作品集网站部署到网上，让全世界都能访问您的作品！

## 🚀 部署平台选择

### 推荐平台（免费）
1. **Vercel** - 最佳选择，对React项目支持完美
2. **Netlify** - 功能强大，易于使用
3. **GitHub Pages** - 完全免费，适合静态网站

## 📋 部署前准备

### 1. 确保代码已提交
```bash
# 检查Git状态
git status

# 如果还有未提交的更改
git add .
git commit -m "Ready for deployment"
```

### 2. 创建GitHub仓库
1. 访问 [GitHub.com](https://github.com)
2. 点击 "New repository"
3. 仓库名称：`qingyu-portfolio`
4. 设置为 Public
5. 不要勾选 "Add README"（因为我们已经有了）

### 3. 推送代码到GitHub
```bash
# 添加远程仓库
git remote add origin https://github.com/您的用户名/qingyu-portfolio.git

# 推送到GitHub
git push -u origin master
```

## 🌟 方法一：Vercel部署（推荐）

### 步骤1：注册Vercel账号
1. 访问 [vercel.com](https://vercel.com)
2. 点击 "Sign Up"
3. 选择 "Continue with GitHub"
4. 授权Vercel访问您的GitHub

### 步骤2：导入项目
1. 在Vercel仪表板点击 "New Project"
2. 选择您刚创建的GitHub仓库
3. 点击 "Import"

### 步骤3：配置项目
- **Framework Preset**: Vite
- **Root Directory**: `./` (默认)
- **Build Command**: `npm run build` (默认)
- **Output Directory**: `dist` (默认)
- **Install Command**: `npm install` (默认)

### 步骤4：部署
1. 点击 "Deploy"
2. 等待构建完成（通常2-3分钟）
3. 获得您的网站URL：`https://qingyu-portfolio.vercel.app`

### 步骤5：自定义域名（可选）
1. 在项目设置中点击 "Domains"
2. 添加您的自定义域名
3. 配置DNS记录

## 🌐 方法二：Netlify部署

### 步骤1：注册Netlify账号
1. 访问 [netlify.com](https://netlify.com)
2. 点击 "Sign up"
3. 选择 "GitHub"

### 步骤2：连接仓库
1. 点击 "New site from Git"
2. 选择 "GitHub"
3. 选择您的仓库

### 步骤3：构建设置
- **Build command**: `npm run build`
- **Publish directory**: `dist`
- **Base directory**: `./`

### 步骤4：部署
1. 点击 "Deploy site"
2. 等待构建完成
3. 获得网站URL：`https://random-name.netlify.app`

## 📱 方法三：GitHub Pages部署

### 步骤1：安装GitHub Pages插件
1. 在仓库页面点击 "Settings"
2. 左侧菜单选择 "Pages"
3. Source选择 "GitHub Actions"

### 步骤2：创建工作流文件
创建 `.github/workflows/deploy.yml`：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ master ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout
      uses: actions/checkout@v3
      
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        
    - name: Install dependencies
      run: npm install
      
    - name: Build
      run: npm run build
      
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./dist
```

### 步骤3：推送代码
```bash
git add .
git commit -m "Add GitHub Pages workflow"
git push
```

## 🔧 部署后配置

### 1. 更新简历文件
确保简历文件在正确位置：
```
public/files/Qingyu_Cao_Resume.pdf
```

### 2. 测试所有功能
- [ ] 主页加载正常
- [ ] 项目详情页正常
- [ ] 图片查看器工作
- [ ] 简历下载功能
- [ ] 联系表单
- [ ] 响应式设计

### 3. 性能优化
- 压缩图片文件
- 启用CDN
- 配置缓存策略

## 🚨 常见问题解决

### 问题1：构建失败
**原因**：依赖问题或代码错误
**解决**：
```bash
# 本地测试构建
npm run build

# 检查错误信息
npm run lint
```

### 问题2：图片不显示
**原因**：图片路径错误
**解决**：确保图片在 `public/media/` 目录下

### 问题3：路由不工作
**原因**：单页应用路由配置
**解决**：在Vercel/Netlify中配置重定向规则

### 问题4：简历下载失败
**原因**：文件路径或权限问题
**解决**：确保文件在 `public/files/` 目录下

## 📊 部署后监控

### 1. 性能监控
- 使用Google PageSpeed Insights
- 监控Core Web Vitals
- 优化加载速度

### 2. 访问统计
- 集成Google Analytics
- 监控用户行为
- 分析访问数据

### 3. 定期更新
- 定期更新项目内容
- 保持依赖包最新
- 备份重要数据

## 🎯 最佳实践

### 1. 版本控制
- 使用有意义的提交信息
- 定期推送代码
- 使用分支管理功能

### 2. 安全考虑
- 不要提交敏感信息
- 使用环境变量
- 定期更新依赖

### 3. 备份策略
- 定期备份代码
- 保存重要文件
- 使用多个部署平台

## 📞 技术支持

如果在部署过程中遇到问题，可以：

1. 查看平台文档
2. 检查构建日志
3. 联系技术支持
4. 参考本指南的常见问题部分

---

**祝您部署成功！🎉**

*最后更新：2024年12月*
