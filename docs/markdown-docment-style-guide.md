# Markdown 技术文档写作规范

说明：本文档是对[中文技术文档的写作规范](https://github.com/yeshiqing/document-style-guide)的补充，原规范不含 Markdown 文档的书写要求。

## 字间距

（1）代码注释中混有中英文，中英文之间需要空格

```js
/*
 * 错误：查看某字符的Unicode编码
 * 正确：查看某字符的 Unicode 编码
 */
"—".charCodeAt(0).toString(16)
```

（2）中文和表示代码的反引号之间不必空格

按下`command`键，再按下`option`键。

## Markdown 语法中的符号

（1）反引号的使用

- 地址栏中的地址，属于代码片段，应该使用反引号（\`）包裹。
  例如地址栏访问：`chrome://inspect/#devices`

- 操作系统中的文件路径，应该用反引号（\`）包裹。
  
- 文件名（不论是否带后缀）需要用反引号（\`）包裹。例如：“项目的主入口是`index.js`”。

- HTML 标签需要加上尖括号并用反引号包裹。
    例如：“`<header>`标签可以用在多个场景，既可以表示整个网页的头部，也可以表示一篇文章或者一个区块的头部。”

（2）根据编辑器支持情况，使用脚注语法

`[^1]: 脚注信息`

- 不是所有 Markdown 编辑器都支持脚注，比如语雀目前不支持脚注。
- 实际上个人认为脚注是非常方便的，比如 Github、Typora 都支持脚注。在不打断文档主线逻辑阅读流畅性的情况，对特殊词语进行补充说明。

（3）Obsidian 和 Typora 中不要用颜色高亮`==高亮部分==`语法，因为 GitHub 不支持这个语法。

## 其他

（1）语雀中写博客**不要用“字体颜色”，用加粗代替**，便于文档迁移。

（2）不建议使用`<details>`标签折叠代码

因为不同 Markdown 引擎的解析语法不同，并不通用。现在使用的 Obsidian 对 Markdown 文档支持折叠功能，非常好！

- 在 Github 中，通过 details 标签中保留一行空行，可以实现代码折叠而且能保留语法高亮。
  
    ````markdown
    <details>
    <summary>我是摘要</summary>
    <p>其他内容</p>
    <!-- 这行空行必须保留 -->
    ```HTML
    <h1>heading</h1>
    ```
    </details>
    ````
    
- 在 Typora（v1.3.7）中，在 details 标签中，通过 pre 标签可以实现代码折叠，但没有语法高亮，而且 HTML 标签之间不能有空行。
  
    ```markdown
    <details>
    <summary>我是摘要</summary><pre>
    let f = function () {
       this.a = 1;
       this.b = 2;
    }
    </pre>
    </details>
    ```
    
    这种方式不支持 HTML 标签，除非将每个 HTML 标签都进行转义。同样也没有语法高亮。
    ```markdown
    <details>
    <summary>我是摘要</summary>
    <pre>
    &lt;h1&gt;heading1&lt;/h1&gt;
    </pre>
    </details>
    ```