# efss24.github.io 个人主页

纯静态页面（HTML + CSS），不需要构建工具，GitHub Pages 直接发布。本地双击 `index.html` 就能预览。

## 目录

```
index.html              所有内容都在这里，搜索「【填写】」逐项替换
assets/css/style.css    样式；颜色在文件顶部 :root（浅色）和 dark 块（深色）里改
assets/img/avatar.svg   头像占位图，换成自己的照片后改 index.html 里的 src
assets/img/paper.svg    论文/项目缩略图占位
assets/img/favicon.svg  浏览器标签图标（里面的字母 Y 可改成名字首字母）
files/                  放 cv.pdf 等文件
.nojekyll               告诉 GitHub Pages 不要用 Jekyll 处理，保持原样发布
```

## 怎么填

还没填的板块（头像、Scholar/ORCID/CV 链接、About、News、Publications、Projects、Experience、Awards）都包在
`<template data-todo="...">…</template>` 里，页面上不显示。填好一块后删掉它外面的 `<template>` 标签就会显示；
顶部导航的链接也在一个 `<template data-todo="nav">` 里，记得把对应链接移到外面。

- **个人信息**：头像、中英文名、职位单位、一句话方向、邮箱和各类链接。不需要的链接整行删掉。
- **News**：每条一个 `<li>`，最新的放最上面。
- **Publications**：每篇论文复制一个 `<div class="pub">…</div>`。
  - 自己的名字用 `<b class="me">` 包起来，会加粗并加下划线。
  - 共同一作加 `<sup>*</sup>`，通讯作者加 `<sup>†</sup>`。
  - 缩略图建议 5:3，放到 `assets/img/pubs/`。
  - 在投稿件那一块不想公开就整块删掉。
- **Projects**：每个项目一个 `<a class="card">`。
- **Experience / Awards**：按时间倒序。
- **删掉整个板块**：同时删掉顶部导航 `<nav>` 里对应的链接。

## 发布到 GitHub Pages

1. 在 GitHub 新建一个公开仓库，名字必须是 `efss24.github.io`，不要勾选初始化 README。
2. 在本文件夹里运行：

   ```bash
   git init
   git add .
   git commit -m "Initial homepage"
   git branch -M main
   git remote add origin https://github.com/efss24/efss24.github.io.git
   git push -u origin main
   ```

3. 打开仓库的 Settings → Pages，Source 选 `Deploy from a branch`，分支选 `main`、目录选 `/ (root)`。
4. 等一两分钟，访问 https://efss24.github.io 。

之后每次改完：`git add . && git commit -m "update" && git push`，网站一两分钟内自动更新。
