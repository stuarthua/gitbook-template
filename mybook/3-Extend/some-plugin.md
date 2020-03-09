# GitBook 插件

Gitbook 3.2.3 默认加载的插件有：

* livereload
* highlight
* search
* lunr
* sharing
* fontsettings
* theme-default
* favicon-absolute

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

```
{%ace edit=true, lang='c_cpp'%}
// This is a hello world program for C.
#include <stdio.h>

int main(){
  printf("Hello World!");
  return 1;
}
{%endace%}
```

效果预览：

![Snipaste_2019-09-21_22-08-12.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/Snipaste_2019-09-21_22-08-12.png)

> **注意：** 开启此插件，使用 gitbook 生成 epub、mobi 格式电子书时，有可能失败

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

> **注意：** 开启此插件，使用 gitbook 生成 epub、mobi 格式电子书时，页脚样式会添加到正文中

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

```
<!--sec data-title="Sectionx Demo" data-id="section0" data-show=true ces-->

Insert markdown content here (you should start with h3 if you use heading).  

<!--endsec-->
```

效果预览：

<!--sec data-title="Sectionx Demo" data-id="section0" data-show=true ces-->

Insert markdown content here (you should start with h3 if you use heading).  

<!--endsec-->

> **注意：** 该插件开启后，和 callouts 有冲突，建议置于 callouts 插件之前加载

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

### expandable-chapters

增加侧边栏标题展开收缩功能

```json
"plugins": [
  "expandable-chapters"
]
```

使用效果：

![expandable-chapters.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/expandable-chapters.png)

### expandable-chapters-small

增加侧边栏标题展开收缩功能，图标较小

```json
"plugins": [
  "expandable-chapters-small"
]
```

使用效果：

![Snipaste_2019-09-21_21-37-53.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/Snipaste_2019-09-21_21-37-53.png)


### donate

增加打赏功能

```json
"plugins": [
  "donate"
],
"pluginsConfig": {
  "donate": {
    "button": "打赏",
    "alipayText": "支付宝打赏",
    "wechatText": "微信打赏",
    "alipay": "xxx.jpg",
    "wechat": "xxx.jpg"
  }
}
```

### copy-code-button

给 GitBook 的 Code 添加复制功能，可以一键复制代码块的所有代码

```json
"plugins": [
  "copy-code-button"
]
```

效果预览：

![copy-button.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/copy-button.png)

### theme-comscore

区分标题颜色的主题

```json
"plugins": [
  "theme-comscore"
]
```

效果预览：

![Snipaste_2019-09-21_20-54-30.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/Snipaste_2019-09-21_20-54-30.png)

### toolbar-button

添加工具栏按钮，如添加下载 PDF 按钮

```json
"plugins": [
  "toolbar-button"
]
"pluginsConfig": {
    "toolbar-button": {
      "url": "https://stuarthua.github.io/gitbook-template/gitbook-template.pdf", 
      "icon": "fa-file-pdf-o", 
      "label": "下载PDF"
    },
}
```

需要安装 [gitbook-pdf](https://www.npmjs.com/package/gitbook-pdf) 插件和 [calibre](https://calibre-ebook.com)，生成 PDF：

```
# 安装 gitbook-pdf
## 如果无法下载 phantomjs-1.9.7-macosx.zip，可在 https://bitbucket.org/ariya/phantomjs/downloads/ 目录中找到 phantomjs-1.9.8-macosx.zip 手动放到报错目录，再次执行安装即可
npm install gitbook-pdf -g

# 安装 calibre
brew cask install calibre
```

生成 PDF：

```bash
gitbook pdf .
```

同理，也可生成 ePub 和 Mobi 格式电子书

```bash
gitbook epub .
gitbook mobi .
```

效果预览：

![Snipaste_2019-09-21_20-56-14.png](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/Snipaste_2019-09-21_20-56-14.png)

> **注意：** 使用此插件，会覆盖 edit-link 插件、rss 插件、fontsetting 插件的标题栏显示

### callouts

更好看的 hint callout 提示

```json
{
    "plugins": ["callouts"],
    "pluginsConfig":{
        "callouts":{
            "showTypeInHeader": false
        }
    }
}
```

效果预览：

![hints-callouts.jpg](https://raw.githubusercontent.com/stuarthua/PicGo/master/gitbook-template/hints-callouts.jpg)

> **注意：** 该插件开启后，和 sectionx 有冲突，建议置于 sectionx 插件后

### sitemap-general

生成站点地图，方便搜索引擎收录

```json
{
    "plugins": [
        "sitemap-general"
    ],
    "pluginsConfig":{
        "sitemap-general":{
            "prefix": "https://stuarthua.github.io/gitbook-template/"
        }
    }
}
```

### ga

Google 统计

```json
{
    "plugins": [
        "ga"
    ],
    "pluginsConfig": {
        "ga": {
            "token": "UA-XXXX-Y"
        }
    }
}
```

token 从 Google Analytics 中获取

### baidu-tongji

给 GitBook 的站点添加百度统计，这样用户的访问数量可以通过百度统计查看到

```json
{

    "plugins": [
        "baidu-tongji"
    ],
    "pluginsConfig": {
        "baidu-tongji": {
        "token": "xxxxxx"
    }
}
```

### favicon-absolute

为网站设置 favicon

```json
{
    "plugins": [
        "favicon-absolute"
    ],
    "pluginsConfig": {
        "favicon-absolute":{
        "favicon": "/favicon.ico",
        "appleTouchIconPrecomposed152": "/apple-touch-icon-precomposed-152.png"
        }
    }
}
```