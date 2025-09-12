# 媒体资源文件结构说明

## 📁 文件夹结构

### 项目媒体资源 (`projects/`)
每个项目都有独立的文件夹，包含以下子文件夹：

#### 1. `hero/` - 项目主图
- `hero-image.jpg` - 项目详情页的主图
- `hero-video.mp4` - 项目视频（可选）

#### 2. `thumbnails/` - 缩略图
- `thumbnail.jpg` - 项目列表页的缩略图

#### 3. `sections/` - 各章节图片
根据项目章节组织，例如：
- `research/` - 研究阶段图片
- `design/` - 设计阶段图片
- `final/` - 最终成果图片
- `concept/` - 概念图
- `mechanics/` - 机制说明图
- `art/` - 艺术设计图
- `showcase/` - 展示图
- `tech-stack/` - 技术栈图
- `methodology/` - 方法论图
- `modeling/` - 建模图
- `logo-design/` - 标志设计图
- `brand-guidelines/` - 品牌指南图

### 通用资源 (`common/`)
- `icons/` - 通用图标
- `backgrounds/` - 背景图片
- `avatars/` - 头像图片

### 视频资源 (`videos/`)
- `project-demos/` - 项目演示视频
- `process/` - 过程记录视频

## 📝 文件命名规范

### 图片文件
- 使用小写字母和连字符
- 包含描述性名称
- 例如：`research-interview-1.jpg`, `final-mockup-mobile.jpg`

### 视频文件
- 使用小写字母和连字符
- 包含项目名称和描述
- 例如：`stumbldoor-demo.mp4`, `design-process-timelapse.mp4`

## 🎯 使用方式

### 在代码中引用
```javascript
// 项目主图
heroImage: '/media/projects/stumbldoor/hero/hero-image.jpg'

// 缩略图
thumbnail: '/media/projects/stumbldoor/thumbnails/thumbnail.jpg'

// 章节图片
images: [
  {
    src: '/media/projects/stumbldoor/sections/research/research-1.jpg',
    alt: 'Research process',
    caption: 'User interview session'
  }
]
```

## 📏 图片尺寸建议

### 主图 (hero)
- 推荐尺寸：1200x800px 或 1600x900px
- 格式：JPG, PNG
- 文件大小：< 500KB

### 缩略图 (thumbnail)
- 推荐尺寸：400x300px
- 格式：JPG
- 文件大小：< 100KB

### 章节图片
- 推荐尺寸：800x600px
- 格式：JPG, PNG
- 文件大小：< 300KB

### 视频
- 格式：MP4
- 分辨率：1080p 或 720p
- 文件大小：< 50MB（用于网页）

## 🔧 优化建议

1. **压缩图片**：使用工具如 TinyPNG 或 ImageOptim 压缩图片
2. **WebP格式**：考虑使用 WebP 格式以获得更好的压缩率
3. **响应式图片**：为不同屏幕尺寸准备不同尺寸的图片
4. **懒加载**：在代码中实现图片懒加载以提升性能

## 📋 上传清单

在上传文件前，请确保：
- [ ] 文件命名符合规范
- [ ] 图片尺寸合适
- [ ] 文件大小在建议范围内
- [ ] 图片质量清晰
- [ ] 文件放在正确的文件夹中
