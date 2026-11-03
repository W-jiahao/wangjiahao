# 个人学术主页

基于原仓库的 Minimal Mistakes / Jekyll，按参考学术主页的两栏结构制作。个人资料、简介、论文和动态分别从 `_data/profile.yml` 和 `_data/academic.yml` 读取；未填写的内容保留空白。

网站地址（GitHub Pages 部署成功后）：**https://w-jiahao.github.io/wangjiahao/**

## 发布

1. 仓库 Settings → Pages → Build and deployment → Source 选择 **Deploy from a branch**。
2. Branch 选择 **master**，Folder 选择 **/(root)**，点击 Save。
3. 以后在 GitHub 修改文件并提交到 `master`，GitHub Pages 会自动构建发布，通常需要几分钟。

在 Actions 的 **pages build and deployment** 中查看进度。构建失败时，线上会继续显示上一次成功的版本，因此即使只改 `profile.yml`，其他数据文件的语法错误也会阻止整站更新。

不需要修改仓库名称，也不要将发布目录设为 `docs`（原主题文档与个人主页无关）。

## 填写个人资料

编辑 `_data/profile.yml`。空字段不会显示，`name` 留空时显示 `Your Name`。

```yaml
name: "Your English Name"
name_zh: "中文姓名"
bio: "身份 / 研究方向"
email: "you@example.com"
location: "城市 / 国家"
affiliation: "学校 / 单位"
avatar: "/assets/images/your-photo.jpg"
scholar: "https://scholar.google.com/citations?user=YOUR_ID"
github: "https://github.com/W-jiahao"
cv_pdf: "/files/cv.pdf"
```

将照片上传到 `assets/images/`。将 PDF 简历上传到 `files/`，然后填写 `cv_pdf`；留空时 CV 导航会打开站内简历页。站内资源填写以 `/` 开头的路径，不要重复添加 `/wangjiahao`。

## 填写学术内容

所有学术内容集中在 `_data/academic.yml`。以下仅是填写格式示例，不会自动显示到网页。

请保留缩进：`news` 每条需要 `date` 和 `text`，`publications` 每条需要 `title`、`authors` 等字段。不要把整段新闻或论文直接放进 `[]`。Markdown 链接写成 `[文字](https://...)`。

```yaml
about: |
  在这里写个人简介。支持 **粗体** 和 [链接](https://example.com)。

news:
  - date: "2026-11"
    text: "在这里写一条动态。"

publications:
  - title: "论文标题"
    authors: "**你的名字**, 其他作者"
    venue: "会议或期刊"
    year: 2026
    paper: "https://example.com/paper"
    code: "https://github.com/your-name/project"
    selected: true

activities:
  - "在这里写学术服务或专业活动。"

awards:
  - "在这里写奖项和年份。"

talks:
  - title: "报告标题"
    date: "2026-11"
    venue: "报告场合"
    url: "https://example.com/talk"
    description: "报告简介。"

teaching:
  - title: "课程名称"
    term: "2026 Fall"
    role: "课程角色"
    description: "课程简介。"

cv: |
  ## Education

  在这里填写教育经历。支持 Markdown。
```

`selected: true` 的论文同时出现在首页 Selected Publications，完整列表显示在 Publications 页面。`authors` 和 `venue` 支持 Markdown，例如 `venue: "ACM Transactions on Information Systems (**TOIS, CCF-A, THU-A**)"` 会将括号内文字加粗。未提供 Paper / Code 链接的论文不会显示相应链接。

## 本地预览

安装 Ruby 3.3 和 Bundler 后：

```sh
bundle install
bundle exec jekyll serve --baseurl /wangjiahao
```

打开 http://127.0.0.1:4000/wangjiahao/ 。站点布局在 `_layouts/academic.html`，样式在 `assets/css/academic.css`。

## 致谢

- [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes)，MIT 许可证，原始版权见 `LICENSE`。
- 页面结构参考 [Yuli Liu 的学术主页](https://l-lyl.github.io/yuli-liu.github.io/)，未复制其个人内容和照片。
