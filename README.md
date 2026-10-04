# GitHub 使用教程

GitHub 是一个基于 Git 的代码托管平台，适合项目管理、协作开发、代码审查和开源贡献。本文档将带你从入门到基础实用，帮助你快速掌握 GitHub 的核心使用方式。

---

## 1. GitHub 是什么？

GitHub 是全球最常用的代码托管平台之一，主要用于：

- 托管代码仓库
- 版本控制
- 团队协作
- Pull Request（PR）代码审查
- 项目管理
- 自动化部署和 CI/CD
- 开源社区协作

GitHub 依赖 Git 作为底层版本控制系统，而 GitHub 则负责代码在线托管与多人协作。

---

## 2. 先准备什么？

在使用 GitHub 之前，建议你准备：

- 一个 GitHub 账号
- Git 安装在本地电脑
- 一个代码编辑器（VS Code 推荐）
- 一个想管理或协作的项目

---

## 3. 注册 GitHub 账号

1. 打开 https://github.com
2. 点击 Sign up
3. 输入邮箱、用户名和密码
4. 完成验证码验证
5. 选择免费版即可开始使用

建议你：

- 使用常用邮箱
- 取一个简洁、易记的用户名
- 填写真实信息，方便团队协作和职业展示

---

## 4. 什么是 Git？

Git 是一个分布式版本控制工具，主要用于：

- 记录代码修改历史
- 回滚到任意版本
- 分支开发
- 多人协作
- 避免覆盖他人代码

GitHub 是 Git 的在线托管平台；Git 负责“本地版本管理”，GitHub 负责“远程协作与共享”。

---

## 5. 安装 Git

### Windows

- 下载：https://git-scm.com/downloads
- 安装后验证：

```bash
git --version
```

### macOS

```bash
brew install git
```

### Linux

```bash
sudo apt install git
```

---

## 6. 配置 Git 用户信息

首次使用 Git 时，建议配置用户名和邮箱：

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"
```

查看配置：

```bash
git config --global --list
```

---

## 7. GitHub 仓库（Repository）

仓库是 GitHub 中存放项目代码的地方，通常包含：

- 项目代码
- 文档说明
- 配置文件
- README
- .gitignore

仓库可以是：

- 公开仓库：任何人都可以看到
- 私有仓库：仅允许指定用户访问

---

## 8. 创建第一个仓库

在 GitHub 网页端操作：

1. 登录 GitHub
2. 点击右上角的 +
3. 选择 New repository
4. 输入仓库名
5. 选择公开或私有
6. 可以勾选 “Initialize this repository with a README”
7. 点击 Create repository

推荐命名：

- `my-project`
- `front-end-demo`
- `user-management-api`

---

## 9. 克隆仓库到本地

克隆指的是把远程仓库下载到本地：

```bash
git clone https://github.com/用户名/仓库名.git
```

例如：

```bash
git clone https://github.com/octocat/Hello-World.git
```

进入目录：

```bash
cd Hello-World
```

---

## 10. 常用 Git 命令

### 查看状态

```bash
git status
```

### 添加文件到暂存区

```bash
git add .
```

### 提交代码

```bash
git commit -m "feat: add login page"
```

### 推送到远程仓库

```bash
git push origin main
```

### 拉取远程更新

```bash
git pull origin main
```

### 查看提交记录

```bash
git log --oneline
```

---

## 11. Git 分支（Branch）

分支用于并行开发，避免破坏主分支。常见分支如下：

- `main`：主分支
- `develop`：开发分支
- `feature/login`：功能分支
- `hotfix/fixbug`：修复分支

创建分支：

```bash
git checkout -b feature/login
```

或者新版本 Git：

```bash
git switch -c feature/login
```

切换分支：

```bash
git switch main
```

查看分支：

```bash
git branch
```

---

## 12. 提交代码到 GitHub

完整流程：

```bash
git status
git add .
git commit -m "初始化项目"
git push origin main
```

如果是第一次推送新分支：

```bash
git push -u origin feature/login
```

---

## 13. Pull Request（PR）

Pull Request 是指把某个分支的代码请求合并到另一个分支。它通常用于：

- 代码评审
- 团队协作
- 功能合并前检查
- 控制主分支稳定性

操作流程：

1. 创建分支
2. 提交代码
3. 进入 GitHub 仓库
4. 点击 Compare & pull request
5. 填写标题和说明
6. 选择目标分支（如 `main`）
7. 创建 PR

PR 提交时，建议说明：

- 修改了什么
- 为什么修改
- 是否有风险
- 是否已测试

---

## 14. Issue 是什么？

Issue 用于跟踪：

- bug
- 新功能需求
- 任务清单
- 讨论和反馈

它类似项目中的待办事项和问题记录。

创建 Issue 的步骤：

1. 打开仓���
2. 点击 Issues
3. 点击 New issue
4. 输入标题和内容
5. 点击 Submit new issue

---

## 15. README.md 是什么？

README 是项目首页展示的说明文件，通常包括：

- 项目简介
- 安装步骤
- 使用方式
- 目录结构
- 贡献方式
- 运行环境

示例：

```markdown
# My Project

这是一个示例项目。

## 安装

```bash
npm install
```

## 运行

```bash
npm run dev
```
```

---

## 16. .gitignore 的作用

.gitignore 通常用来忽略不需要上传的文件，例如：

- `node_modules/`
- `.env`
- `dist/`
- `.DS_Store`

示例：

```gitignore
node_modules/
.env
.DS_Store
```

---

## 17. GitHub 协作流程

真实开发中常用流程如下：

1. 从 `main` 拉取最新代码
2. 创建功能分支
3. 在分支上开发功能
4. 提交代码并推送
5. 创建 Pull Request
6. 代码评审
7. 合并到 `main`
8. 删除已完成分支

示例：

```bash
git checkout main
git pull origin main
git checkout -b feature/search
git add .
git commit -m "feat: add search"
git push -u origin feature/search
```

---

## 18. 常见冲突处理

当两个人修改了同一文件时，可能出现冲突。处理方式：

```bash
git status
```

然后手动解决冲突文件，再继续：

```bash
git add .
git commit -m "resolve merge conflicts"
```

---

## 19. GitHub Actions（基础介绍）

GitHub Actions 可以让你自动化：

- 代码测试
- 构建项目
- 自动部署
- 定时任务

通常配置在：

```bash
.github/workflows/
```

---

## 20. GitHub 个人主页的价值

GitHub 也可以作为个人技术展示平台：

- 展示项目
- 记录学习历程
- 提升职业竞争力
- 参与开源社区

建议：

- 维护公开项目
- 写清晰 README
- 保持代码质量
- 参与真实项目贡献

---

## 21. 最常用命令速查表

```bash
# 初始化仓库
git init

# 克隆仓库
git clone <url>

# 查看状态
git status

# 添加文件
git add .

# 提交
git commit -m "message"

# 推送
git push origin main

# 拉取
git pull origin main

# 新建分支
git checkout -b feature/demo

# 切换分支
git checkout main

# 查看日志
git log --oneline
```

---

## 22. 新手常见问题

### Q1：git push 失败怎么办？

常见原因：

- 远程分支不存在
- 无权限
- 本地代码未同步

处理方式：

```bash
git pull --rebase origin main
git push origin main
```

### Q2：如何回退提交？

```bash
git reset --hard HEAD~1
```

### Q3：如何查看某个文件的历史？

```bash
git log -- file.txt
```

---

## 23. 学习建议

想快速上手 GitHub，可以这样做：

1. 创建自己的 GitHub 账号
2. 新建一个仓库
3. 学会 git add / commit / push
4. 多练习分支和 PR
5. 参与开源项目
6. 维护自己的 README

---

## 24. 总结

GitHub 是开发者协作和项目管理的重要工具，它能帮助你：

- 管理代码版本
- 团队协作开发
- 提交和审查代码
- 跟踪需求问题
- 自动化部署
- 展示个人能力

掌握 GitHub 后，你会在程序开发、团队协作和职业成长中受益很多。

---

## 25. 推荐学习资源

- Git 官方文档：https://git-scm.com/doc
- GitHub 官方文档：https://docs.github.com/
- Pro Git：https://git-scm.com/book/zh/v2
- GitHub Skills：https://skills.github.com/

---

如果你愿意，我还可以继续补充：

- GitHub 实战教程（从创建仓库到部署）
- Git 命令速查表
- 团队协作流程图
- GitHub Actions 自动化部署教程
- 开源项目贡献指南

你也可以直接告诉我想要哪一种版本，我可以继续完善。
