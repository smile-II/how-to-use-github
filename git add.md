是的，`git add` 命令可以添加单个文件到暂存区。以下是使用 `git add` 添加单个文件的示例：

```bash
git add <file_path>
```

其中，`<file_path>` 是你要添加的文件的路径和文件名。例如，如果你有一个名为 `example.txt` 的文件在当前目录中，你可以使用以下命令将其添加到暂存区：

```bash
git add example.txt
```

如果文件在子目录中，例如 `src` 目录中的 `example.txt`，你可以使用：

```bash
git add src/example.txt
```

### 示例操作
假设你有一个名为 `main.py` 的文件，你想将它添加到暂存区，然后提交更改：

```bash
# 添加单个文件到暂存区
git add main.py

# 提交更改
git commit -m "Add main.py with initial implementation"
```

### 其他相关命令
1. **添加多个文件**：可以一次性添加多个文件，只需在 `git add` 命令后列出它们，例如：
   ```bash
   git add file1.txt file2.txt
   ```

2. **添加所有更改的文件**：使用 `.` 来添加当前目录中的所有更改文件：
   ```bash
   git add .
   ```

3. **添加特定类型的文件**：例如，添加所有 `.txt` 文件：
   ```bash
   git add *.txt
   ```

通过 `git add` 命令，可以灵活地将单个文件或多个文件添加到暂存区，根据需要进行提交。