# 我的愿景板 · GitHub Pages 部署

单文件 HTML 应用，无后端，无依赖，可托管在 GitHub Pages 永久免费使用。

## 文件
- `index.html` — 主应用（约 76KB，全内联、零外链、离线可用）

## 部署步骤（约 3 分钟）

### 1. 在 GitHub 新建一个空仓库
- 打开 https://github.com/new
- Repository name: `vision-board`（或任意名字，会影响最终链接）
- 选择 **Public**（GitHub Pages 免费版要求公开仓库）
- 其他选项都不要勾，直接点 **Create repository**

### 2. 把代码推上去
在本地项目目录里跑（把 `YOUR_USERNAME` 改成你的 GitHub 用户名）：

```bash
cd "J:\KSQD\WorkBuddy数据\lBK梦想板"
git init
git add index.html README.md .gitignore
git -c user.email="you@example.com" -c user.name="Your Name" commit -m "feat: 部署个人愿景板"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/vision-board.git
git push -u origin main
```

第一次 push 会要求登录：用户名 + **Personal Access Token**（不再是密码）。
获取 Token：GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token，勾选 `repo` 即可。

### 3. 开启 GitHub Pages
- 进仓库页面 → 顶部 **Settings** → 左侧 **Pages**
- Source: **Deploy from a branch**
- Branch: `main` / `(root)` → Save

等待 1-3 分钟，链接会出现在 Pages 设置页顶部：

> ✦ **https://YOUR_USERNAME.github.io/vision-board/**

手机浏览器打开这个链接即可。

## 后续修改（最常用）

**改愿景内容、数字、文字卡、上传照片、备份数据**——全部在网页底部「设置」Tab 里完成，改完自动保存到浏览器 localStorage。不需要重新部署。

**想改页面本身（比如换背景色、改交互逻辑）**：
1. 在 `J:\KSQD\WorkBuddy数据\lBK梦想板\index.html` 里修改
2. 推送：
   ```bash
   git add index.html
   git commit -m "update: ..."
   git push
   ```
3. 等 1-3 分钟，链接自动刷新

## 数据存在哪？
- 全部存在你自己**手机/电脑浏览器的 localStorage** 里——不上传服务器
- 不同设备的数据互不相通（手机和电脑各一份）
- 想换设备：在原设备的「设置 → 导出备份」下载 JSON，到新设备「设置 → 导入恢复」上传即可
- 想全清：从仓库 Settings → Danger Zone → Delete this repository

## 添加到手机桌面（像 APP 一样）
打开链接 → 浏览器菜单 → 「添加到主屏幕」/「Add to Home Screen」，之后从桌面图标进入就是**全屏运行**，没有浏览器地址栏，像原生 APP。

## 为什么用 GitHub Pages？
- **永久免费**（公开仓库）
- **永久链接**（不删仓库就一直能用）
- **自带 HTTPS**（手机浏览器 PWA 友好）
- 后续想换域名也很简单