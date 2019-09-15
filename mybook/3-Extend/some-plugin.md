# GitBook 插件

Gitbook 3.2.3 默认加载的插件有：

* livereload
* highlight
* search
* lunr
* sharing
* fontsettings
* theme-default

## 第三方插件

参考：

* [https://snowdreams1006.github.io/gitbook-official/zh/](https://snowdreams1006.github.io/gitbook-official/zh/)
* [https://gitbook.zhangjikai.com/](https://gitbook.zhangjikai.com/)
* [http://www.chengweiyang.cn/gitbook/](http://www.chengweiyang.cn/gitbook/)

### prism & prism-themes

禁用 `highlight` 插件，使用 `prism` 搭配 `prism-themes` 为语法添加高亮显示

```json
{
    "plugins": [
        "prism",
        "prism-theme",
        "-highlight"
    ],
    "pluginsConfig": {
        "prism": {
            "css": [
                "prism-themes/themes/prism-base16-ateliersulphurpool.light.css"
            ]
        }
    }
}
```

修改默认样式，编辑 `website.css`, 添加 css 样式：

```css
/* Prism */
pre[class*="language-"] {
    border: none;
    background-color: #f7f7f7;
    font-size: 1em;
    line-height: 1.2em;
}
```

### search-pro

禁用 `lunr`, `search`, 使用 `search-pro` 支持中文搜索

```json
{
    "plugins": [
        "-lunr",
        "-search",
        "search-pro"
    ]
}
```

### advanced-emoji

使用 `advanced-emoji` 添加 emoji 支持

```json
{
    "plugins": [
        "advanced-emoji"
    ]
}
```

使用示例：

<pre>
:bowtie: :smile: :laughing: :blush: :smiley: :relaxed:
</pre>

### ace

添加插件，使 GitBook 支持 ace

```json
{
    "plugins": [
        "ace"
    ]
}
```

修改 `ace` 默认行高，编辑 `website.css`, 添加 css 样式：

```css
/* Ace */
.aceCode {
    font-size: 14px !important;
}
```

使用示例：

{%ace edit=true, lang='c_cpp'%}
// This is a hello world program for C.
#include <stdio.h>

int main(){
  printf("Hello World!");
  return 1;
}
{%endace%}

### splitter

添加 `splitter` 使侧边栏的宽度可以自由调节

```json
{
    "plugins": [
        "splitter"
    ]
}
```

### edit-link

使用 `edit-link` 添加顶部编辑菜单

```json
{
    "plugins": [
        "edit-link"
    ],
    "pluginsConfig": {
        "edit-link": {
            "base": "https://github.com/USER/REPO/edit/BRANCH",
            "label": "Edit"
        }
    }
}
```

使用效果：

![Snipaste_2019-09-16_02-05-46.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/tmp/Snipaste_2019-09-16_02-05-46.png)

### page-footer-ex

使用 `page-footer-ex`, 为页面添加页脚

```json
{
    "plugins": [
        "page-footer-ex"
    ],
    "pluginsConfig": {
        "page-footer-ex": {
            "copyright": "Copyright &copy stuarthua.com 2019",
            "markdown": false,
            "update_label": "<i>该文件修订时间：</i>",
            "update_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}
```

使用效果：

![Snipaste_2019-09-16_02-13-01.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/tmp/Snipaste_2019-09-16_02-13-01.png)

### sectionx

添加 `sectionx` 使页面支持分块显示

```json
{
    "plugins": [
        "sectionx"
    ],
    "pluginsConfig": {
        "sectionx": {
            "tag": "b"
        }
    }
}
```

使用示例：

<!--sec data-title="Sectionx Demo" data-id="section0" data-show=true ces-->

Insert markdown content here (you should start with h3 if you use heading).  

<!--endsec-->

### todo

使用 `todo` 添加 Todo 功能。

```json
{
    "plugins": [
        "todo"
    ]
}
```

默认的 checkbox 会向右偏移 2em，如果不希望偏移，可以在 `website.css` 里加上下面的代码:

```css
/* Todo */
input[type=checkbox]{
    margin-left: -2em;
}
```

使用示例：

- [ ] write some articles
- [x] drink a cup of tea

### github

`github`  添加 github 图标

```json
{
    "plugins": [
        "github"
    ]
}
```

使用效果：

![Snipaste_2019-09-16_02-17-54.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/tmp/Snipaste_2019-09-16_02-17-54.png)

### rss

`rss` 添加 rss 订阅功能

```json
{
    "plugins": [
        "rss"
    ],
    "pluginsConfig": {
        "rss": {
            "title": "gitbook-template",
            "description": "基于 Legacy 版 Gitbook 的模版",
            "author": "Stuart Hua",
            "feed_url": "https://stuarthua.github.io/gitbook-template/rss",
            "site_url": "https://stuarthua.github.io/gitbook-template/",
            "managingEditor": "stuarthua.cn@gmail.com",
            "webMaster": "stuarthua.cn@gmail.com",
            "categories": [
                "gitbook"
            ]
        }
    }
}
```

使用效果：

![Snipaste_2019-09-16_02-27-18.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/tmp/Snipaste_2019-09-16_02-27-18.png)

### anchor-navigation-ex

使用 `anchor-navigation-ex` 添加 Toc 到侧边悬浮导航以及回到顶部按钮

```json
{
    "plugins": [
        "anchor-navigation-ex"
    ],
    "pluginsConfig": {
        "anchor-navigation-ex": {
            "showLevel": false,
            "associatedWithSummary": false
        }
    }
}
```

注意: `anchor-navigation-ex` 插件只会提取 h1-h3 标签作为悬浮导航，且必须按照 h1 - h2 - h3 的顺序嵌套，才可被提取目录

使用效果：

![Snipaste_2019-09-16_02-26-29.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/tmp/Snipaste_2019-09-16_02-26-29.png)

### disqus

使用 `disqus` 增加评论功能

```json
{
    "plugins": [
        "disqus"
    ],
    "pluginsConfig": {
        "disqus": {
            "shortName": "Your Name"
        }
    }
}
```

### versions-select

使用 `versions-select` 插件，添加版本选择的下拉菜单，针对文档有多个版本的情况，需要添加多版本文档地址

```json
{
    "plugins": [
        "versions-select"
    ],
    "pluginsConfig": {
        "versions-select": {
            "options": [
                {
                    "value": "http://stuarthua.github.io/gitbook-template",
                    "text": "v3.2.2"
                },
                {
                    "value": "http://stuarthua.github.io/gitbook-template/v2",
                    "text": "v2.6.4"
                }
            ]
        }
    }
}
```

可以自定义 css 来修改 select 的显示样式，编辑 `website.css`：

```css
.versions-select select {
    height: 2em;
    line-height: 2em;
    border-radius: 4px;
    background: #efefef;
}
```

使用效果：

![Snipaste_2019-09-16_02-45-47.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/tmp/Snipaste_2019-09-16_02-45-47.png)