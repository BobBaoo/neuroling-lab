# NeuroLinguistics Lab Website

基于 Hugo + Blowfish 主题的神经语言学课题组网站。

**在线地址：** <https://crazybob01.com/>（域名 DNS 配置完成后生效）  
**备用地址：** <https://bobbaoo.github.io/neuroling-lab/>

## 技术栈

- [Hugo](https://gohugo.io/) — 静态网站生成器
- [Blowfish](https://blowfish.page/) — Hugo 主题
- GitHub Pages — 托管 + 自动部署

## 本地开发

```bash
# 克隆仓库
git clone --recurse-submodules git@github.com:BobBaoo/neuroling-lab.git
cd neuroling-lab

# 启动开发服务器（热重载）
hugo server -D

# 构建
hugo
```

> Hugo 安装：macOS 用 `brew install hugo`，其他系统见 [gohugo.io/installation](https://gohugo.io/installation/)。

## 目录结构

```
├── config/_default/        # 站点配置
│   ├── languages.en.toml   # 英文语言设置
│   ├── languages.zh-cn.toml # 中文语言设置
│   ├── menus.en.toml       # 英文导航菜单
│   ├── menus.zh-cn.toml    # 中文导航菜单
│   └── params.toml         # 主题参数
├── content/
│   ├── en/                 # 英文内容
│   └── zh/                 # 中文内容
│       ├── _index.md       # 首页
│       ├── people/         # 团队成员
│       ├── research/       # 研究方向
│       ├── publications/   # 论文发表
│       ├── news/           # 新闻动态
│       ├── join/           # 加入我们
│       └── contact/        # 联系方式
├── assets/img/             # 图片资源（LOGO、照片等）
├── static/                 # 静态文件
│   └── CNAME               # 自定义域名配置
└── .github/workflows/      # CI/CD 自动部署
```

## 内容更新指南

### 新增新闻

```bash
hugo new content content/zh/news/2025-06-xxx.md
hugo new content content/en/news/2025-06-xxx.md
```

### 修改成员信息

编辑 `content/zh/people/_index.md` 和 `content/en/people/_index.md`

### 添加论文

编辑 `content/zh/publications/_index.md` 和 `content/en/publications/_index.md`

### 更新站点配置

站点名称、描述等在 `config/_default/languages.*.toml` 中修改。主题参数在 `config/_default/params.toml` 中修改。

### 替换图片

- LOGO：替换 `assets/img/logo.svg`
- 成员照片：放入 `assets/img/` 后在内容中引用

## 部署

推送到 `main` 分支即自动触发 GitHub Actions 构建并部署到 GitHub Pages。
