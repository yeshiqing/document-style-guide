# 中文技术文档写作规范说明

## 文档体系

文档体系指产品使用说明文档的规范。其中“文件名小写”这一文件命名规则，并不适用于项目源代码。比如 Java 代码中要求类文件首字母要大写，比如`Solution.java`

## 为什么文件名要小写？

1）适配对大小写敏感的 Linux 操作系统，保证不同操作系统的可移植性。

2）比驼峰命名更易读。

3）用户的文件都采用小写文件名，就很方便与系统预置的目录（Downloads）或特定用途的文件（README.md、CHANGELOG.md、LICENSE、Cat.Java）相区分。

4）命令行输入命令时，不用传入忽略字符大小写的参数`-i`。

补充：如果这个文件名是某个专有名词的缩写，建议该大写还是大写以示区分，比如我会选择`V8-research`而非`v8-research`后者容易让人误解为第8个版本。

详见阮一峰文章：[为什么文件名要小写](https://www.ruanyifeng.com/blog/2017/02/filename-should-be-lowercase.html)

## 为什么建议使用「连字暨减号」来分隔文件名中的多个单词？

文档原文：

> 文件名包含多个单词时，单词之间建议使用半角的连词线（-）分隔。

原因：

1）有的单词包含连词线，如果使用下划线，不利于统一风格，比如 five-year_child。

2）下划线需要按 Shift 键。

3）下划线不利于 SEO。https://www.woorank.com/en/blog/underscores-in-urls-why-are-they-not-recommended



## 为什么文件名中间不能带空格？

原因：

1）部分编程语言文件名不允许空格，大部分原因是文件名和类、命名空间保持一致，类、命名空间不允许存在空格，所以文件也不能存在空格。

2）Linux 系统的命令行中，文件名中带有空格的文件，需要加转义字符（`\ `）或引号，操作不变。如查看名为“foo bar”的文件夹中的内容：

```shell
ls -l foo\ bar
或
ls -l 'foo bar'
```



## 为什么文件名必须使用半角字符，不得使用全角字符？

文档原文：

> 文件名必须使用半角字符，不得使用全角字符。这也意味着，中文不能用于文件名。

原因：

便于运维人员操作。有些 CI（Continuous Integration，持续集成）服务器只有 ASCII 码环境。