### Git 操作手册：解决本地与远程仓库分支冲突并推送更改

#### 1. 切换到本地 `main` 分支
确保你当前在本地的 `main` 分支上：
```bash
git checkout main
```

#### 2. 添加并提交本地更改
确保所有本地更改已经被添加并提交：
```bash
git add .
git commit -m "Save local changes"
```

#### 3. 拉取远程分支的更改并应用到本地
使用 `--rebase` 选项将远程分支的更改拉取到本地：
```bash
git pull origin main --rebase
```

- 如果没有冲突，Git 会自动完成 rebase 并更新本地分支。
- 如果有冲突，Git 会提示你解决冲突。

#### 4. 解决冲突（如果有的话）
手动解决所有冲突，然后使用以下命令继续 rebase：
```bash
git add .
git rebase --continue
```

#### 5. 推送本地更改到远程仓库
解决所有冲突并完成 rebase 后，推送本地更改到远程仓库：
```bash
git push origin main
```

#### 6. 处理可能的错误

- 如果在推送过程中遇到错误，提示远程仓库有更新且需要先拉取更改：
  ```bash
  ! [rejected]        main -> main (non-fast-forward)
  error: failed to push some refs to 'github.com:smile-II/Whic-is-bigger-9.9-or-9.11.git'
  ```

- 重新拉取远程更改并处理冲突后再推送：
  ```bash
  git pull origin main --rebase
  git push origin main
  ```

- 如果需要强制推送：
  ```bash
  git push origin main --force
  ```

### 注意事项
- **拉取远程分支的更改不会删除本地文件**，但可能会覆盖本地文件中的更改，特别是那些已经被追踪和提交到 Git 中的文件。
- **未被追踪的文件** 不会受到影响。
- **冲突处理**：如果远程分支中的更改与本地更改冲突，你需要手动解决冲突。

### 取消当前合并操作
如果在合并过程中遇到问题，可以取消当前合并操作并恢复到合并前的状态：
```bash
git merge --abort
```

### 清理未跟踪的文件和目录
如果需要清理未跟踪的文件和目录，请确保已经备份所有重要的文件，然后执行以下命令：
```bash
git clean -fd
```


# `git commit`和`git push`是Git中两个重要的操作，它们的作用和区别如下：

### `git commit`

`git commit`是将你的更改保存到本地仓库的操作。

1. **本地操作**：`git commit`只在你的本地仓库中运行，它不会影响远程仓库。
2. **生成快照**：每次你执行`git commit`，Git都会为你的项目创建一个新的快照（commit），包含所有被跟踪文件的当前状态。
3. **需要消息**：通常你需要为每次提交添加一条消息，描述这次更改的内容，以便后续查阅。例如：`git commit -m "use markdown"`。

### `git push`

`git push`是将本地仓库的更改上传到远程仓库的操作。

1. **远程操作**：`git push`将你本地仓库中的所有提交（commit）推送到远程仓库，使得远程仓库与本地仓库保持同步。
2. **同步更新**：执行`git push`后，其他协作成员可以通过拉取（pull）或克隆（clone）远程仓库来获取你的更改。
3. **指定远程和分支**：通常你需要指定远程仓库和分支。例如：`git push origin main`。

### 工作流程

一个常见的Git工作流程如下：

1. **修改文件**：在工作区修改文件。
2. **暂存更改**：使用`git add`命令将更改添加到暂存区。例如：`git add .`。
3. **提交更改**：使用`git commit`命令将暂存区的更改提交到本地仓库。例如：`git commit -m "commit message"`。
4. **推送更改**：使用`git push`命令将本地仓库的更改推送到远程仓库。例如：`git push origin main`。

### 举例

假设你在本地修改了README.md文件，并想将这些更改提交并推送到远程仓库：

1. **查看状态**：
   ```bash
   git status
   ```

2. **暂存更改**：
   ```bash
   git add README.md
   ```

3. **提交更改**：
   ```bash
   git commit -m "Update README with new links"
   ```

4. **推送更改**：
   ```bash
   git push origin main
   ```

### 总结

- **`git commit`**：将你的更改保存到本地仓库。
- **`git push`**：将本地仓库的更改上传到远程仓库。




# 只修改一个文件

如果你只修改了一个文件，工作流程依然遵循Git的标准流程。下面是详细步骤：

### 1. 修改文件
你在工作区对一个文件进行了修改，比如修改了`README.md`文件。

### 2. 查看状态
查看当前修改的文件状态，确认哪些文件被修改了。

```bash
git status
```

输出会显示哪些文件被修改了，哪些文件被暂存了，哪些文件还没有被跟踪。

### 3. 暂存更改
将修改的文件添加到暂存区。

```bash
git add README.md
```

### 4. 提交更改
将暂存区的更改提交到本地仓库，生成一个新的提交记录。

```bash
git commit -m "Updated README with new links"
```

### 5. 推送更改
将本地仓库的更改推送到远程仓库。

```bash
git push origin main
```

### 完整示例

假设你在本地修改了`README.md`文件，具体的工作流程如下：

```bash
# 查看状态
git status

# 输出示例：
# On branch main
# Your branch is up to date with 'origin/main'.
#
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git restore <file>..." to discard changes in working directory)
# 	modified:   README.md
#
# no changes added to commit (use "git add" and/or "git commit -a")

# 暂存更改
git add README.md

# 查看状态，确认文件已被暂存
git status

# 输出示例：
# On branch main
# Your branch is up to date with 'origin/main'.
#
# Changes to be committed:
#   (use "git restore --staged <file>..." to unstage)
# 	modified:   README.md

# 提交更改
git commit -m "Updated README with new links"

# 输出示例：
# [main 04c944a] Updated README with new links
#  1 file changed, 2 insertions(+), 1 deletion(-)

# 推送更改到远程仓库
git push origin main

# 输出示例：
# Enumerating objects: 6, done.
# Counting objects: 100% (6/6), done.
# Delta compression using up to 32 threads
# Compressing objects: 100% (4/4), done.
# Writing objects: 100% (4/4), 758 bytes | 758.00 KiB/s, done.
# Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
# To https://github.com/smile-II/how-to-use-github.git
#    b11fd9c..04c944a  main -> main
```

### 关键点解释

- **`git status`**：查看当前工作区和暂存区的状态。
- **`git add <file>`**：将修改的文件添加到暂存区。
- **`git commit -m "message"`**：将暂存区的更改提交到本地仓库，并添加提交信息。
- **`git push origin main`**：将本地仓库的提交推送到远程仓库的`main`分支。


要将你的Git远程仓库URL更改为使用SSH，你可以使用以下命令：

1. 复制你的SSH远程仓库URL。例如，假设你的GitHub用户名是 `smile-II`，仓库名是 `Whic-is-bigger-9.9-or-9.11`，那么SSH URL是 `git@github.com:smile-II/Whic-is-bigger-9.9-or-9.11.git`。

2. 使用以下命令将远程仓库URL从HTTPS更改为SSH：

```bash
git remote set-url origin git@github.com:smile-II/Whic-is-bigger-9.9-or-9.11.git
```

这是完整的过程：

1. 打开终端或命令提示符。
2. 进入你的Git项目目录。
3. 运行以下命令：

```bash
git remote set-url origin git@github.com:smile-II/Whic-is-bigger-9.9-or-9.11.git
```

然后你可以尝试再次推送代码：

```bash
git push origin main
```

请确保你的SSH密钥已正确配置并添加到你的GitHub账户中。如果你还没有配置SSH密钥，可以按照之前提供的步骤生成并添加SSH密钥。