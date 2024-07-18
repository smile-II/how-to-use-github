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

通过这些步骤，你可以成功地解决本地与远程仓库分支的冲突并推送更改。如果在执行这些步骤时遇到任何问题，请随时联系我。