# STM32项目Git仓库操作说明

## 操作概述

本文档记录了为STM32项目集合创建Git仓库并推送到远程仓库的完整操作过程。

## 已完成的操作

### 1. 初始化Git仓库
```bash
cd d:\Clion_Stm32
git init
```
**结果**: 成功初始化Git仓库（重新初始化了已存在的仓库）

### 2. 创建.gitignore文件
创建了适合STM32项目的`.gitignore`文件，包含以下主要排除项：
- 编译输出文件（*.o, *.elf, *.bin, *.hex等）
- Keil MDK-ARM生成的文件
- CLion/CMake生成的文件
- IDE配置文件
- 调试文件
- 临时文件和备份文件
- 敏感信息文件（密钥、证书等）

### 3. 创建README.md文档
创建了详细的项目说明文档，包含：
- 项目概述和结构
- 各子项目详细说明
- 开发环境要求
- 快速开始指南
- 代码规范
- 贡献指南

### 4. 添加文件到Git
```bash
git add .
```
**结果**: 成功添加所有项目文件到Git暂存区

### 5. 提交更改
```bash
git commit -m "初始提交：添加STM32项目集合

- 包含LED、Blik、01_RTOS三个项目
- 添加完整的.gitignore配置
- 添加详细的README.md文档
- 支持CLion和Keil开发环境"
```
**结果**: 成功提交，创建了初始版本

## 待完成的操作

### 6. 添加远程仓库
您需要先在Git托管平台（如GitHub、GitLab、Gitee等）创建一个新的仓库，然后执行：

```bash
# 添加远程仓库（请替换为您的实际仓库地址）
git remote add origin https://github.com/用户名/仓库名.git

# 或者使用SSH（推荐）
git remote add origin git@github.com:用户名/仓库名.git
```

### 7. 推送到远程仓库
```bash
# 推送主分支到远程仓库
git push -u origin main

# 如果远程仓库使用master分支
git branch -M main  # 重命名当前分支为main
git push -u origin main
```

## 推荐的Git托管平台

### GitHub
- **地址**: https://github.com
- **优点**: 全球最大的代码托管平台，社区活跃
- **适用**: 开源项目、个人项目

### GitLab
- **地址**: https://gitlab.com
- **优点**: 功能完整，支持私有仓库
- **适用**: 企业项目、团队协作

### Gitee（码云）
- **地址**: https://gitee.com
- **优点**: 国内访问速度快，支持中文
- **适用**: 国内开发者、中文项目

## 创建远程仓库的步骤

### 在GitHub上创建仓库
1. 登录GitHub账户
2. 点击右上角的"+"号，选择"New repository"
3. 填写仓库信息：
   - **Repository name**: `STM32-Projects`（或您喜欢的名称）
   - **Description**: `STM32嵌入式开发项目集合`
   - **Visibility**: 选择Public或Private
   - **不要**勾选"Initialize this repository with a README"（因为我们已经有了）
4. 点击"Create repository"
5. 复制仓库的HTTPS或SSH地址

### 在GitLab上创建仓库
1. 登录GitLab账户
2. 点击"New project"
3. 选择"Create blank project"
4. 填写项目信息并创建
5. 复制仓库地址

### 在Gitee上创建仓库
1. 登录Gitee账户
2. 点击右上角的"+"号，选择"新建仓库"
3. 填写仓库信息并创建
4. 复制仓库地址

## 完整的推送命令示例

假设您在GitHub上创建了仓库，完整的推送过程如下：

```bash
# 1. 添加远程仓库（替换为您的实际地址）
git remote add origin https://github.com/yourusername/STM32-Projects.git

# 2. 验证远程仓库配置
git remote -v

# 3. 推送到远程仓库
git push -u origin main

# 如果遇到分支名称问题，可能需要：
git branch -M main
git push -u origin main
```

## 后续维护操作

### 日常提交流程
```bash
# 1. 查看文件状态
git status

# 2. 添加修改的文件
git add .
# 或添加特定文件
git add 文件名

# 3. 提交更改
git commit -m "描述性的提交信息"

# 4. 推送到远程仓库
git push
```

### 分支管理
```bash
# 创建新分支
git checkout -b feature/新功能名称

# 切换分支
git checkout 分支名

# 合并分支
git checkout main
git merge feature/新功能名称

# 删除分支
git branch -d feature/新功能名称
```

### 查看历史
```bash
# 查看提交历史
git log --oneline

# 查看文件修改历史
git log --follow 文件名

# 查看差异
git diff
```

## 注意事项

1. **敏感信息保护**: 确保不要提交密码、密钥等敏感信息
2. **文件大小限制**: 大多数Git平台对单个文件有大小限制（通常100MB）
3. **提交信息规范**: 使用清晰、描述性的提交信息
4. **定期备份**: 定期推送到远程仓库以防止数据丢失
5. **分支策略**: 对于团队开发，建议使用Git Flow或GitHub Flow工作流

## 故障排除

### 常见问题及解决方案

#### 1. 推送被拒绝
```bash
# 如果远程仓库有更新，先拉取
git pull origin main
# 然后再推送
git push origin main
```

#### 2. 认证失败
- 检查用户名和密码
- 对于GitHub，可能需要使用Personal Access Token
- 考虑配置SSH密钥

#### 3. 文件过大
```bash
# 使用Git LFS处理大文件
git lfs track "*.bin"
git add .gitattributes
```

#### 4. 中文文件名问题
```bash
# 配置Git支持中文文件名
git config core.quotepath false
```

## 总结

本次操作成功完成了：
- ✅ Git仓库初始化
- ✅ 创建.gitignore文件
- ✅ 创建README.md文档
- ✅ 添加所有项目文件
- ✅ 完成初始提交
- ⏳ 等待添加远程仓库
- ⏳ 等待推送到远程仓库

请按照上述说明完成远程仓库的创建和推送操作。如有任何问题，请参考故障排除部分或联系技术支持。