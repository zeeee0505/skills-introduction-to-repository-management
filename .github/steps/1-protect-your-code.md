# 步骤 1: 保护你的代码

假设你为 Mergington 高中开发了一个管理课外活动的网站，这个网站突然火了起来，原本只是一个简单的报名工具，现在已经成了学校一半社团活动的核心平台 📚✨。

校长 Martinez 对你的成果非常满意，甚至在教职工会议上宣布：所有社团都要用这个网站！

这当然是好事，但你心里也有点紧张——万一有人不小心改坏了代码，偏偏又是在秋季活动展前夕，那可就麻烦了 😰

随着越来越多老师加入协作，现在必须给仓库加点“安全措施”。好在 GitHub 提供了不少工具来帮你做到这一点：

## 关键保护手段

1. **仓库规则集**（Repository Rulesets）：可以限制一些高风险操作，比如：

   - 不能直接往重要分支（如 main）提交代码
   - 防止分支被删除或重命名
   - 禁止强制推送（避免历史被覆盖）
   - 以及更多控制策略

1. **`.gitignore`** - 这是一个“忽略清单”，告诉 Git 哪些文件不应该被纳入版本控制，例如：

   - 临时文件
   - 包含密码或敏感信息的配置文件
   - 其他开发者不需要的系统文件

> [!TIP]
> 可以把这些设置想象成学校校刊的编辑流程：各个学生委员会负责拍照和撰写文章，最后由校刊主编调整排版，确保整体流畅，再由老师/顾问签字确认内容合适。

## ⌨️ 实操练习: (可选) 体验一下网站功能

<details>
<summary>展示步骤</summary>

在[GitHub Copilot 入门指南](https://github.com/skills/getting-started-with-github-copilot/) 课程中，我们开发了这个课外活动网站。你可以按照以下步骤启动开发环境并进行体验。

> ❗ **重要:** 这一部分主要是为了让你体验课外活动网站，**不是**完成本次练习的必要条件。如果你愿意，可以跳过此活动。

1. 创建在线开发环境（Codespace）：右键点击下面的按钮，在新标签页中打开**创建 Codespace** 页面。使用默认配置。

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. 等待一段时间，让环境准备就绪。它会自动安装所有需要的依赖库和服务。

1. 确认 **GitHub Copilot** 和 **Python** 插件已安装并启用。

   <img width="300" alt="copilot extension for VS Code" src="https://github.com/user-attachments/assets/ef1ef984-17fc-4b20-a9a6-65a866def468" /><br/>
   <img width="300" alt="python extension for VS Code" src="https://github.com/user-attachments/assets/3040c0f5-1658-47e2-a439-20504a384f77" />

1. 运行项目：在左侧边栏中，选择 **Run and Debug** 选项卡，然后按 **Start Debugging** 图标。

   <details>
   <summary>📸 查看截图</summary><br/>

   <img width="300" alt="run and debug" src="https://github.com/user-attachments/assets/50b27f2a-5eab-4827-9343-ab5bce62357e" />

   </details>

   <details>
   <summary>🤷 遇到问题？</summary><br/>

   如果**Run and Debug**区域为空，请尝试重新加载VS Code：打开命令面板（`Ctrl`+`Shift`+`P`）并搜索 `Developer: Reload Window`。

   <img width="300" alt="empty run and debug panel" src="https://github.com/user-attachments/assets/0dbf1407-3a97-401a-a630-f462697082d6" />

   </details>

1. 在 **Ports** tab 中找到网页访问地址，打开链接确认是否能正常访问。

   <details>
   <summary>📸 查看截图</summary><br/>

   <img width="350" alt="ports tab" src="https://github.com/user-attachments/assets/8d24d6b5-202d-4109-8174-2f0d1e4d8d44" />

   ![Screenshot of Mergington High School WebApp](https://github.com/user-attachments/assets/5e1e7c1e-1b0e-4378-a5af-a266763e6544)

   </details>

</details>

## ⌨️ 实操练习：添加分支保护规则

首先，让我们添加一些保护措施，以防止有人意外破坏系统。

1. 如果有必要，打开另一个标签页并导航到此仓库。进入仓库的 **Settings（设置）** 页面

1. 在左侧导航中，展开 **Rules** 区域，然后选择 **Rulesets**。

1. 单击 **New ruleset** 按钮，然后选择 **New branch ruleset**。

   <img width="250" alt="image" src="https://github.com/user-attachments/assets/1e9fd519-1421-4d6b-b654-a3fe53a8fb75" />

1. 设置 **Ruleset Name** 为 `Protect main`，并将 **Enforcement status** 设为 `Active`。

   <img width="250" alt="image" src="https://github.com/user-attachments/assets/ce30fd34-39b5-4e22-b348-4af61fd05cd1" />

1. 找到 **Targets** 部分，使用 **Add target** 下拉菜单添加 2 个条目：

   1. 添加 **Include default branch** 选项，包含默认分支（防止切换默认分支绕过规则）

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/217263cc-d5c2-4ac0-b03c-a72494e5c812" />

   1. 使用 **include by pattern** 选项，并输入模式 `main`

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/968c9ed8-b051-44eb-af42-d99670ad31fd" />

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/ddc52767-d93e-4c9e-a77a-90c3b5c08fb5" />

1. 找到 **Rules** 部分，确保以下选项已选中。

   - [x] Restrict deletions (限制删除分支)
   - [x] Require a pull request before merging (合并前需要拉取请求)
     - Required approvals: `0` (需要的审批数量: `0`)
     - [x] Require review from Code Owners (需要代码所有者审查)
   - [x] Block force pushes (禁止强制推送)

1. 滚动到底部，单击 **Create** 按钮保存规则集。

## ⌨️ 实操练习：创建 `.gitignore` 文件

我们知道很多老师使用不同的工具，为了避免大家提交不必要的文件，可以创建一个`.gitignore`文件来告诉 Git。

1. 在顶部导航栏，返回 **Code** 选项卡，确认你位于 `main` 分支上。

1. 在文件列表上方，点击 **Add file** 下拉菜单，选择 **Create new file** 新建文件。

   <img width="300" alt="New file button" src="https://github.com/user-attachments/assets/8f3f8da8-1471-485a-9df5-8c03ecba2d8e"/>

1. 输入文件名 `.gitignore`。我们将先忽略模板选择器，稍后再自定义。将以下示例内容复制到文件中。

   <img width="350" alt="新文件预览" src="https://github.com/user-attachments/assets/580d1a63-a264-4d44-8901-50ad708b8822"/>

   ```gitignore
   # Python backend for club management
   __pycache__/
   *.py[cod]      # Python compiled files
   *$py.class
   *.so
   .Python
   env/
   .env           # Where database passwords are stored
   venv/          # Virtual environment for testing
   .venv

   # Teacher IDE settings
   .vscode/       # Ms. Rodriguez uses VS Code
   .idea/         # Mr. Chen uses PyCharm

   # Local development & testing
   instance/
   .pytest_cache/
   .coverage      # Test coverage reports
   htmlcov/

   # Staff computer files
   .DS_Store      # For teachers with Macs
   Thumbs.db      # For teachers with Windows
   ```

1. 在页面右侧，选择 **Commit changes...** 按钮。请注意，我们无法直接提交到 `main` 分支！这说明我们的规则集正在起作用，太棒了！

   <img width="400" alt="image" src="https://github.com/user-attachments/assets/4e85948d-75c8-4c13-8ddd-4707bf9b0805" />

1. 在输入框中，输入 `prepare-to-collaborate` 作为分支名称，然后点击 **Propose changes** 按钮。你会跳转到一个新页面，以发起一个新的拉取请求。

1. 设置标题为 `Prepare to collaborate`，然后点击 **Create pull request** 按钮。**请不要立即合并**，因为我们还要添加更多与协作相关的更改。

1. 文件已提交，Mona 会自动检查你的工作。稍等片刻，她会在评论中给出反馈与下一步任务。

> [!TIP]
> GitHub 官方提供了大量现成的 `.gitignore` 模板，适用于不同语言和项目类型，可以在 [github/gitignore](https://github.com/github/gitignore) 仓库中查看。

<details>
<summary>🤷 遇到问题?</summary><br/>

确保你将 `.gitignore` 文件提交到了 `prepare-to-collaborate` 分支。文件名和分支名都要完全匹配！

</details>
