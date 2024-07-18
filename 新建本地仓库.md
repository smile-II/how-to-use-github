以下是如何在本地新建一个 Git 仓库并将其推送到 GitHub 的详细步骤：

### 1. 创建一个新的 Git 仓库

#### 在本地创建一个新目录并初始化 Git 仓库
```bash
mkdir my-new-repo
cd my-new-repo
git init
```

### 2. 添加文件并提交

#### 创建一个 README 文件并添加一些内容
```bash
echo "# My New Repo" >> README.md
```

#### 添加文件到 Git
```bash
git add README.md
```

#### 提交文件
```bash
git commit -m "Initial commit"
```

### 3. 在 GitHub 上创建一个新的仓库

1. 登录到 [GitHub](https://github.com)。
2. 点击右上角的“+”按钮，然后选择“New repository”。
3. 输入你的仓库名称（例如 `my-new-repo`），并填写其他相关信息。
4. 点击“Create repository”按钮。

### 4. 将本地仓库与 GitHub 仓库关联

#### 复制 GitHub 仓库的 URL
例如：`https://github.com/your-username/my-new-repo.git` 或 `git@github.com:your-username/my-new-repo.git`

#### 将远程仓库添加为 `origin`
```bash
git remote add origin https://github.com/your-username/my-new-repo.git
```

#### 如果链接错了，重置链接
```bash
git remote set-url origin https://github.com/smile-II/how-to-use-github.git
```



### 5. 推送本地仓库到 GitHub

#### 将本地 `main` 分支推送到远程 `main` 分支
```bash
git push -u origin main
```

### 6. 检查推送结果

#### 在 GitHub 上查看仓库
1. 打开浏览器，访问你的 GitHub 主页。
2. 点击你的新仓库 `my-new-repo`，查看是否包含你刚才提交的文件。

### 完整的操作示例

1. 创建并初始化 Git 仓库：
   ```bash
   mkdir my-new-repo
   cd my-new-repo
   git init
   ```

2. 创建 README 文件并提交：
   ```bash
   echo "# My New Repo" >> README.md
   git add README.md
   git commit -m "Initial commit"
   ```

3. 创建 GitHub 仓库，并添加远程仓库：
   ```bash
   git remote add origin https://github.com/your-username/my-new-repo.git
   ```

4. 推送本地仓库到 GitHub：
   ```bash
   git push -u origin main
   ```

通过这些步骤，你应该能够成功地将本地创建的 Git 仓库推送到 GitHub。如果在执行这些步骤时遇到任何问题，请告诉我，我可以提供进一步的帮助。

```python
反引号 在键盘数字1的左边```
```