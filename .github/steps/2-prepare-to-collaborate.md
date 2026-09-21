# 步骤 2: 为协作做好准备

你的校园网站现在越来越受欢迎了！在上次教职工会议展示之后，艺术社的 Rodriguez 老师和象棋社的 Chen 老师都兴奋地找到了你，提出了不少新想法：

- Rodriguez 老师想增加一个**作品展示画廊**
- Chen 老师则希望为象棋和体育活动添加一个比赛赛程系统！ 🎨♟️

虽然你很高兴大家的热情，但你也意识到需要在他们开始修改代码之前设定一些规则。你可不想在春假来临前夕，因为代码冲突导致注册系统崩溃！

让其他老师加入到 Mergington 高中的项目中，意味着你需要考虑如何让大家协同工作而不破坏彼此的代码。

**Colaboradores（协作者）** 就是你通过仓库设置授权、可以修改项目代码的人。

- 允许他人参与开发，同时仍然保护仓库的关键设置
- 个人仓库权限简单。组织仓库权限更细致灵活，如读、写、维护和管理。

为了让多人协作不混乱，GitHub 提供了两个特殊文件：

1. **`CONTRIBUTING.md`** - 贡献指南。内容可以包括：

   - 如何搭建开发环境
   - 如何提交修改（流程说明）
   - 代码风格规范，保持一致
   - 如何在遇到问题时寻求帮助

1. **`CODEOWNERS`** - 用来明确“谁负责哪部分代码”。

   - 当有人提交 Pull Request 时，GitHub 会自动通知对应负责人来审核

## ⌨️ 实操练习：创建贡献指南文件

IT 社团明天就要开会了，现在要提前准备好文档，让新加入的老师能快速上手。

1. 确保当前位于 `prepare-to-collaborate` 分支。

1. 在文件列表上方，点击 **Add file** 下拉菜单，选择 **Create new file** 新建文件。

1. 写入欢迎信息。

   ```md
   # Contributing to the Mergington High Extra-Curricular Activities Website

   Thank you for your interest in helping improve our school's website!
   Whether you want to add your club's activities, fix a bug, or suggest
   new features, this guide will help you get started. 🎉
   ```

1. 添加开发环境设置说明，帮助老师快速搭建开发环境。

   ```md
   ## 开发环境

   1. 将仓库克隆到本地。
   2. 安装 Python 依赖：`pip install -r requirements.txt`。
   3. 运行开发服务器：`python src/app.py`。
   4. 在浏览器中访问 `http://localhost:8000` 查看网站。

   ## 提交修改

   1. 为你的修改创建一个新分支。
      - 使用描述性名称，例如 `art-gallery-feature` 或 `fix-chess-signup`
   2. 使用示例学生数据在本地进行修改和测试。
      - 使用 MongoDB 扩展预览包含的示例数据。
   3. 推送你的分支并创建拉取请求。
   4. 等待审查并解决任何反馈。

   ## 代码风格

   - 遵循 Python 代码的 PEP 8 规范（后端）
   - 使用清晰、描述性的变量名（例如：student_name、start_time）
   - 添加注释来描述逻辑块
   ```

1. 添加 “获取帮助” 部分。

   ```md
   ## 遇到问题?

   - 首先检查是否存在相同的 issue。
     - 如果 issue 已存在，请添加评论或点赞。
     - 如果没有，请创建并保持描述尽量详细。
   - 参加每周四午餐时间的 IT 社团答疑。
   - 其他问题，请发送邮件至 techclub@mergingtonhigh.example.edu
   ```

1. 在右上方，使用 **Commit changes...** 按钮，直接提交到 `prepare-to-collaborate` 分支。

## ⌨️ 实操练习：指定代码负责人

随着越来越多的人加入，你希望核心功能的修改仍然由你把关。这可以通过 `CODEOWNERS` 文件来实现。

1. 返回 **Code** tab。确保你在 `prepare-to-collaborate` 分支上。

1. 在顶部目录，创建一个名为 `CODEOWNERS` 的新文件（区分大小写，无扩展名）。

1. 添加以下内容：

   ```codeowners
   # Core functionality - changes here should be rare!
   /src/app.py                   @{{ login }}
   /src/backend/database.py      @{{ login }}
   /src/backend/routers/auth.py  @{{ login }}

   # The frontend will need refactored soon to be more object oriented.
   /src/static/   @{{ login }}
   ```

1. 在右上方，使用 **Commit changes...** 按钮，直接提交到 `prepare-to-collaborate` 分支。

1. 文件提交后，等待片刻，让 Mona 检查你的工作、提供反馈并开启下一课。

## ⌨️ 实操练习：(可选) 添加你的第一个协作者

如果你已经准备好让别人参与开发，可以邀请他们加入：

> [!IMPORTANT]
> 这一步是可选的，因为它需要其他人拥有 GitHub 账户才能参与。

1. 在顶部导航中，选择 **Settings** tab。

1. 在左侧导航中，选择 **Collaborators**。

1. 找到 **Manage access** 区域，然后点击 **Add people** 按钮。

   <img width="350" alt="" src="https://github.com/user-attachments/assets/686c32c6-11c2-4e69-bad1-39062d5b4376" />

1. 输入朋友或同事的 GitHub 用户名或邮箱，然后点击 **Add to repository** 按钮。

   <img width="350" alt="" src="https://github.com/user-attachments/assets/d0eaf344-baf0-4a9c-9291-c11e7a9fdaa3" />

> [!IMPORTANT]
> 个人仓库只有一个协作角色类型。 " Collaborator" 获得**写**权限，但没有 **admin** 权限。如果您需要更精细的权限，可以考虑创建一个免费的[组织](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations)，并分配[存储库角色](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization)。
