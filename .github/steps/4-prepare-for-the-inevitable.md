# 步骤 4: 为不可避免的事情做好准备

当你在教师休息室喝着咖啡时，你突然意识到：随着越来越多的老师加入贡献，安全漏洞的出现只是时间问题。😱

这是不可避免的——哪怕维护再好的项目，也会遇到安全问题。让我们通过配置 GitHub 提供的一些工具来积极为这一天做好准备：

1. **Dependabot** - 用来监控你项目依赖的第三方库，检测依赖中的已知漏洞，自动创建拉取请求，将依赖项升级到安全版本。

1. **Code Scanning** - 分析代码库的代码，查找安全漏洞和编码错误。使用 GitHub Copilot Autofix 自动为这些警报建议修复方案。

1. **Security Policy and Private vulnerability reporting** - 提供指南和简单表单，供安全研究人员和最终用户直接向代码库维护者报告漏洞。这可以防止在修复前公开敏感问题。

> [!NOTE]
> 这只是一个快速设置指南。要更详细地设置每个服务，我们建议参考相关的 GitHub Skills 课程和/或 GitHub 文档。

## ⌨️ 实操练习：使用 Dependabot 自动更新安全补丁

通过配置 Dependabot，实现自动修复依赖漏洞，减少人工维护

> [!TIP]
> 进一步了解，可以查看 GitHub Skills 上的 [Secure Repository Supply Chain](https://github.com/skills/secure-repository-supply-chain) 课程！

1. 在顶部导航，选择 **Settings** tab。

1. 在左侧导航，选择 **Advanced Security**。

1. 找到 **Dependabot** 部分，确认或更改设置以匹配以下内容：

   - **Dependabot alerts**: `enabled`
   - **Dependabot security updates**: `enabled`
   - **Grouped security updates**: `enabled`

1. 找到 **Dependabot version updates** 并点击 **Enable** 按钮。这会打开一个编辑器来创建配置文件。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/a4d7ae19-0439-4b78-bcbf-9fce5c5410ff" />

1. 在左侧文件列表中，点击顶部 **Expand file tree** 按钮显示文件列表。在顶部，将分支切换到 `prepare-to-collaborate`。记住，我们的规则不允许直接修改 `main` 分支上的文件。

   <img width="500" alt="image" src="https://github.com/user-attachments/assets/18a3cd1a-75ab-4e5e-a4c4-efd175d91ced" />

1. 将 `package-ecosytem` 设置为 `pip`，以便 Dependabot 自动监控我们的 Python 依赖项。

   <img width="500" alt="image" src="https://github.com/user-attachments/assets/0bc90e67-4b71-4780-8272-20dc0fff5c4c" />

1. 在右上角，使用 **Commit changes...** 按钮，直接将更改提交到 `prepare-to-collaborate` 分支。

## ⌨️ 实操练习：使用 Code Scanning 检测潜在的安全风险

我们学校没有人是专业软件开发人员，所以我们启用代码扫描功能，这样如果代码里可能存在安全隐患，就能及时提醒我们。同时，我们也配置 GitHub Copilot，让它可以自动生成修复问题的 Pull Request

> [!TIP]
> 进一步了解，可以查看 GitHub Skills 上的 [Introduction to CodeQL](https://github.com/skills/introduction-to-codeql) 课程！

1. 在顶部导航，选择 **Settings** tab。

1. 在左侧导航，选择 **Advanced Security**。

1. 找到 **Code scanning** 部分，点击 **Set up** 按钮并选择 **Default** 选项以打开配置面板。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/5b3a89e5-c71a-44d9-b917-d1a21dc52181" />

1. 点击 **Enable CodeQL** 按钮接受默认配置。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/6d5f7164-d8ed-4b5d-bbcf-8aed9e7acc5d" />

1. 在 **Tools** 部分下方，确认 **Copilot Autofix** 已启用。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/b9d57e7a-f392-4c51-b137-f205a77adb79" />

## ⌨️ 实操练习：建立漏洞上报机制

现在自动化的安全机制已经准备好了，接下来我们要为“真实的人”制定一份指南，让他们在发现安全漏洞时，可以用一种安全、规范的方式进行报告

1. 在顶部导航，选择 **Settings** tab。

1. 在左侧导航，选择 **Advanced Security**。

1. 找到 **Private vulnerability reporting** 设置，确认其状态为 `enabled`。

1. 在顶部导航，点击 **Security** tab。

1. 在左侧导航，点击 **Policy** 选项。

1. 点击 **Start setup** 按钮，启动编辑器以创建 `SECURITY.md` 文件。

   <img width="350" alt="" src="https://github.com/user-attachments/assets/183b9fcc-1521-47fd-8165-b476a8ccb370"/><br/>

   <img width="350" alt="" src="https://github.com/user-attachments/assets/36c272d1-bc4a-48c8-b234-56173a214cdb"/>

1. 在左侧文件列表中，点击顶部 **Expand file tree** 按钮显示文件列表。在顶部，将分支切换到 `prepare-to-collaborate`。记住，我们的规则不允许直接修改 `main` 分支上的文件。

1. 我们将忽略提供的模板，而是使用 Mergington High School IT 部门的建议。添加以下内容：

   > 💡 **小提示** 如果你切换到一个不包含相同文件的分支，编辑器将变为空白。按下 **Restore** 按钮可以恢复上一个编辑器的内容。

   ```markdown
   # Mergington High School Security Policy

   ## Reporting a Vulnerability

   At Mergington High, we take the security of our Extra-Curricular Activities website seriously, especially
   since it contains student information. If you discover a security vulnerability, please follow these steps:

   1. **Do not** create an issue on this repository, disclose the vulnerability publicly, or discuss it with other teachers/students.
   1. In the top navigation of this repository, click the **Security** tab.
   1. In the top right, click the **Report a vulnerability** button.
   1. Fill out the provided form. It will request information like:
      - A description of the vulnerability
      - Steps to reproduce the issue
      - Potential impact on student data or website functionality
      - Suggested fix (if you have one)
   1. Email the IT Club faculty advisor at techsupport@mergingtonhigh.example.edu and inform them you have made a report. **Do not** include any vulnerability details.

   ## Response Timeline

   - We will acknowledge receipt of your report within 2 school days
   - We will provide an initial assessment within 5 school days
   - Critical issues affecting student data will be addressed immediately
   - We will create a private fork to solve the issue and invite you as a collaborator so you can see our progress and contribute.

   ## Thank You

   Your help in keeping our school's digital resources secure is greatly appreciated!
   Responsible disclosure of security vulnerabilities helps protect our entire school community.
   ```

1. 在右上角，使用 **Commit changes...** 按钮，直接将更改提交到 `prepare-to-collaborate` 分支。

1. 提交文件后，等待片刻，让 Mona 检查你的工作，提供反馈，并开启下一课的内容。
