# Markdown格式转换

参考：
1. [Markdown 格式如何转换成 Word](https://www.zhihu.com/question/22972843)
2. [Markdown格式书写，Word，PDF，HTML，PNG格式输出](http://www.jianshu.com/p/e60cc2f76f12)
3. [使用 markdown 编辑文档并转换为 word 格式](http://hi.ktsee.com/383.html)


## 转换成word


```
pandoc -f markdown -t docx ./test.md -o test.docx
pandoc -f markdown_github -t docx ./test.md -o test.docx
pandoc -f markdown -t html ./test.md | pandoc -f html -t docx -o test.docx
```

