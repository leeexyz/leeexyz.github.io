---
layout: post
title: 学习Markdown语法
tags: [skill]
---
[Markdown](https://zh.wikipedia.org/wiki/Markdown)是一种轻量级标记性语言，由于其纯文本标记的特性，非常容易学习和掌握。本文就是学习Markdown的第一次实践。

#### 为什么要学习它?
1. 现在很多主流的网站都使用Markdown书写，如：Github、Stackoverflow；
2. 学习起来非常容易，基本的Markdown只有十几种，学习曲线容易；
3. Markdown的文本能够很容易得转化成HTML；
4. 当然，最重要的还是能够帮助开发者更高效、更友好的开发文档。

#### 选择书写工具
Markdown对于编辑器没有特别的要求，可以根据自己的喜好选择诸如：Notepad++、Subline、Vim、Emacs等。对我而言，还是钟爱Vim作为编辑器：）那么，下面就讲一讲我都在Vim中配置了哪些插件加快Markdown的书写效率。

1. 配置~/.vimrc文件
   1. 第一步配置[Vundle](https://github.com/VundleVim/Vundle.vim)来管理Vim插件，本文不详述；
   2. 添加三个插件（[tabular](https://github.com/godlygeek/tabular)、[vim-markdown](https://github.com/plasticboy/vim-markdown)、[vim-instant-markdown](https://github.com/suan/vim-instant-markdown)）：

          " Markdown Support Markdown语法支持
          Plugin 'godlygeek/tabular'
          Plugin 'plasticboy/vim-markdown'
          " Markdown Preview Markdown预览支持
          Plugin 'suan/vim-instant-markdown'
   3. 安装插件;
       `:PluginInstall`
2. 可以按照自己的喜好进行配置，这里是作者自己定制的[.vimrc](https://gist.github.com/ColdinLee/dfffea3d9cad4f2501ec8fd299ece22a)文件，大家可以参考。

### Markdown基本语法
#### 粗体和斜体

    在这一段话中，你可以看到粗体和斜体的简单用法。当你在书写文档的时候，想要**强调**一些内容，或者引用一些比如：书籍、词语等，可以采用*斜体*字。Markdonw中实现这些非常的容易。你甚至可以将它们***组合***在一起使用。

在这一段话中，你可以看到粗体和斜体的简单用法。当你在书写文档的时候，想要**强调**一些内容，或者引用一些比如：书籍、词语等，可以采用*斜体*字。Markdonw中实现这些非常的容易。你甚至可以将它们***组合***在一起使用。

#### 标题
当你想要更改标题的类型时，可以选择这样的方式：

    # 一级标题
    ## 二级标题
    ### 三级标题
    #### 四级标题
    ##### 五级标题
    ###### 六级标题

这些分别对应HTML中的h1到h6，但是这里需要注意的是，不要忘记#号后面的空格。

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
#### 超链接

    有时，你也许会加入一些超链接，方便跳转。你可以这样做：[点击这里进入Github](www.github.com)

有时，你也许会加入一些超链接，方便跳转。你可以这样做：[点击这里进入Github](www.github.com)

    除了上面的方法，还有另外一种方法也可以创建超链接。可以[谷歌][标签]搜索Markdown超链接，总之[谷歌2][标签]可是学习的必备工具。

    [标签]: www.google.com

除了上面的方法，还有另外一种方法也可以创建超链接。可以[谷歌][标签]搜索Markdown超链接，总之[谷歌2][标签]可是学习的必备工具。

[标签]: www.google.com

#### 换行

    当需要换行时候，可以采用两种方式。一种是：直接在一行的结尾加入两个空格（用--表示）--
    或者只能强制在两行之间加入一个

    空行。

当需要换行时候，可以采用两种方式。一种是：直接在一行的结尾加入两个空格 
或者只能强制在两行之间加入一个

空行。

#### 有序列表和无序列表

    列表是一种常用的表现方式，特别是当你需要概括、总结要点时：
    * 当观点没有顺序之分；
      * 举例一；
      * 举例二；
    * 重要程度相仿时；
    * 可以采用这种方式；
      1. 有序事例一；
      2. 有序事例二；
    * 但是不要忘记*号后面的空格。

列表是一种常用的表现方式，特别是当你需要概括、总结要点时：
* 当观点没有顺序之分；
  * 举例一；
  * 举例二；
* 重要程度相仿时；
* 可以采用这种方式；
  1. 有序事例一；
  2. 有序事例二；
* 但是不要忘记*号后面的空格。

#### 引用

    当你引用到其他作者的话语时，可以采用这样的方式：
    >这里都是引用

当你引用到其他作者的话语时，可以采用这样的方式：
>这里都是引用

#### 代码支持

    当然，最最重要的莫过于代码引用、代码高亮。如下是一个Github风格的语法高亮（四个空格缩进）：  
        python
        def hello_vim_markdown():
            print "hello Markdown!"
 

当然，最最重要的莫过于代码引用、代码高亮。如下是一个Github风格的语法高亮（四个空格缩进）：

    :::python
    def hello_vim_markdown():
        print "hello Markdown!"

#### 写在最后
虽然这里只是简单介绍了常用的Markdown语法，但也要勤加练习才能熟练运用。除此之外，Markdown还存在许多其他强大的扩展，期待你的学习和发现。：）
