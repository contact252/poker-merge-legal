# Poker Merge 2048 - Legal Documents

这个文件夹包含游戏的法律文档，用于上架 Google Play 和 App Store。

## 文件说明

- `index.html` - 主页（包含指向隐私政策和服务条款的链接）
- `privacy-policy.html` - 隐私政策
- `terms-of-service.html` - 服务条款

## 部署到 GitHub Pages

### 步骤1：创建 GitHub 仓库

1. 登录 GitHub
2. 创建新仓库：`poker-merge-2048-legal`（或任意名称）
3. 设置为 **Public**（免费托管）

### 步骤2：上传文件

```bash
# 在项目根目录执行
cd /Users/Song/cocos/PokerMerge

# 初始化 Git（如果还没有）
git init

# 添加远程仓库（替换为你的 GitHub 用户名）
git remote add docs https://github.com/YOUR_USERNAME/poker-merge-2048-legal.git

# 只提交 docs-website 文件夹
cd docs-website
git init
git add .
git commit -m "Add legal documents"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/poker-merge-2048-legal.git
git push -u origin main
```

### 步骤3：启用 GitHub Pages

1. 进入仓库 → Settings → Pages
2. Source 选择 `main` 分支
3. 文件夹选择 `/ (root)`
4. 点击 Save

等待 1-2 分钟后，你的网站就会发布在：
```
https://YOUR_USERNAME.github.io/poker-merge-2048-legal/
```

## 使用这些 URL

**隐私政策：**
```
https://YOUR_USERNAME.github.io/poker-merge-2048-legal/privacy-policy.html
```

**服务条款：**
```
https://YOUR_USERNAME.github.io/poker-merge-2048-legal/terms-of-service.html
```

## 修改前的重要事项

在部署前，请务必修改以下内容：

1. **替换邮箱地址**：
   - 搜索 `[YOUR_EMAIL@example.com]`
   - 替换为你的真实邮箱

2. **替换管辖区域**（terms-of-service.html 第11条）：
   - `[Your Country/State]` 改为你的国家/地区（例如：中国、美国加州）
   - `[Your Jurisdiction]` 改为具体司法管辖区

3. **检查第三方服务**：
   - 如果你没用 Google Analytics/Firebase，删除 privacy-policy.html 中的相关段落
   - 如果用了其他广告平台（Unity Ads等），添加相应隐私链接

## 快速修改命令

```bash
# 批量替换邮箱（macOS/Linux）
cd docs-website
sed -i '' 's/\[YOUR_EMAIL@example.com\]/yourname@gmail.com/g' *.html

# 批量替换司法管辖区
sed -i '' 's/\[Your Country\/State\]/China/g' terms-of-service.html
sed -i '' 's/\[Your Jurisdiction\]/Shanghai, China/g' terms-of-service.html
```

## 在游戏中使用

修改后的 URL 需要填写到：

1. **Google Play Console** → App Content → Privacy Policy → 填入 URL
2. **App Store Connect** → App Information → Privacy Policy URL → 填入 URL
3. **游戏内设置面板** → 添加按钮 → 使用 `sys.openURL()` 跳转
