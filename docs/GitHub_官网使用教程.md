# GitHub 官网使用教程（面向小白，图文并茂）

说明：本教程面向从未用过 GitHub 或对网页不熟悉的初学者。每个操作我都按最详细的步骤写清楚，并在需要时给出截图位置的占位说明（你可以把真实截图替换占位图）。

---

## 目录
1. GitHub 是什么？为什么要用它  
2. 访问与登录（Sign up / Sign in）  
3. 个人主页（Profile）与菜单导览  
4. 新建仓库（Repository）——最常用流程（网页端）  
5. 在网页上上传文件（README、PDF、图片）  
6. 克隆（clone）到本地并推送（简单命令）  
7. 分支（Branch）与 Pull Request（PR）基础流程  
8. Issues（问题）与项目管理（Projects）基础  
9. 仓库设置与权限（常见设置）  
10. 常见问题快速排查（FAQ）  
11. 入门练习（两题）  
12. 截图模板（建议拍摄的图片与命名）  
13. 附录：常用术语表

---

## 1. GitHub 是什么？为什么要用它
- GitHub 是一个基于 Git 的代码托管��协作平台。适用于个人项目、团队协作、开源贡献与文档托管。  
- 你可以在上面：
  - 存放代码与文档（Repository / 仓库）  
  - 跟踪任务（Issues）  
  - 提交改动并请求合并（Pull Request）  
  - 展示个人或项目作品（Profile / README / Pages）

简短建议：初学者先从“创建仓库 -> 上传 README -> 编辑 README -> 提交”这几个网页操作入手，熟悉流程后再学命令行。

---

## 2. 访问与登录
1. 打开浏览器，访问 https://github.com  
2. 如果没有账号，点击右上角的 "Sign up"（注册）按步骤注册：填邮箱、用户名、密码，按页面提示完成验证。  
3. 若已有账号，点击右上角 "Sign in"，输入用户名/邮箱与密码登录。  
4. 登录后右上角会显示你的头像（或默认头像），说明你已登录成功。

截图占位（替换为实际截图）：
- screenshot-01-home.png：GitHub 主页（未登录和已登录两种状态）
- screenshot-02-signin.png：Sign in 页面（输入区域）

注意：注册时记好用户名与密码，建议开启两步验证（2FA）提高安全性（Settings → Security）。

---

## 3. 个人主页（Profile）与顶部菜单导览
- 登录后，页面右上角是你的头像按钮，点击会弹出菜单：Profile（个人主页）、Your repositories（你的仓库）、Settings（设置）等。  
- 个人主页（Profile）显示你的简介、仓库列表、贡献图（contributions）等。  
- 顶部还有搜索框、Pull requests、Issues、Marketplace 等入口。

截图占位：
- screenshot-03-avatar-menu.png：头像下拉菜单（标注 Repositories、Profile、Settings）
- screenshot-04-profile.png：个人主页页面（标注仓库标签）

小提示：Profile 里可以设置简介（bio）、个人网站、邮箱等，让别人更容易认识你。

---

## 4. 新建仓库（Repository）——网页端详细步骤
目的：创建一个新的代码或文档仓库（例如：my-docs）

步骤：
1. 登录后点击右上角头像 → 选择 “Your repositories” 或直接在 Repositories 页面点击绿色 “New” 按钮。  
   - 或者页面右上有一个 “+” 按钮，点后选择 “New repository”。  
2. 在 “Create a new repository” 页面填写：
   - Repository name：输入仓库名（例如 `my-docs`）。只能用字母、数字、连字符 `-`，不能有空格。  
   - Description（可选）：写一句话说明仓库的用途。  
   - Visibility：选择 Public（公开）或 Private（私有）。初学者通常选 Public（公开），但不要上传敏感信息。  
   - Initialize this repository with：建议勾选 “Add a README file”（自动添加 README）。可以同时选择 .gitignore（根据语言）或 license。  
3. 点击 “Create repository” 按钮，成功后会进入仓库主页，地址栏显示 `https://github.com/<你的用户名>/<仓库名>`。

截图占位：
- screenshot-05-create-repo.png：Create a new repository 表单（标注各字段）
- screenshot-06-repo-home.png：仓库主页（标注 Code 按钮、Add file）

小技巧：
- 如果只想先试水，创建 Public 仓库并添加 README 即可；以后若要私有可在 Settings 更改。

---

## 5. 在网页上上传文件（README、PDF、图片）
方法一：网页上传单个或少量文件（适合初学者）
1. 打开仓库主页（例如 `https://github.com/<username>/my-docs`）。  
2. 点击 “Add file” → 选择 “Upload files”。  
3. 把本地文件拖到上传区域，或点击选择。  
4. 在下方填写 Commit message（例如：Add tutorial PDF），然后点击 “Commit changes”。  
5. 文件会被保存到仓库当前分支（默认 `main`）。

方法二：在网页上新建或编辑文本文件（例如编辑 README）
1. 点击 “Add file” → “Create new file”。  
2. 在文件名输入框输入 `README.md`，在编辑器里写 Markdown内容。  
3. 填写 Commit message → 点击 “Commit new file”。

截图占位：
- screenshot-07-upload-file.png：Upload files 页面（标注拖拽区域、Commit 按钮）
- screenshot-08-create-file.png：Create new file 编辑界面

注意：
- 网页上传适合少量文件或文档；如果文件很多或频繁变更，建议使用 Git 命令行上传（见第6节）。

---

## 6. 克隆（clone）到本地并推送（最基础命令）
如果你想在本地编辑并推送到 GitHub，下面是最常用的命令（基于 HTTPS）：

准备：先安装 Git（https://git-scm.com/download/）

示例：把仓库克隆到本地并上传文件
1. 克隆仓库到本地：
   git clone https://github.com/<你的用户名>/<仓库名>.git
2. 进入仓库目录：
   cd <仓库名>
3. 添加或修改文件，然后提交并推送：
   git add .
   git commit -m "Add tutorial PDF"
   git push origin main

说明：
- 如果启用了两步验证（2FA），在推送时使用 Personal Access Token（PAT）作为密码（在 GitHub → Settings → Developer settings → Personal access tokens 生成）。
- 可选择使用 SSH（先生成 SSH key 并把公钥添加到 GitHub → Settings → SSH and GPG keys）。

截图占位：
- screenshot-09-quick-setup.png：仓库主页的 Quick setup（显示 clone 命令）

---

## 7. 分支（Branch）与 Pull Request（PR）基础流程
为什么用分支：在分支上开发新功能或修复 bug，避免直接修改 `main`。

网页上常用的简单流程（适合小白）：
1. 在仓库页面的分支下拉框输入新分支名（如 `feature/readme`），按回车创建并切换到该分支。  
2. 在该分支上编辑 README 或上传文件并 Commit。  
3. 在仓库页面会出现 “Compare & pull request” 按钮，点击进入 PR 页面，填写标题与说明，提交 PR。  
4. PR 可以被合并（Merge）到 `main`，也可以先进行 Review（审查）。

命令行流程（示例）：
 git checkout -b feature/readme
（修改文件）
 git add .
 git commit -m "Update README"
 git push -u origin feature/readme
 在 GitHub 页面创建 PR 并合并。

截图占位：
- screenshot-10-branch-pr.png：分支下拉框与 Compare & pull request 按钮

小提示：
- PR 描述写清楚“做了什么”和“如何测试”，方便别人审查。

---

## 8. Issues（问题）与项目管理（Projects）基础
- Issues 用来记录 bug、任务或讨论：仓库 → Issues → New issue。写标题和详细描述，可以分配负责人（Assignees）、加标签（Labels）。
- Projects（看板）可以拖放 Issues，做简单的任务看板管理。

截图占位：
- screenshot-11-issues-new.png：New issue 界面
- screenshot-12-projects.png：Projects 看板示例

---

## 9. 仓库设置与权限（常见设置）
在仓库页面右上点击 “Settings” 可配置很多选项，常用包括：
- Manage access：邀请合作者并设置权限（Read / Write / Admin）。  
- Branches：设置保护分支（Require pull request reviews 等）。  
- Actions：设置 GitHub Actions 的权限（如果要自动化生成 PDF 或 CI）。  
- Webhooks：配置与外部服务的集成。

安全建议：
- 不要把密码、秘钥直接提交到仓库。使用 `.gitignore` 忽略本地机密文件。  
- 开启账号两步验证（2FA）。  
- 使用 Dependabot 提示来关注依赖安全。

截图占位：
- screenshot-13-settings-access.png：Settings → Manage access

---

## 10. 常见问题快速排查（FAQ）
Q：看不到某个按钮（如 New、Add file）怎么办？
A：确认你已登录；如果仓库是别人的并且你没有权限，界面会显示不同的选项。尝试刷新页面或换浏览器。

Q：推送时报错 “permission denied” 或 403？
A：可能是没有写权限，或 2FA 下未使用 PAT。检查是否以正确的账号登陆并使用 PAT 或 SSH key。

Q：如何删除仓库？
A：进入仓库 Settings → 下拉到最底部 Danger Zone → Delete this repository（小心操作，删除不可恢复，建议先备份）。

---

## 11. 入门练习（两题）
练习 1：创建仓库并上传 README
- 目标：创建名为 `my-docs` 的仓库，添加 README.md 并写一句自我介绍。
- 步骤提示：参照第4和第5节完成。

练习 2：在分支上修改 README 并提交 PR
- 目标：在新分支 `feature/update-readme` 上修改 README 内容并发起 PR 合并到 main。
- 步骤提示：参照第7节（网页分支创建或命令行）。

---

## 12. 截图模板（建议拍摄并命名）
如果你希望我把教程做成带实图的 PDF，请按下面清单拍截图并上传给我（按序号命名）：
- screenshot-01-home.png — GitHub 登录后主页（标注顶部导航与头像）
- screenshot-02-signin.png — Sign in 页面（邮箱/密码输入框）
- screenshot-03-avatar-menu.png — 点击头像后的下拉菜单（标注 Repositories、Profile、Settings）
- screenshot-04-profile.png — 个人主页（Profile）
- screenshot-05-create-repo.png — Create a new repository 页面
- screenshot-06-repo-home.png — 仓库主页（Code 按钮、Add file）
- screenshot-07-upload-file.png — Add file → Upload files 页面
- screenshot-08-quick-setup.png — Quick setup：clone 命令显示
- screenshot-09-branch-pr.png — 创建分支/Compare & pull request 页面
- screenshot-10-issues-new.png — New issue 页面
- screenshot-11-settings-access.png — Settings → Manage access 页面

我会把这些图片放在教程对应位置并做箭头标注（若你不提供，我会用示意图代替）。

---

## 13. 常用术语表（简短）
- Repository（仓库）：存放代码/文档的地方。  
- Commit：一次提交，记录变更。  
- Branch（分支）：并行开发的线。  
- Pull Request（PR）：请求把分支改动合并到另一个分支（通常是 main）。  
- Clone：把远程仓库复制到本地。  
- Fork：复制别人的仓库到自己的账号下（常用于贡献开源）。  
- Issue：问题或任务条目。  
- README.md：项目介绍文件，通常显示在仓库主页。

---

结束语
- 本教程为入门级网页操作指南，适合“零命令行”用户快速上手 GitHub 官网。  
- 如果你想要：
  - 我把这份 Markdown 转成 PDF 并自动生成示意图（我可以代做），回复 “请生成 PDF 并提交仓库”；  
  - 或者你把真实截图上传给我，我帮你排版并生成带实图的 PDF，回复 “我上传截图”。

感谢你阅读，有任何不懂的步骤随时把截图或描述发过来，我会一步步指导你完成。
