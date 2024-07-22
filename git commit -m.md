抱歉，确实应该包括 `update` 类型的提交。`update` 类型通常用于一般性更新，不属于 `feat`、`fix` 等明确类型的提交。下面是补充了 `update` 类型的提交规范描述：

### 提交类型
- **feat**: 增加新功能（feature）
- **fix**: 修复 bug
- **docs**: 只修改文档
- **style**: 不影响代码含义的改动（空白、格式化、缺少分号等）
- **refactor**: 代码重构（既不是新增功能，也不是修改 bug 的代码变动）
- **perf**: 改善性能的代码变动
- **test**: 增加测试
- **chore**: 对构建过程或辅助工具和库的更改（不影响源文件、测试用例）
- **update**: 一般性更新，不属于上述类型的改动

### 提交消息格式
提交消息一般分为三个部分：类型、简短描述和详细描述。

1. **类型（type）**:
   用于描述提交的类型，例如 `feat`、`fix`、`update` 等。
   
2. **简短描述（subject）**:
   用一句话简要描述提交的内容，长度建议控制在50个字符以内。

3. **详细描述（body，可选）**:
   详细描述代码变动的内容，解释为什么进行这些变动及其影响。


# 提交类型示例

### 增加新功能
```plaintext
feat: Add user profile page

Implemented a new user profile page where users can view and edit their personal information.
```

### 修复 bug
```plaintext
fix: Resolve login redirect issue

Fixed a bug where users were not redirected to the dashboard after logging in.
```

### 更新文档
```plaintext
docs: Add API usage examples

Included examples in the README for using the new API endpoints.
```

### 代码格式化
```plaintext
style: Reformat code with Prettier

Formatted the codebase using Prettier to ensure consistent code style.
```

### 代码重构
```plaintext
refactor: Simplify authentication logic

Refactored the authentication logic for better readability and maintainability.
```

### 性能优化
```plaintext
perf: Optimize database queries

Improved the performance of user data retrieval by optimizing database queries.
```

### 增加测试
```plaintext
test: Add tests for user registration

Added unit tests for the user registration process to ensure reliability.
```

### 构建工具和依赖更新
```plaintext
chore: Update project dependencies

Updated several dependencies to their latest versions to fix security vulnerabilities.
```

### 一般性更新
```plaintext
update: Update third-party libraries

Updated lodash and moment.js to their latest stable versions to improve security and performance.
```

这个例子涵盖了常见的提交类型，并提供了简短的提交消息示例。你可以根据这些模板来编写自己的提交消息。