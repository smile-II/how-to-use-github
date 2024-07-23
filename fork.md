当你 fork 别人的项目时，以下事情会发生：

1. **创建一个副本**：GitHub 会在你的账户下创建一个原始项目的副本。这是一个完全独立的仓库，你可以对其进行修改而不会影响原始项目。
   
2. **保持连接**：你的 fork 仓库和原始项目之间会保留一个连接，方便你将原始项目中的更改同步到你的副本中。

3. **独立开发**：你可以在自己的仓库中独立地进行开发、提交代码、创建分支等操作，完全不受原始项目的影响。

4. **拉取请求**：当你对项目进行修改并希望将这些更改合并回原始项目时，你可以创建一个 pull request（PR）。项目维护者会审查你的更改，并决定是否合并到他们的项目中。

### 具体步骤

1. **Fork 项目**
   - 在 GitHub 上，找到你要 fork 的项目。
   - 点击页面右上角的 `Fork` 按钮。
   - GitHub 会在你的账户下创建这个项目的副本。

2. **克隆仓库**
   - 在你的 GitHub 账户下找到 fork 的仓库。
   - 点击 `Code` 按钮，复制仓库的 URL。
   - 在本地机器上运行以下命令来克隆仓库：
     ```bash
     git clone <your-forked-repo-url>
     ```

3. **设置上游仓库**
   - 在克隆的仓库目录中，运行以下命令将原始项目设置为 `upstream` 远程仓库：
     ```bash
     cd <your-forked-repo>
     git remote add upstream <original-repo-url>
     ```

4. **保持你的 fork 同步**
   - 定期从原始项目拉取更改并合并到你的 fork 中：
     ```bash
     git fetch upstream
     git checkout main  # 或者 master，根据原始项目的默认分支
     git merge upstream/main  # 或者 upstream/master
     ```

5. **提交和推送更改**
   - 在你的 fork 中进行修改并提交：
     ```bash
     git add .
     git commit -m "Your commit message"
     git push origin main  # 或者你的分支名
     ```

6. **创建 Pull Request**
   - 在你的 GitHub 仓库页面上，点击 `New pull request` 按钮。
   - 选择要合并的分支，并提交 pull request。
   - 原始项目的维护者会收到通知并审查你的更改。

### 示例
假设你 fork 了一个项目 `example-repo`，以下是具体步骤的示例：

1. Fork 项目
2. 克隆你的 fork
   ```bash
   git clone https://github.com/yourusername/example-repo.git
   cd example-repo
   ```
3. 设置上游仓库
   ```bash
   git remote add upstream https://github.com/originalusername/example-repo.git
   ```
4. 保持同步
   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```
5. 提交和推送更改
   ```bash
   # 进行更改...
   git add .
   git commit -m "Fixed a bug in the data processing script"
   git push origin main
   ```
6. 创建 Pull Request
   - 在 GitHub 上打开你的 fork 仓库页面，点击 `New pull request`，选择你刚刚提交的分支，提交 PR。

通过这些步骤，你可以在不影响原始项目的情况下进行独立开发，并且能够将你的贡献提交给原始项目。