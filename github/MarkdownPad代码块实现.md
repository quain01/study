# 代码块

## 单行代码块

`这是一个代码行`

## 多行代码块（使用三个反引号实现）

```shell
这是一个代码块
```

```
代码块
代码块
how to return
```

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

## 多行代码块（使用tab缩进实现）

    // ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    {
        zheshiyigeceshi 
        这是另外一个测试
    }

    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html

## 问题

1. 多行代码块如何换行：Markdown中“Markdown Processer”需要配置为“CommonMark”，否则多行代码块无法正确换行。
2. 参考知乎[Markdownpad2如果实现代码换行？](https://www.zhihu.com/question/29383702)
