<img align="right" width="150" alt="logo" src="https://user-images.githubusercontent.com/5889006/190859553-5b229b4f-c476-4cbd-928f-890f5265ca4c.png">

# Hugo Stack 中文博客

这是一个基于 [Hugo Theme Stack](https://github.com/CaiJimmy/hugo-theme-stack) 的博客站点，使用 [Hugo Modules](https://gohugo.io/hugo-modules/) 引入主题。

## 本地开发

确保本机已经安装：

- Git
- Go
- Hugo extended

常用命令：

```bash
hugo server -D
hugo --cleanDestinationDir
```

`hugo server -D` 用于本地预览，`hugo --cleanDestinationDir` 用于生成干净的静态产物。

## 项目结构

```text
.
├── config/_default/      # Hugo 配置拆分目录
├── content/              # 站点内容：文章、页面、分类、标签
├── assets/               # 图片、SCSS 等资源
├── public/               # Hugo 构建后的静态文件
├── resources/            # Hugo 资源缓存
├── go.mod / go.sum       # Hugo Module 依赖
└── README.md             # 项目说明
```

几个最重要的目录和文件：

- `config/_default/config.toml`：站点基础配置，例如标题、语言、分页、`baseurl`
- `config/_default/languages.toml`：语言定义，决定站点启用哪些语言
- `config/_default/params.toml`：Stack 主题参数，例如侧栏、文章信息、组件、评论系统
- `config/_default/menu.toml`：全局菜单和社交链接
- `config/_default/module.toml`：主题模块入口，这个项目通过它加载 `hugo-theme-stack`
- `content/_index.md`：首页配置
- `content/post/`：博客文章，每篇文章通常使用 page bundle 目录结构
- `content/page/`：独立页面，例如搜索、归档、友情链接
- `content/categories/` 和 `content/tags/`：taxonomy 的元信息页，可以给分类/标签定义中文标题、描述和样式

## 本地化思路

这个项目的本地化分成两层：

1. 主题界面文案  
   由 `config/_default/config.toml` 里的 `defaultContentLanguage` 控制，Stack 主题内置了中文 i18n。

2. 站点实际内容  
   由 `content/` 下的 Markdown 文件控制，包括页面标题、菜单名称、文章正文、分类标签名称等。

如果你后面要继续做双语站点，可以在 `config/_default/languages.toml` 增加其他语言，再为内容文件增加语言后缀，例如 `index.en.md`、`index.zh.md`。

## 更新主题

```bash
hugo mod get -u github.com/CaiJimmy/hugo-theme-stack/v4
hugo mod tidy
```

主题版本由 `config/_default/module.toml` 管理。
