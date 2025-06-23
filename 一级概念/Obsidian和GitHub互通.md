以下是使用 **GitHub + Obsidian 管理研究生资料** 的关键步骤总结


### **一、基础环境搭建**  
1. **工具准备**  
   - 安装 **Obsidian**（笔记管理）、**Git**（版本控制），注册 **GitHub 账号**（远程存储）。  
   - 验证 Git 环境：终端执行 `git --version` ，确认安装成功。  

2. **GitHub 仓库创建**  
   - 新建 GitHub 仓库（如 `postgraduate` ），初始化 `README.md` 和 `.gitignore`（选 Markdown 模板，过滤冗余文件）。  


### **二、本地仓库与远程关联**  
1. **初始化本地 Git 仓库**  
   - 在 Obsidian Vault（笔记文件夹，如 `postgraduate` ）执行：  
     ```bash
     git init  # 初始化本地仓库
     git status  # 查看仓库状态（确认 Untracked files）
     ```  

2. **关联 GitHub 远程仓库**  
   - 复制 GitHub 仓库 HTTPS 地址，终端执行：  
     ```bash
     git remote add origin https://github.com/你的用户名/仓库名.git  # 关联远程
     git remote -v  # 验证关联（显示 fetch/push 地址）
     ```  


### **三、核心配置与首次同步**  
1. **Git 身份配置**  
   - 终端执行（替换为你的 GitHub 邮箱/用户名）：  
     ```bash
     git config --global user.email "你的邮箱"  
     git config --global user.name "你的 GitHub 用户名"  
     ```  

2. **提交并推送首次内容**  
   - 暂存文件 → 提交 → 推送（解决分支追踪问题）：  
     ```bash
     git add .  # 暂存所有文件（或指定文件）
     git commit -m "初始化：Obsidian 笔记仓库"  # 提交并写说明
     git push --set-upstream origin master  # 推送并设置上游分支
     ```  


### **四、日常使用与协同**  
1. **Obsidian 与 Git 联动**  
   - 安装 **Obsidian Git 插件**，配置自动提交/拉取，日常编辑后：  
     - 命令面板执行 `Git: Commit-and-sync` ，一键提交+推送。  

2. **分支管理（可选）**  
   - 开发新内容时创建分支（如研究子方向、论文草稿）：  
     ```bash
     git checkout -b 新分支名  # 创建并切换分支
     git push --set-upstream origin 新分支名  # 推送新分支到远程
     ```  

3. **版本回溯与协作**  
   - 查看历史：`Git: Show log`（插件）或 `git log`（终端）。  
   - 协同开发：通过 GitHub Pull Request 合并分支，解决冲突。  


### **五、常见问题解决**  
- **分支不一致**：GitHub 默认 `main` 分支，本地是 `master` 时，统一分支名（如切换默认分支为 `master` ，或本地创建 `main` 并合并）。  
- **推送失败**：检查 Git 身份配置、远程关联、提交记录（确保有 `commit` 后再 `push` ）。  


这套流程覆盖了 **“本地笔记 → Git 版本控制 → GitHub 远程备份”** 的完整链路，既保证资料安全（多端同步、版本回溯），又能结构化管理研究内容（Obsidian 双向链接、标签体系），长期使用可沉淀为个人知识体系的“第二大脑” 。