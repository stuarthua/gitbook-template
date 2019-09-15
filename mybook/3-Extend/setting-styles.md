# 自定义样式 styles

在项目根目录下新建 `styles` 目录

```bash
mkdir styles
```

在该目录下存放 `website.css` 样式文件

编辑 `website.css`, 清除浏览器缓存，重新运行即可查看效果

修改如下：

```css
/* remove gitbook link */
.gitbook-link {
    display: none !important;
}

/* Todo */
input[type=checkbox]{
    margin-left: -2em;
}

/* Prism */
pre[class*="language-"] {
    border: none;
    background-color: #f7f7f7;
    font-size: 1em;
    line-height: 1.2em;
}

/* Ace */
.aceCode {
    font-size: 14px !important;
}
```