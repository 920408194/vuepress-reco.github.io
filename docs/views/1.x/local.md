---
title: 多语言配置
date: 2019-03-24
---

::: tip <Badge text="1.3.3+" />
`vuepress-theme-reco` 的多语言配置，是在站点多语言配置和默认主题多语言配置的基础上增加的额外配置，所以请先了解官方的 [多语言配置官方文档](https://v1.vuepress.vuejs.org/zh/guide/i18n.html#%E7%AB%99%E7%82%B9%E5%A4%9A%E8%AF%AD%E8%A8%80%E9%85%8D%E7%BD%AE)。**并且请注意，`vuepress` 的默认语言代码为 `en-US`**。
:::

## 网站支持的语言

|名称|语言代码|
|:-:|-|
|简中|`zh-CN`、`zh-SG`|
|繁中|`zh-HK`、`zh-MO`、`zh-TW`|
|日语|`ja-JP`|
|韩语|`ko-KR`|
|英语|`en-US` 及除上面语种外其他任何语种|

## 如果网站只有一种语言

### 修改默认语言代码

`vuepress` 的默认语言代码为 `en-US`，如果我们需要改成简体中文，需要通过站点多语言配置来修改：

```js{5}
// config.js
module.exports = {
  locales: {
    '/': {
      lang: 'zh-CN'
    }
  }
}
```

### 修改默认语言配置

如果你觉得主题内置的术语不符合你的喜好，你可以这样修改：

```js{11,12,13,14,15,16,17,18}
// config.js
module.exports = {
  locales: {
    '/': {
      lang: 'zh-CN'
    }
  }
  themeConfig: {
    locales: {
      '/': {
        recoLocals: {
          homeBlog: {
            article: '美文', // 默认 文章
            tag: '标识', // 默认 标签
            category: '类别', // 默认 分类
            friendLink: '友链' // 默认 友情链接
          }
        }
      }
    }
  }
}
```

## 如果你的网站有多种语言

上面的语法同样适用：

```js
// config.js
module.exports = {
  locales: {
    '/': {
      lang: 'zh-CN'
    },
    '/en/': {
      lang: 'en-US'
    }
  }
  themeConfig: {
    locales: {
      '/': {
        recoLocals: {
          homeBlog: {
            article: '美文', // 默认 文章
            tag: '标识', // 默认 标签
            category: '类别', // 默认 分类
            friendLink: '友链' // 默认 友情链接
          }
        }
      },
      '/en/': {
        recoLocals: {
          homeBlog: {
            article: 'Article',
            tag: 'Tag',
            category: 'Category',
            friendLink: 'Friend Link'
          }
        }
      }
    }
  }
}
```

## 将文章按语言代码进行区分

下面这篇文章将在语言类型为 `zh-CN` 时显示：

```yaml{4}
---
title: 前端
date: 2020-03-04
lang: 'zh-CN'
---
```

下面这篇文章将在语言类型为 `en-US` 时显示：

```yaml{4}
---
title: Front End
date: 2020-03-04
lang: 'en-US'
---
```
