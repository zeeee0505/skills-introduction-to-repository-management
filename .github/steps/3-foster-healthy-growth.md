# 步骤 3: 营造健康发展氛围

随着越来越多的人加入，Martinez 校长在晨会后特意找你谈话：“你的网站正成为学校的关键基础设施！我们需要确保它随着越来越多老师的加入而健康发展。你能添加一些指南来保持一切井然有序吗？”

随着课外活动网站的发展，你需要的不仅仅是技术保护和贡献指南。你还需要鼓励健康和建设性的沟通。

下面我们通过 Code of Conduct（行为准则）和 Issue Templates（问题模板）来营造健康的社区氛围。

1. **Code of Conduct** - 这是一个规范社区成员行为准则的文件。把它想象成为学生手册，其中规定了尊重他人的行为规范、如何报告非技术问题以及违反规定的后果。

2. **Issue Templates** - 问题模板要求大家按格式提问题，减少来回沟通成本

## ⌨️ 实操练习：用行为准则设定预期

让我们先为日益壮大的教师贡献者团队建立一些社区准则。

> [!TIP]
> [Contributor Covenant](https://www.contributor-covenant.org/) 是许多项目使用的流行行为准则。

1. 在顶部导航中，返回 **Code** 选项卡。确保你在 `prepare-to-collaborate` 分支上。

1. 在顶部目录，创建一个名为 `CODE_OF_CONDUCT.md` 的新文件（区分大小写）。

1. 添加行为准则内容。

   ```markdown
   # Mergington High School Code of Conduct

   ## Our Pledge

   In the interest of fostering an open and welcoming environment for
   our school community, we as contributors and maintainers pledge to
   make participation in the Extra-Curricular Activities project a
   respectful and harassment-free experience for everyone.

   ## Our Standards

   Examples of behavior that contributes to creating a positive environment include:

   - Using welcoming and inclusive language
   - Being respectful of differing viewpoints and experiences
   - Gracefully accepting constructive criticism
   - Focusing on what is best for the students and the school community
   - Showing empathy towards other community members

   Examples of unacceptable behavior include:

   - The use of inappropriate language or imagery
   - Trolling, insulting comments, and personal attacks
   - Public or private harassment
   - Publishing others' private information without explicit permission
   - Other conduct which could reasonably be considered inappropriate in a school setting

   ## Responsibilities

   Project maintainers are responsible for clarifying the standards of
   acceptable behavior and are expected to take appropriate and fair
   corrective action in response to any instances of unacceptable behavior.

   Project maintainers have the right and responsibility to remove, edit,
   or reject comments, commits, code, issues, and other contributions that
   are not aligned to this Code of Conduct.

   ## Scope

   This Code of Conduct applies both within project spaces and in public spaces
   when an individual is representing the project or the school. Examples of
   representing the project include using an official project email address,
   posting via an official social media account, or acting as an appointed
   representative at an online or offline event.

   ## Enforcement

   Instances of abusive, harassing, or otherwise unacceptable behavior may be
   reported to the IT Club faculty advisor. All complaints will be reviewed and
   investigated promptly and fairly.

   Project maintainers who do not follow or enforce the Code of Conduct in good faith may
   face temporary or permanent repercussions as determined by the school administration.

   ## Attribution

   This Code of Conduct is adapted from the [Contributor Covenant](https://www.contributor-covenant.org),
   version 1.4, available at [https://www.contributor-covenant.org/version/1/4/code-of-conduct.html](https://www.contributor-covenant.org/version/1/4/code-of-conduct.html)
   ```

1. 在右上角，使用 **Commit changes...** 按钮，将你的修改直接提交到 `prepare-to-collaborate` 分支。

## ⌨️ 实操练习：通过问题模板提升沟通效率

现在让我们创建 Issue 模板，以便其他教师可以以标准化的方式报告错误或提出新需求。

> [!TIP]
> 建议你可以考虑用一下正在测试中的 [Issue 表单功能](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms)，它能让大家提问题的时候更方便、更清晰。

1. 在顶部导航栏，选择 **Settings** tab。

1. 找到 **Features** 部分，确认 **Issues** 已启用。

   <img width="350" alt="" src="https://github.com/user-attachments/assets/dafb976b-4b8c-4c5e-8989-04d3e7bbe70d" />

1. 点击 **Set up templates** 按钮进入问题模板编辑器。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/bd94af1e-d564-472f-a435-f12fa1bf3b5c" />

1. 点击 **Add template** 下拉菜单，选择 **Bug report**。

   <img width="350" alt="" src="https://github.com/user-attachments/assets/baee263d-b233-4029-b629-9544eacf1e27" />

1. 点击 **Preview and edit** 按钮查看当前模板。点击 **Edit icon** (铅笔) 图标进行编辑。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/1c8500f7-10b2-406b-9385-d5b9480e2f71" /><br/>

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/77e312e2-af3c-4015-94f0-b1cf7409cc40" /><br/>

   <img width="700" alt="image" src="https://github.com/user-attachments/assets/c2aecd6e-d021-4149-b088-7cbf883a7e33" />

1. (可选) 为了让我们的学生和老师更省心，可以删除关于桌面和手机详情的部分。

1. 对 "Feature request" 模板重复上述步骤。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/6456e261-fcd8-4845-b1ab-f2c2d5883c77" />

1. 准备好模板后，让我们提交它们。点击右上角的 **Propose changes** 按钮。输入描述，并将分支设置为 `add-issue-templates`，然后点击 **Commit changes**。你可以忽略自动创建的拉取请求。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/a00a3740-ce0c-430c-9541-e56b7d9b45d6" />

1. 提交文件后，等待片刻，让 Mona 检查你的工作、提供反馈并开启下一课。

> [!TIP]
> 你有没有注意到，现在你正在 2 个分支上并行工作？这正是多人协作时的真实写照。
