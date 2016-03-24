---
layout : post
title : "Pandoc使用简介"
category : software
date : 2016-03-24
tags : [software]
SyntaxHihglighter: true
shTheme: shThemeDefault 
duoshuo: true 
math: true
---

## 什么是Pandoc

假如我现在有一个markdown文件，我想把它转化成tex文档，或者html文档，甚至word文档。最容易想到的方法是打开编辑器，将文本复制粘贴过去后开始进行设置。而事实上这对于很多情况无异于重新进行排版，于是我们希望有一个工具可以快速从某些文档转换成另一种文档。

对于我本人来说，现在的需求比较简单，把tex文档转换成.markdown，.pdf，beamer，或者markdown转换成.pdf，那Pandoc这个工具呼之欲出。至于历史和关于软件本身的简介参考[官方主页](http://pandoc.org/).

## 安装

[详情点我](http://pandoc.org/installing.html)，请参考官方说明文档。

## 使用

在此，我只列举一些我常用的命令（流程）

安装完毕后在命令行下输入

`pandoc --version`可以查看是否安装成功，版本是哪一个。

`pandoc --help`或者`pandoc -h`显示帮助

实际上上面的帮助对于轻度使用者并不是很大，不如直接来学具体的命令。OK，现在我们直接从需求上来进行说明

**目的**：将 C:\Users\yourname\Desktop\新建文本文档.txt (假设没有中文)转换成 C:\Users\yourname\Desktop\新建文本文档.markdown，可以在命令行中输入

``` shell
pandoc --ascii -f txt C:\Users\yourname\Desktop\新建文本文档.txt -t markdown -o C:\Users\yourname\Desktop\新建文本文档.markdown
```

上面的`新建文本文档.txt`和`新建文本文档.markdown`可以换成`.md` `.tex` `.html`等，接着我们解释几个命令

`--ascii`  避免转换成UTF-8编码

`-f` 后面设置输入格式，如`tex` `beamer` `html` `markdown`等（可根据后缀名判断，此时可忽略）

`-t` 后面设置输出格式，如`tex` `beamer` `html` `markdown`等

`-o` 设置输出文件路径，若没有的话大多情况自动在命令行下输出。因此这一个选项最好要写上

**目的**：将 C:\Users\yourname\Desktop\新建文本文档.txt (假设没有中文)转换成 C:\Users\yourname\Desktop\新建文本文档.pdf，同样输入

``` shell
pandoc --latex-engine=xelatex -f txt C:\Users\yourname\Desktop\新建文本文档.txt -t pdf -o C:\Users\yourname\Desktop\新建文本文档.pdf
```

稍等一会就会出现pdf文档(假设已经安装LaTeX)。

大致明白以上的内容后就可以进行最基础的文档格式转化了。另外想看看效果的话，可以看看[这里](http://pandoc.org/try/)

## 简写及cheatsheet

[^http://pandoc.org/demos.html​]: 实际上上面所述的很多内容可以简写，我们根据需求把一些转换命令列举如下

1. txt转换html格式
   
   `pandoc yourfile.txt -o yourfile.html`
   
2. 独立html文档要加`-s`
   
   `pandoc -s yourfile.txt -o yourfile.html`
   
3. txt转换为pdf格式
   
   `pandoc --latex-engine=xelatex yourfile.txt -o newfile.pdf`
   
4. 上面的txt格式和pdf格式可以替换，如若不成，就用全命令
   
   ``` shell
   pandoc -f [输入格式] [输入文档路径] -t [输出格式] -o [输出文档路径]
   ```
   
5. 实际上还可以简写为
   
   ``` shell
   pandoc -f [输入格式]  -t [输出格式] [输入文档路径] 
   ```
   
   或者
   
   ``` shell
   pandoc -o [输出文档路径] [输入文档路径]
   ```
   
6. 转换tex时
   
   ``` shell
   pandoc -s [input] -o [output].tex
   ```
   
7. 将网页转换成markdown
   
   ``` shell
   pandoc -s -r html http://www.gnu.org/software/make/ -o output.html
   ```
   
8. PDF with numbered sections and a custom LaTeX header
   
   ``` shell
   pandoc -N --template=mytemplate.tex --variable mainfont="Palatino" --variable sansfont="Century Gothic" --variable monofont="Consolas" --variable fontsize=12pt --variable version=1.15.2 README --latex-engine=xelatex --toc -o example14.pdf
   ```
   
9. EPUB ebook
   
   ``` shell
   pandoc -S README -o README.epub
   ```
   
10. Word docx:
    
    ``` shell
    pandoc -s -S README -o example.docx
    ```
    
11. LaTeX math to docx:
    
    ``` shell
    pandoc -s math.tex -o example.docx
    ```
    
12. Docx with a reference docx:
    
    ``` shell
    pandoc -S --reference-docx twocolumns.docx -o UsersGuide.docx README
    ```
    
13. Docx to markdown, including math:
    
    ``` shell
    pandoc -s example.docx -t markdown -o example.md
    ```
    
14. EPUB to plain text:
    
    ``` shell
    pandoc README.epub -t plain -o example.text
    ```

----

关于如何协作进行$LaTeX$的编写，请参考[这里](http://www.tuicool.com/articles/femeA3)



**2016年3月24日 22:49初稿**