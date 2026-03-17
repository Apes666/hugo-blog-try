---
title: 链接
slug: links
links:
  - title: GitHub
    description: GitHub 是全球最大的代码托管与协作平台之一。
    website: https://github.com
    image: https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png
menu:
    main: 
        weight: 4
        params:
            icon: link

comments: false
---

要启用这个页面，只需要在 front matter 中添加 `links` 字段。

当前页面的 front matter 示例：

```yaml
links:
  - title: GitHub
    description: GitHub 是全球最大的代码托管与协作平台之一。
    website: https://github.com
    image: https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png
  - title: TypeScript
    description: TypeScript 是 JavaScript 的类型化超集，最终会编译成普通 JavaScript。
    website: https://www.typescriptlang.org
    image: ts-logo-128.jpg
```

`image` 字段既支持本地图片，也支持外链图片。
