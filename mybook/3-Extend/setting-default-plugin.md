# 默认插件设置

Gitbook 3.2.3 默认加载的插件有：

* livereload
* highlight
* search
* lunr
* sharing
* fontsettings
* theme-default

## 禁用 sharing 插件

```json
{
  "title": "Gitbook Template",
  "description": "A template for gitbook",
  "author": "Stuart Hua",
  "language": "zh-hans",
  "gitbook": "3.2.3",
  "links": {
    "sidebar": {
        "Blog": "https://blog.stuarthua.com/"
    }
  },
  "plugins": [
    "-sharing"
  ]
}
```

## 开启标题的数字索引

```json
{
  "title": "Gitbook Template",
  "description": "A template for gitbook",
  "author": "Stuart Hua",
  "language": "zh-hans",
  "gitbook": "3.2.3",
  "links": {
    "sidebar": {
        "Blog": "https://blog.stuarthua.com/"
    }
  },
  "plugins": [
    "-sharing"
  ],
  "pluginsConfig": {
    "theme-default": {
      "showLevel": true
    }
  }
}
```