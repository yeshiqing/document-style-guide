# Markdown 技术文档写作规范

说明：本文档是对[中文技术文档的写作规范](https://github.com/yeshiqing/document-style-guide)的补充，原规范不含 Markdown 文档的书写要求。


（1）代码注释中混有中英文，中英文之间同样需要空格

```js
/*
 * 错误：查看某字符的Unicode编码
 * 正确：查看某字符的 Unicode 编码
 */
"—".charCodeAt(0).toString(16)
```

（2）中文和表示代码的反引号之间不必空格`code`

（3）对于 details 标签，不建议用于折叠代码。因为不同 Markdown 引擎的解析语法不同，并不通用。

- 在 Github 中，通过 details 标签中保留一行空行，可以实现代码折叠而且能保留语法高亮。
    
    ```markdown
    <details>
    <summary>我是摘要</summary>
    <p>其他内容</p>
    <!-- 这行空行必须保留 -->
    ```HTML
    <h1>heading</h1>
    ```
    </details>
    ```
    
- 在 Typora（v1.3.7）中，在 details 标签中，通过 pre 标签可以实现代码折叠，但没有语法高亮。
    而且注意 HTML 标签中不能有空行。
    
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
    &lt;h2&gt;heading2&lt;/h2&gt;
    &lt;h3&gt;heading3&lt;/h3&gt;
    </pre>
    </details>
    ```

（4）反引号的使用

- 地址栏中的地址，属于代码片段，应该使用反引号（\`）包裹。
  例如地址栏访问：`chrome://inspect/#devices`

- 操作系统中的文件路径，应该用反引号（\`）包裹。
  
- 文件名（不论是否带后缀）需要用反引号（\`）包裹。例如：“项目的主入口是`index.js`”。

- HTML 标签需要加上尖括号并用反引号包裹。
    例如：“`<header>`标签可以用在多个场景，既可以表示整个网页的头部，也可以表示一篇文章或者一个区块的头部。”

（5）能不用脚注就不用脚注

- 便于文档迁移，因为不是所有 Markdown 编辑器都支持脚注。比如语雀目前不支持脚注，语雀中用「折叠块」或「文档内跳转」代替脚注。
- 实际上个人认为脚注是非常方便的，比如 Github、Typora 都支持脚注。在不打断文档主线逻辑阅读流畅性的情况，对特殊词语进行补充说明。
