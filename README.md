# 🚀 GitHub 新手完全指南

> 这是一份为编程新手设计的 GitHub 使用教程。无论你是编程初学者还是从未接触过版本控制，这份指南都会帮助你快速上手 GitHub！

---

## 📚 目录

1. [什么是 GitHub？](#1-什么是-github)
2. [什么是 Git？](#2-什么是-git)
3. [前期准备](#3-前期准备)
4. [创建 GitHub 账号](#4-创建-github-账号)
5. [安装 Git](#5-安装-git)
6. [配置 Git](#6-配置-git)
7. [创建第一个仓库](#7-创建第一个仓库)
8. [克隆仓库](#8-克隆仓库到本地)
9. [第一次提交](#9-你的第一次提交)
10. [分支开发](#10-分支-branch)
11. [Pull Request](#11-pull-request)
12. [常见问题](#12-常见问题)
13. [命令速查表](#13-命令速查表)

---

## 1. 什么是 GitHub？

### 简单理解

想象 GitHub 是一个**代码保管库**，类似于：
- 💾 云盘（可以保存你的代码）
- 👥 社交平台（可以与他人协作）
- 📚 作品集（可以展示你的项目）

### GitHub 的主要用途

| 用途 | 说明 |
|------|------|
| 📁 **代码托管** | 把代码保存到云端，不怕丢失 |
| 👫 **团队协作** | 多人一起开发同一个项目 |
| 📝 **版本管理** | 记录代码的每一次修改 |
| 🔍 **代码审查** | 团队成员评审代码质量 |
| 📦 **项目管理** | 跟踪任务、问题和进展 |
| 🤝 **开源贡献** | 参与全球开源社区 |
| 💼 **职业展示** | 展示你的编程能力 |

---

## 2. 什么是 Git？

### Git vs GitHub 的区别

```
┌─────────────────────────────────────┐
│  Git（本地版本控制）                 │
│  ❌ 不需要网络                        │
│  ❌ 只在你的电脑上                   │
│  ✅ 记录代码历史变化                 │
│  ✅ 管理分支开发                     │
└─────────────────────────────────────┘
           ⬇️ 推送到
┌─────────────────────────────────────┐
│  GitHub（远程代码托管）              │
│  ✅ 需要网络                         │
│  ✅ 代码保存在云端                   │
│  ✅ 多人协作                         │
│  ✅ 在线查看和管理                   │
└─────────────────────────────────────┘
```

### 核心概念解释

| 概念 | 比喻 | 作用 |
|------|------|------|
| **仓库（Repo）** | 项目文件夹 | 存放你的项目代码 |
| **提交（Commit）** | 存档点 | 记录一次代码修改 |
| **分支（Branch）** | 平行世界 | 独立开发某个功能 |
| **推送（Push）** | 上传 | 把本地代码上传到 GitHub |
| **拉取（Pull）** | 下载 | 从 GitHub 下载最新代码 |

---

## 3. 前期准备

在开始前，请准备好以下东西：

- ✅ 一个邮箱（用于注册 GitHub）
- ✅ 一个网络连接
- ✅ 一个代码编辑器（推荐 [VS Code](https://code.visualstudio.com/)）
- ✅ 30 分钟的闲置时间

---

## 4. 创建 GitHub 账号

### 步骤（5 分钟）

#### 第一步：访问官网

打开浏览器，进入 https://github.com

你会看到这样的界面：

```
┌──────────────────────────────────┐
│  GitHub 官方网站                  │
│  [Sign up] ← 点击这个按钮          │
└──────────────────────────────────┘
```

#### 第二步：填写注册信息

依次填写：

1. **Email**：你的邮箱（建议常用邮箱）
   ```
   example@gmail.com
   ```

2. **Password**：强密码（字母 + 数字 + 符号）
   ```
   MyGitHub@2024
   ```

3. **Username**：用户名（唯一标识）
   ```
   推荐：小写字母 + 数字，例如 john-code-2024
   ```

#### 第三步：验证邮箱

- 点击 "Create account"
- GitHub 会发验证邮件到你的邮箱
- 打开邮件，点击验证链接
- ✅ 账号创建完成

---

## 5. 安装 Git

### 根据你的操作系统选择

#### Windows 用户

1. 打开浏览器，进入 https://git-scm.com/downloads
2. 点击 "Windows"
3. 下载完成后，双击安装程序
4. 按默认选项一路 Next
5. 安装完成

**验证是否成功：**

打开 "命令提示符"（搜索 `cmd`），输入：

```bash
git --version
```

如果显示版本号（如 `git version 2.40.0`），说明安装成功！

#### macOS 用户

打开 "终端"（Terminal），复制粘贴这条命令：

```bash
brew install git
```

如果没有安装 Homebrew，先安装它：

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Linux 用户

打开终端，输入：

```bash
sudo apt update
sudo apt install git
```

---

## 6. 配置 Git

### 告诉 Git 你是谁

打开命令行，输入以下命令（把引号里的内容替换成你的信息）：

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"
```

**例如：**

```bash
git config --global user.name "Zhang San"
git config --global user.email "zhangsan@gmail.com"
```

### 验证配置

输入以下命令查看配置：

```bash
git config --global --list
```

你应该能看到：

```
user.name=Zhang San
user.email=zhangsan@gmail.com
```

---

## 7. 创建第一个仓库

### 在 GitHub 网页上创建

#### 第一步：进入创建页面

1. 登录 GitHub
2. 点击右上角的 **+** 图标
3. 选择 **New repository**

#### 第二步：填写仓库信息

```
┌────────────────────────────────┐
│ Repository name *              │
│ [my-first-project]  ← 填这��    │
│                                │
│ Description                    │
│ [My first GitHub project]      │
│                                │
│ Public ⭕  Private ⭕          │
│                                │
│ ☑️ Add a README file           │
│ ☑️ Add .gitignore             │
│ ☑️ Choose a license            │
│                                │
│ [Create repository]  ← 点击完成  │
└────────────────────────────────┘
```

**字段解释：**

| 字段 | 含义 | 建议 |
|------|------|------|
| **Repository name** | 仓库名 | 小写 + 连字符，如 `my-project` |
| **Description** | 描述 | 简短说明项目用途 |
| **Public/Private** | 公开/私密 | 学习用选 Public |
| **README** | 说明文件 | ✅ 一定要勾选 |

#### 第三步：创建完成

✅ 恭喜！你的第一个仓库已创建！

你会看到一个类似这样的页面：

```
my-first-project
├── README.md
├── .gitignore
└── LICENSE
```

---

## 8. 克隆仓库到本地

现在你需要把 GitHub 上的代码下载到电脑上。

### 什么是克隆？

```
GitHub 上的代码 ──[克隆]──> 你的电脑
    (远程)                  (本���)
```

### 操作步骤

#### 第一步：获取仓库地址

在你的仓库页面，点击绿色的 **Code** 按钮：

```
┌──────────────────────────┐
│ Code ▼                   │
│ ┌────────────────────┐   │
│ │ Local              │   │
│ │ [HTTPS] ⭕ SSH     │   │
│ │                    │   │
│ │ https://github...  │   │
│ │ [📋 Copy]          │   │
│ └────────────────────┘   │
└──────────────────────────┘
```

复制 HTTPS 链接（例如：`https://github.com/x1li/my-first-project.git`）

#### 第二步：在电脑上创建项目文件夹

打开命令行，选择一个合适的位置，例如：

```bash
# Windows 用户
cd D:\MyProjects

# macOS/Linux 用户
cd ~/Documents/MyProjects
```

#### 第三步：克隆仓库

输入克隆命令：

```bash
git clone https://github.com/你的用户名/my-first-project.git
```

稍等片刻，你会看到：

```
Cloning into 'my-first-project'...
remote: Counting objects: ...
Resolving deltas: 100%
```

#### 第四步：进入项目目录

```bash
cd my-first-project
```

🎉 完成！现在你的电脑上已经有了项目代码。

---

## 9. 你的第一次提交

现在，让我们做一个最简单的修改和提交。

### 第一步：修改文件

用记事本或 VS Code 打开 `README.md` 文件，添加一行内容：

```markdown
# My First Project

Hello GitHub! 👋

This is my first project.
```

### 第二步：查看状态

打开命令行，输入：

```bash
git status
```

你会看到：

```
On branch main
Changes not staged for commit:
  modified:   README.md

no changes added to commit
```

这说明 Git 检测到了你的修改。

### 第三步：添加到暂存区

```bash
git add .
```

这个命令的意思是"把所有修改的文件都加入暂存区"。

再查看一次状态：

```bash
git status
```

现在看起来像这样：

```
On branch main
Changes to be committed:
  modified:   README.md
```

### 第四步：提交修改

```bash
git commit -m "docs: update README with greeting message"
```

你会看到：

```
[main 3e4a5b6] docs: update README with greeting message
 1 file changed, 3 insertions(+)
```

这说明提交成功了！

### 第五步：推送到 GitHub

现在把修改上传到 GitHub：

```bash
git push origin main
```

你会看到：

```
Counting objects: 3, done.
Writing objects: 100% (3/3), ...
To https://github.com/你的用户名/my-first-project.git
   abc1234..3e4a5b6  main -> main
```

✅ 推送完成！现在刷新 GitHub 网页，你会看到文件已经更新了。

### 整个过程可视化

```
修改文件 → 查看状态 → 添加暂存 → 提交修改 → 推送到GitHub
  README      (看变化)    (git add)   (git commit)  (git push)
```

---

## 10. 分支（Branch）

### 为什么需要分支？

想象你在开发一个功能，但不想破坏主分支的代码。分支就是为了这个目的而存在的。

```
主分支（main）
    ↓
    ├─→ 功能分支 A（feature/login）← 开发登录功能
    │
    ├─→ 功能分支 B（feature/search）← 开发搜索功能
    │
    └─→ 修复分支（hotfix/bug-fix）← 修复紧急 bug
```

### 创建分支

#### 第一步：创建并切换到新分支

```bash
git checkout -b feature/my-new-feature
```

或者用新版命令：

```bash
git switch -c feature/my-new-feature
```

#### 第二步：查看当前分支

```bash
git branch
```

你会看到：

```
* feature/my-new-feature
  main
```

星号 `*` 表示当前所在分支。

#### 第三步：在新分支上工作

现在你可以安全地修改代码，不会影响 `main` 分支：

```bash
# 修改文件
git add .
git commit -m "feat: add new feature"
git push -u origin feature/my-new-feature
```

#### 第四步：切换回主分支

```bash
git switch main
```

或者用老版命令：

```bash
git checkout main
```

### 分支命名规范

为了管理方便，推荐这样命名：

| 分支类型 | 命名示例 | 用途 |
|---------|---------|------|
| 功能分支 | `feature/login` | 开发新功能 |
| 修复分支 | `hotfix/fix-bug` | 修复紧急 bug |
| 开发分支 | `develop` | 整合所有功能 |
| 主分支 | `main` | 生产环境代码 |

---

## 11. Pull Request

### 什么是 Pull Request？

Pull Request（简称 PR）是请求把你的分支合并到主分支的正式流程。

```
你的分支           主分支
feature/login  →  PR  →  main
    ↓
   审核 → 批准 → 合并
```

### 创建 PR 的步骤

#### 第一步：推送分支到 GitHub

```bash
git push -u origin feature/login
```

#### 第二步：在 GitHub 网页上创建 PR

打开你的仓库，GitHub 会自��提示你创建 PR：

```
┌─────────────────────────────────┐
│ feature/login 有更新              │
│ [Compare & pull request] ← 点这里 │
└─────────────────────────────────┘
```

#### 第三步：填写 PR 信息

```
┌──────────────────────────────────┐
│ Title: Add login page            │
│                                  │
│ Description:                     │
│ - 添加登录页面                    │
│ - 集成验证逻辑                    │
│ - 已完成测试                      │
│                                  │
│ Reviewers: @teammate             │
│                                  │
│ [Create pull request]            │
└──────────────────────────────────┘
```

#### 第四步：等待审查

- 🔍 团队成员查看你的代码
- 💬 他们可能会提出意见
- ✏️ 你可以继续推送修改

#### 第五步：合并 PR

审查通过后：

```
[Merge pull request]
   ↓
feature/login 分支代码 → main 分支
```

---

## 12. 常见问题

### Q1：我的提交信息应该写什么？

**好的提交信息：**

```
feat: add login functionality
fix: resolve login button click issue
docs: update README with installation guide
refactor: simplify authentication logic
```

**不好的提交信息：**

```
update
fix bug
edit file
```

### Q2：git push 失败了怎么办？

**常见错误：**

```
error: failed to push some refs to 'https://github.com/...'
hint: Updates were rejected because the remote contains work that you do
```

**解决方案：**

```bash
# 先拉取最新代码
git pull origin main

# 再推送
git push origin main
```

### Q3：如何删除不小心创建的分支？

```bash
# 删除本地分支
git branch -d feature/wrong-branch

# 删除远程分支
git push origin --delete feature/wrong-branch
```

### Q4：提交错了，怎么撤回？

**撤回最近的提交（代码保留）：**

```bash
git reset --soft HEAD~1
```

**撤回最近的提交（代码也删除）：**

```bash
git reset --hard HEAD~1
```

### Q5：如何查看提交历史？

```bash
# 简洁版本
git log --oneline

# 详细版本
git log
```

---

## 13. 命令速查表

### 最常用的 15 个命令

| 命令 | 作用 | 例子 |
|------|------|------|
| `git clone` | 克隆仓库 | `git clone https://github.com/user/repo.git` |
| `git status` | 查看状态 | `git status` |
| `git add` | 添加文件 | `git add .` |
| `git commit` | 提交修改 | `git commit -m "feat: new feature"` |
| `git push` | 推送到远程 | `git push origin main` |
| `git pull` | 拉取远程更新 | `git pull origin main` |
| `git checkout` | 切换分支 | `git checkout main` |
| `git switch` | 切换分支(新) | `git switch main` |
| `git branch` | 查看分支 | `git branch` |
| `git branch -b` | 创建分支 | `git branch -b feature/new` |
| `git log` | 查看历史 | `git log --oneline` |
| `git diff` | 查看差异 | `git diff` |
| `git merge` | 合并分支 | `git merge feature/new` |
| `git reset` | 撤销修改 | `git reset --hard HEAD~1` |
| `git config` | 配置信息 | `git config --global user.name "name"` |

---

## 📖 学习路线

### 第 1 周：掌握基础

- ✅ 创建 GitHub 账号
- ✅ 安装并配置 Git
- ✅ 创建第一个仓库
- ✅ 完成第一次提交和推送

### 第 2 周：理解分支

- ✅ 学会创建分支
- ✅ 在分支上开发功能
- ✅ 创建和合并 Pull Request
- ✅ 理解代码评审流程

### 第 3 周：实战应用

- ✅ 维护自己的项目
- ✅ 参与开源项目
- ✅ 学习 GitHub 高级功能

---

## 🎯 最佳实践

### ✅ 你应该做的

1. **定期提交**
   ```bash
   # 每完成一个小功能就提交一次
   git add .
   git commit -m "feat: complete feature X"
   ```

2. **写清晰的提交信息**
   ```bash
   git commit -m "fix: resolve authentication bug on login page"
   ```

3. **创建分支开发**
   ```bash
   git checkout -b feature/new-feature
   # 开发...
   git push origin feature/new-feature
   ```

4. **拉取最新代码**
   ```bash
   git pull origin main  # 开发前记得同步
   ```

### ❌ 你应该避免的

1. **不要直接推送到 main**
   ```bash
   # ❌ 不要这样做
   git push origin main
   
   # ✅ 应该用 PR
   git push origin feature/new-feature
   ```

2. **不要提交大文件**
   ```bash
   # ❌ 不要上传 node_modules、.env 等文件
   # ✅ 使用 .gitignore 排除它们
   ```

3. **不要使用模糊的提交信息**
   ```bash
   # ❌ 不要写"update"
   git commit -m "update"
   
   # ✅ 写清楚做了什么
   git commit -m "feat: add dark mode toggle"
   ```

---

## 🔗 推荐资源

### 官方文档

- [GitHub 官方文档](https://docs.github.com/)
- [Git 官方文档](https://git-scm.com/doc)
- [GitHub Skills](https://skills.github.com/) - 免费互动教程

### 中文资源

- [Pro Git 中文版](https://git-scm.com/book/zh/v2)
- [GitHub 官方中文文档](https://docs.github.com/zh)

### 在线工具

- [Git 可视化工具](https://git-school.github.io/visualizing-git/)
- [GitHub 在线编辑器](https://github.dev/) - 直接在浏览器编辑代码

---

## 🆘 遇到问题？

### 常见错误速查

| 错误 | 原因 | 解决方案 |
|------|------|---------|
| `fatal: not a git repository` | 不在 Git 项目里 | `cd 项目文件夹` |
| `permission denied` | 权限不足 | 检查 SSH 密钥或个人令牌 |
| `merge conflict` | 文件冲突 | 手动编辑冲突文件后重新提交 |
| `upstream is gone` | 远程分支已删除 | `git branch -u origin/main main` |

### 获取帮助

1. 搜索 GitHub Issues 有没有人遇到过
2. 查看 Stack Overflow 或技术论坛
3. 在 GitHub Discussions 提问
4. 阅读官方文档

---

## 🎓 总结

恭喜！你已经学会了：

- ✅ GitHub 的基本概念
- ✅ Git 的基本操作
- ✅ 如何创建和管理项目
- ✅ 如何与他人协作
- ✅ 如何使用 Pull Request

现在你可以：

1. 📁 创建自己的项目
2. 👥 与他人协作开发
3. 🌟 参与开源社区
4. 💼 展示你的代码能力

**下一步建议：**

> 立��创建一个项目，把你最近写的代码上传到 GitHub。实践是最好的学习方式！

---

## 📞 反馈

如果你有任何问题或建议，欢迎：

- 创建 [Issue](../../issues) 报告问题
- 提交 [Pull Request](../../pulls) 改进文档
- 在 [Discussions](../../discussions) 中讨论

---

**祝你学习愉快！🎉**

*最后更新：2024 年 10 月*
