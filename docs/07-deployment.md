# 部署流程文档

## 文档信息

**文档版本**: 1.0  
**创建日期**: 2024-01-08  
**最后更新**: 2024-01-08  
**负责人**: 王国林  
**状态**: 进行中  

## 部署概述

### 部署目标

- 将网站部署到生产环境
- 确保网站可访问
- 配置域名和SSL证书
- 设置监控和备份

### 部署环境

| 环境 | 用途 | 状态 |
|------|------|------|
| 开发环境 | 本地开发 | 已配置 |
| 测试环境 | 功能测试 | 待配置 |
| 生产环境 | 正式上线 | 待配置 |

## 部署前准备

### 部署检查清单

#### 代码检查

- [ ] 所有功能开发完成
- [ ] 代码审查通过
- [ ] 无已知严重bug
- [ ] 代码已提交到版本控制
- [ ] 版本标签已创建

#### 测试检查

- [ ] 功能测试通过
- [ ] 兼容性测试通过
- [ ] 性能测试通过
- [ ] 安全测试通过
- [ ] 用户体验测试通过

#### 文档检查

- [ ] 开发文档完整
- [ ] 测试文档完整
- [ ] 部署文档完整
- [ ] 用户文档完整

#### 配置检查

- [ ] 域名已购买
- [ ] 服务器已准备
- [ ] SSL证书已准备
- [ ] 备份策略已制定

### 部署前测试

#### 预部署测试

| 测试项 | 测试内容 | 测试结果 | 测试人 | 测试日期 |
|--------|----------|----------|--------|----------|
| 功能测试 | 所有功能正常运行 | - | - | - |
| 性能测试 | 性能指标达标 | - | - | - |
| 兼容性测试 | 主流浏览器兼容 | - | - | - |
| 安全测试 | 安全漏洞检查 | - | - | - |

## 部署方案

### 部署选项

#### 选项1: 静态网站托管

**平台选择**:
- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages

**推荐**: GitHub Pages (免费、稳定、易用)

#### 选项2: 云服务器

**平台选择**:
- 阿里云
- 腾讯云
- 华为云
- AWS
- Azure

**推荐**: 阿里云 (国内访问快、价格合理)

### 部署方案选择

**选择方案**: GitHub Pages

**选择理由**:
- 完全免费
- 配置简单
- 自动部署
- 支持自定义域名
- 稳定可靠

## 部署步骤

### 方案1: GitHub Pages部署

#### 步骤1: 创建GitHub仓库

1. 访问 https://github.com
2. 登录或注册账号
3. 点击"New repository"
4. 输入仓库名称: `personal-blog`
5. 选择Public或Private
6. 点击"Create repository"

#### 步骤2: 上传代码到GitHub

```bash
# 初始化Git仓库
cd c:\Users\XM\Desktop\个人博客
git init

# 添加所有文件
git add .

# 提交更改
git commit -m "Initial commit"

# 添加远程仓库
git remote add origin https://github.com/username/personal-blog.git

# 推送到GitHub
git branch -M main
git push -u origin main
```

#### 步骤3: 配置GitHub Pages

1. 进入GitHub仓库页面
2. 点击"Settings"
3. 点击"Pages"选项
4. 在"Build and deployment"下:
   - Source: 选择"Deploy from a branch"
   - Branch: 选择"main"分支和"/ (root)"目录
5. 点击"Save"

#### 步骤4: 等待部署完成

- 部署通常需要1-2分钟
- 部署完成后会显示网站URL
- 默认URL: `https://username.github.io/personal-blog/`

#### 步骤5: 验证部署

1. 访问部署的URL
2. 检查页面是否正常显示
3. 测试所有功能
4. 检查响应式设计

### 方案2: 自定义域名配置

#### 步骤1: 购买域名

**域名注册商**:
- 阿里云: https://wanwang.aliyun.com/
- 腾讯云: https://dnspod.cloud.tencent.com/
- GoDaddy: https://www.godaddy.com/
- Namecheap: https://www.namecheap.com/

**推荐域名**:
- `.com`: 通用性强
- `.cn`: 国内访问快
- `.net`: 技术类网站

#### 步骤2: 配置DNS

1. 登录域名注册商
2. 找到DNS管理
3. 添加以下记录:

| 记录类型 | 主机记录 | 记录值 | TTL |
|----------|----------|--------|-----|
| CNAME | www | username.github.io. | 600 |
| CNAME | @ | username.github.io. | 600 |

#### 步骤3: 配置GitHub Pages

1. 进入GitHub仓库Settings
2. 点击"Pages"选项
3. 在"Custom domain"中输入域名
4. 点击"Save"
5. 等待DNS生效(通常需要24-48小时)

#### 步骤4: 配置SSL证书

GitHub Pages自动提供SSL证书，无需手动配置。

### 方案3: 云服务器部署

#### 步骤1: 购买云服务器

**推荐配置**:
- CPU: 1核
- 内存: 1GB
- 带宽: 1Mbps
- 系统盘: 40GB
- 操作系统: Ubuntu 20.04 LTS

#### 步骤2: 配置服务器

```bash
# 连接到服务器
ssh root@your-server-ip

# 更新系统
apt update && apt upgrade -y

# 安装Nginx
apt install nginx -y

# 启动Nginx
systemctl start nginx
systemctl enable nginx
```

#### 步骤3: 上传网站文件

```bash
# 在本地执行
scp -r c:\Users\XM\Desktop\个人博客\* root@your-server-ip:/var/www/html/
```

#### 步骤4: 配置Nginx

```bash
# 编辑Nginx配置
nano /etc/nginx/sites-available/default

# 修改以下内容
server {
    listen 80;
    server_name your-domain.com www.your-domain.com;
    root /var/www/html;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}

# 重启Nginx
systemctl restart nginx
```

#### 步骤5: 配置SSL证书

```bash
# 安装Certbot
apt install certbot python3-certbot-nginx -y

# 获取SSL证书
certbot --nginx -d your-domain.com -d www.your-domain.com

# 自动续期
certbot renew --dry-run
```

## 部署验证

### 功能验证

| 验证项 | 验证内容 | 验证结果 | 验证人 | 验证日期 |
|--------|----------|----------|--------|----------|
| 页面加载 | 首页正常加载 | - | - | - |
| 导航功能 | 导航链接正常工作 | - | - | - |
| 表单功能 | 联系表单正常提交 | - | - | - |
| 响应式设计 | 移动端正常显示 | - | - | - |

### 性能验证

| 指标 | 目标值 | 实际值 | 状态 |
|------|--------|--------|------|
| FCP | < 1.5s | - | 待测试 |
| LCP | < 2.5s | - | 待测试 |
| FID | < 100ms | - | 待测试 |

### 安全验证

| 验证项 | 验证内容 | 验证结果 | 验证人 | 验证日期 |
|--------|----------|----------|--------|----------|
| SSL证书 | HTTPS正常工作 | - | - | - |
| 安全头 | 安全头配置正确 | - | - | - |
| XSS防护 | XSS攻击防护有效 | - | - | - |

## 部署后维护

### 监控

#### 监控指标

- 网站可用性
- 页面加载速度
- 错误率
- 流量统计

#### 监控工具

- Google Analytics: 流量分析
- Uptime Robot: 可用性监控
- PageSpeed Insights: 性能监控

### 备份

#### 备份策略

- 代码备份: Git版本控制
- 数据备份: 定期备份
- 配置备份: 文档记录

#### 备份频率

- 代码: 每次提交
- 配置: 每次修改
- 数据: 每周

### 更新

#### 更新流程

1. 在开发环境测试新功能
2. 提交代码到版本控制
3. 合并到主分支
4. 自动部署到生产环境
5. 验证部署结果

#### 回滚策略

1. 保留历史版本
2. 快速回滚到稳定版本
3. 分析问题原因
4. 修复后重新部署

## 部署文档

### 部署记录

| 部署ID | 部署日期 | 部署人 | 版本 | 部署环境 | 部署结果 | 备注 |
|--------|----------|--------|------|----------|----------|------|
| - | - | - | - | - | - | - |

### 部署检查清单

#### 部署前检查

- [ ] 代码已提交
- [ ] 测试通过
- [ ] 备份完成
- [ ] 通知相关人员

#### 部署后检查

- [ ] 网站可访问
- [ ] 功能正常
- [ ] 性能达标
- [ ] 日志正常

## 故障排除

### 常见问题

#### 问题1: 网站无法访问

**可能原因**:
- 服务器未启动
- DNS未生效
- 防火墙阻止

**解决方案**:
1. 检查服务器状态
2. 检查DNS配置
3. 检查防火墙设置

#### 问题2: 页面显示异常

**可能原因**:
- 文件未正确上传
- 路径配置错误
- 缓存问题

**解决方案**:
1. 检查文件上传
2. 检查路径配置
3. 清除浏览器缓存

#### 问题3: 性能问题

**可能原因**:
- 图片未优化
- 代码未压缩
- 服务器配置不当

**解决方案**:
1. 优化图片
2. 压缩代码
3. 优化服务器配置

### 应急响应

#### 应急流程

1. 发现问题
2. 评估影响
3. 通知相关人员
4. 执行回滚
5. 分析原因
6. 修复问题
7. 重新部署

#### 联系人

| 角色 | 姓名 | 电话 | 邮箱 |
|------|------|------|------|
| 项目负责人 | 王国林 | - | example@email.com |

## 部署完成标准

- [ ] 网站成功部署
- [ ] 所有功能正常
- [ ] 性能指标达标
- [ ] 安全配置完成
- [ ] 监控系统运行
- [ ] 备份策略实施
- [ ] 文档更新完成

## 附录

### 部署脚本

#### 自动部署脚本 (GitHub Actions)

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout
      uses: actions/checkout@v3
      
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./
```

### 参考资源

- GitHub Pages文档: https://docs.github.com/pages
- Nginx文档: https://nginx.org/en/docs/
- Let's Encrypt: https://letsencrypt.org/

## 版本历史

| 版本 | 日期 | 作者 | 变更说明 |
|------|------|------|----------|
| 1.0 | 2024-01-08 | 王国林 | 初始版本创建 |