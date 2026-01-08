# 开发流程文档

## 文档信息

**文档版本**: 1.0  
**创建日期**: 2024-01-08  
**最后更新**: 2024-01-08  
**负责人**: 王国林  
**状态**: 进行中  

## 开发环境设置

### 必需工具

| 工具 | 版本 | 用途 | 安装状态 |
|------|------|------|----------|
| VS Code | 最新 | 代码编辑器 | 已安装 |
| Git | 最新 | 版本控制 | 待安装 |
| Node.js | 最新 | JavaScript运行时 | 待安装 |
| Chrome | 最新 | 浏览器测试 | 已安装 |
| Firefox | 最新 | 浏览器测试 | 已安装 |
| Safari | 最新 | 浏览器测试 | 已安装 |
| Edge | 最新 | 浏览器测试 | 已安装 |

### 开发环境配置步骤

#### 1. 安装Git
```bash
# 下载并安装Git
# 访问 https://git-scm.com/downloads
# 下载Windows版本并安装
```

#### 2. 配置Git
```bash
git config --global user.name "王国林"
git config --global user.email "example@email.com"
```

#### 3. 初始化Git仓库
```bash
cd c:\Users\XM\Desktop\个人博客
git init
```

#### 4. 创建.gitignore文件
```bash
# .gitignore
node_modules/
.DS_Store
*.log
.vscode/
```

#### 5. 初始提交
```bash
git add .
git commit -m "Initial commit"
```

### VS Code扩展推荐

| 扩展名称 | 用途 | 安装状态 |
|----------|------|----------|
| Live Server | 本地服务器 | 待安装 |
| Prettier | 代码格式化 | 待安装 |
| ESLint | 代码检查 | 待安装 |
| Auto Rename Tag | 标签重命名 | 待安装 |
| Bracket Pair Colorizer | 括号配对 | 待安装 |

## 项目结构

### 目录结构

```
个人博客/
├── docs/                  # 文档目录
│   ├── 01-project-overview.md
│   ├── 02-requirements.md
│   ├── 03-planning.md
│   ├── 04-design.md
│   ├── 05-development.md
│   ├── 06-testing.md
│   ├── 07-deployment.md
│   ├── 08-progress-tracking.md
│   ├── 09-decisions.md
│   └── 10-challenges.md
├── assets/                # 资源目录
│   ├── images/           # 图片
│   ├── icons/            # 图标
│   └── fonts/            # 字体
├── index.html            # 主页
├── style.css             # 样式文件
├── script.js             # JavaScript文件
└── .gitignore            # Git忽略文件
```

### 文件说明

| 文件 | 描述 | 负责人 |
|------|------|--------|
| index.html | 主页HTML文件 | 王国林 |
| style.css | 样式CSS文件 | 王国林 |
| script.js | JavaScript交互文件 | 王国林 |
| docs/ | 项目文档目录 | 王国林 |
| assets/ | 资源文件目录 | 王国林 |

## 开发流程

### 阶段1: HTML结构开发

#### 任务列表
- [ ] 创建HTML5文档结构
- [ ] 添加meta标签
- [ ] 创建导航栏结构
- [ ] 创建首页横幅结构
- [ ] 创建关于我页面结构
- [ ] 创建项目展示结构
- [ ] 创建联系表单结构
- [ ] 创建页脚结构
- [ ] 添加语义化标签
- [ ] 验证HTML有效性

#### 开发步骤

**步骤1: 创建基础HTML结构**
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人博客</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- 内容 -->
</body>
</html>
```

**步骤2: 创建导航栏**
```html
<header>
    <nav class="navbar">
        <div class="logo">我的博客</div>
        <ul class="nav-links">
            <li><a href="#home">首页</a></li>
            <li><a href="#about">关于我</a></li>
            <li><a href="#projects">项目</a></li>
            <li><a href="#contact">联系</a></li>
        </ul>
    </nav>
</header>
```

**步骤3: 创建主要内容区域**
```html
<main>
    <section id="home" class="hero">
        <!-- 首页内容 -->
    </section>
    <section id="about" class="about">
        <!-- 关于我内容 -->
    </section>
    <section id="projects" class="projects">
        <!-- 项目展示内容 -->
    </section>
    <section id="contact" class="contact">
        <!-- 联系表单内容 -->
    </section>
</main>
```

**步骤4: 创建页脚**
```html
<footer>
    <p>&copy; 2024 个人博客. 保留所有权利.</p>
</footer>
```

#### 验证清单
- [ ] HTML结构完整
- [ ] 使用语义化标签
- [ ] 添加适当的ID和class
- [ ] 通过HTML验证器检查

#### 交付物
- [x] index.html文件
- [ ] HTML验证报告

#### 负责人
王国林

#### 预计时间
4小时

### 阶段2: CSS样式开发

#### 任务列表
- [ ] 创建CSS变量
- [ ] 设置全局样式
- [ ] 实现导航栏样式
- [ ] 实现首页横幅样式
- [ ] 实现关于我页面样式
- [ ] 实现项目展示样式
- [ ] 实现联系表单样式
- [ ] 实现页脚样式
- [ ] 实现响应式设计
- [ ] 添加动画效果

#### 开发步骤

**步骤1: 创建CSS变量**
```css
:root {
    --primary-color: #2563eb;
    --secondary-color: #1e40af;
    --text-color: #1f2937;
    --bg-color: #ffffff;
    --light-bg: #f3f4f6;
    --border-color: #e5e7eb;
}
```

**步骤2: 设置全局样式**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    line-height: 1.6;
    color: var(--text-color);
    background-color: var(--bg-color);
}
```

**步骤3: 实现导航栏样式**
```css
header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: rgba(255, 255, 255, 0.95);
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    z-index: 1000;
}
```

**步骤4: 实现首页横幅样式**
```css
.hero {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    text-align: center;
}
```

**步骤5: 实现响应式设计**
```css
@media (max-width: 768px) {
    .navbar {
        flex-direction: column;
        gap: 1rem;
    }
    
    .about-content,
    .contact-content {
        grid-template-columns: 1fr;
    }
}
```

#### 验证清单
- [ ] CSS样式完整
- [ ] 响应式设计正常
- [ ] 动画效果流畅
- [ ] 浏览器兼容性良好

#### 交付物
- [x] style.css文件
- [ ] CSS验证报告

#### 负责人
王国林

#### 预计时间
8小时

### 阶段3: JavaScript交互开发

#### 任务列表
- [ ] 实现导航平滑滚动
- [ ] 实现滚动高亮导航
- [ ] 实现表单验证
- [ ] 实现表单提交处理
- [ ] 实现卡片悬停效果
- [ ] 实现页面滚动动画
- [ ] 优化JavaScript性能

#### 开发步骤

**步骤1: 实现导航平滑滚动**
```javascript
document.addEventListener('DOMContentLoaded', function() {
    const navLinks = document.querySelectorAll('.nav-links a');
    
    navLinks.forEach(link => {
        link.addEventListener('click', function(e) {
            e.preventDefault();
            const targetId = this.getAttribute('href');
            const targetSection = document.querySelector(targetId);
            
            targetSection.scrollIntoView({
                behavior: 'smooth'
            });
        });
    });
});
```

**步骤2: 实现滚动高亮导航**
```javascript
window.addEventListener('scroll', function() {
    let current = '';
    const sections = document.querySelectorAll('section');
    
    sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.clientHeight;
        
        if (pageYOffset >= sectionTop - 200) {
            current = section.getAttribute('id');
        }
    });
    
    navLinks.forEach(link => {
        link.style.color = '';
        if (link.getAttribute('href') === '#' + current) {
            link.style.color = 'var(--primary-color)';
        }
    });
});
```

**步骤3: 实现表单验证和提交**
```javascript
const contactForm = document.querySelector('.contact-form');

contactForm.addEventListener('submit', function(e) {
    e.preventDefault();
    
    const formData = new FormData(this);
    const name = this.querySelector('input[type="text"]').value;
    const email = this.querySelector('input[type="email"]').value;
    const message = this.querySelector('textarea').value;
    
    alert(`感谢您的留言，${name}！我们会尽快通过 ${email} 与您联系。`);
    this.reset();
});
```

#### 验证清单
- [ ] JavaScript功能完整
- [ ] 无JavaScript错误
- [ ] 性能优化良好
- [ ] 用户体验流畅

#### 交付物
- [x] script.js文件
- [ ] JavaScript测试报告

#### 负责人
王国林

#### 预计时间
6小时

## 代码规范

### HTML规范

- 使用语义化标签
- 缩进使用4个空格
- 标签名使用小写
- 属性值使用双引号
- 添加适当的注释

### CSS规范

- 使用CSS变量
- 使用BEM命名规范
- 缩进使用4个空格
- 选择器从左到右排序
- 添加适当的注释

### JavaScript规范

- 使用ES6+语法
- 使用const和let
- 使用箭头函数
- 添加适当的注释
- 遵循函数式编程原则

## 版本控制

### Git工作流

#### 分支策略
- `main`: 主分支，用于生产环境
- `develop`: 开发分支
- `feature/*`: 功能分支

#### 提交规范
```
<type>(<scope>): <subject>

<body>

<footer>
```

#### 提交类型
- `feat`: 新功能
- `fix`: 修复bug
- `docs`: 文档更新
- `style`: 代码格式
- `refactor`: 重构
- `test`: 测试
- `chore`: 构建/工具

### 提交示例

```bash
git add .
git commit -m "feat(导航): 实现导航平滑滚动功能"
git push origin feature/navigation
```

## 代码审查

### 审查清单

#### HTML审查
- [ ] 语义化标签使用正确
- [ ] 结构清晰合理
- [ ] 添加适当的注释
- [ ] 通过HTML验证

#### CSS审查
- [ ] 样式组织合理
- [ ] 使用CSS变量
- [ ] 响应式设计完整
- [ ] 性能优化良好

#### JavaScript审查
- [ ] 代码逻辑清晰
- [ ] 无语法错误
- [ ] 性能优化良好
- [ ] 添加错误处理

## 开发工具

### 浏览器开发者工具

- Chrome DevTools
- Firefox Developer Tools
- Safari Web Inspector
- Edge DevTools

### 在线工具

- HTML Validator: https://validator.w3.org/
- CSS Validator: https://jigsaw.w3.org/css-validator/
- JavaScript Lint: https://jshint.com/
- Performance Test: https://pagespeed.web.dev/

## 开发进度跟踪

### 每日更新

| 日期 | 任务 | 进度 | 问题 | 备注 |
|------|------|------|------|------|
| 2024-01-08 | 创建HTML结构 | 100% | 无 | 完成 |
| - | - | - | - | - |

### 里程碑跟踪

| 里程碑 | 预计日期 | 实际日期 | 状态 |
|--------|----------|----------|------|
| HTML结构完成 | 2024-01-22 | - | 待完成 |
| CSS样式完成 | 2024-01-29 | - | 待完成 |
| JavaScript完成 | 2024-02-04 | - | 待完成 |

## 开发文档

### 技术文档

- [ ] API文档
- [ ] 组件文档
- [ ] 样式指南
- [ ] 代码注释

### 用户文档

- [ ] 使用说明
- [ ] 常见问题
- [ ] 故障排除

## 开发完成标准

- [ ] 所有功能开发完成
- [ ] 代码审查通过
- [ ] 无已知bug
- [ ] 性能达标
- [ ] 文档完整

## 附录

### 参考资源

- MDN Web Docs: https://developer.mozilla.org/
- CSS Tricks: https://css-tricks.com/
- JavaScript Info: https://javascript.info/

### 常用命令

```bash
# Git命令
git status
git add .
git commit -m "message"
git push

# 启动本地服务器
# 使用Live Server扩展或
python -m http.server 8000
```

## 版本历史

| 版本 | 日期 | 作者 | 变更说明 |
|------|------|------|----------|
| 1.0 | 2024-01-08 | 王国林 | 初始版本创建 |