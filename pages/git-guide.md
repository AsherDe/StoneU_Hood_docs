# Git 常用命令速查表（石大时光圈项目专用）

## 🚀 新手必备命令（仅这5个命令就能参与项目）

| 命令 | 用途 | 示例 |
|------|------|------|
| `git clone` | 获取项目代码 | `git clone https://github.com/[用户名]/ShidaTimeCircle.git` |
| `git status` | 查看当前更改状态 | `git status` |
| `git add` | 添加更改到暂存区 | `git add lib/main.dart` 或 `git add .`（添加所有） |
| `git commit` | 提交更改 | `git commit -m "添加登录页面"` |
| `git pull` | 获取最新代码 | `git pull origin main` |

## 📝 基础工作流程

### 1. 获取最新代码
```
git pull origin main
```

### 2. 创建新功能分支
```
git checkout -b feature/login-page
```

### 3. 查看你的更改
```
git status
git diff
```

### 4. 提交更改
```
git add .
git commit -m "实现登录页面UI"
```

### 5. 推送到GitHub
```
git push origin feature/login-page
```

### 6. 创建Pull Request
在GitHub网页上操作：
1. 打开仓库页面
2. 点击"Pull requests"
3. 点击"New pull request"
4. 选择你的分支和目标分支
5. 填写说明并创建

## 🛠️ 常用命令详解

### 分支操作
| 命令 | 用途 | 示例 |
|------|------|------|
| `git branch` | 列出所有本地分支 | `git branch` |
| `git checkout` | 切换分支 | `git checkout main` |
| `git checkout -b` | 创建并切换到新分支 | `git checkout -b feature/calendar` |

### 代码更新
| 命令 | 用途 | 示例 |
|------|------|------|
| `git fetch` | 获取远程更新但不合并 | `git fetch origin` |
| `git merge` | 合并分支 | `git merge feature/login` |
| `git pull` | 获取并合并更新(fetch+merge) | `git pull origin main` |

### 撤销更改
| 命令 | 用途 | 示例 |
|------|------|------|
| `git checkout -- file` | 撤销未暂存的更改 | `git checkout -- lib/main.dart` |
| `git reset HEAD file` | 取消暂存 | `git reset HEAD lib/main.dart` |
| `git reset --soft HEAD~1` | 撤销最近一次提交 | `git reset --soft HEAD~1` |

## 🆘 问题解决

### 合并冲突
如果出现合并冲突：
1. 打开有冲突的文件，查找 `<<<<<<<`, `=======`, `>>>>>>>` 标记
2. 编辑解决冲突
3. 保存文件
4. `git add .`
5. `git commit -m "解决合并冲突"`

### 取消搞砸的合并
```
git merge --abort
```

### 查看提交历史
```
git log
git log --oneline   # 简洁版本
```

## 💡 高级技巧（进阶使用）

### 临时保存工作
```
git stash save "正在开发登录功能"
git stash list
git stash apply stash@{0}
```

### 查看特定文件的历史
```
git log --follow -p -- lib/main.dart
```

### 修改最后一次提交
```
git commit --amend
```

### 交互式变基（重写历史）
```
git rebase -i HEAD~3
```

---

记住，在石大时光圈项目中，我们鼓励小步提交，经常同步，保持代码简洁。有任何Git相关问题，随时在项目群中询问！

---

**提示**：你可以将此速查表打印出来放在桌边，或者将PDF保存在手机上随时查阅。