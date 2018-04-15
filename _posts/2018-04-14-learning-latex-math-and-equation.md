---
layout: post
title: 初识LaTeX数学公式编辑
tags: [skill]
---


[LaTeX](https://zh.wikipedia.org/wiki/LaTeX)是一种基于TeX的排版系统，其将内容编写与排版呈现完全分离，使得文档书写者只需使用简单的文档结构标签，让LaTeX系统负责这些结构的格式和布局，从更加专注于内容的创作，而不必关心如何进行布局排版。需要特别指出的是，LaTeX在复杂数学公式、表格书写方面，非常的强大，可以大大加快此类场景的书写效率。本文就是在学习LaTeX过程中的一些总结。

## LaTeX介绍

对于我们大多数人来说，KeyNote、MS Word等文字处理工具就已经能够满足大多数使用场景了，且这类工具都非常直观、易用，学习曲线也较为容易。而对比LaTeX，它其实更像是一门“编程语言“，存在一定的学习曲线，需要记忆不少符号来满足特定的需要。

说到这里，你可能觉得为什么要费时费力学习它呢？LaTeX作为较为专业的排版系统，目前在国内仍是比较小众的，但其在国外高校、出版社是非常流行的。正是因为其强大的功能，几乎能够实现你想要的任何东西，才会被大家所青睐。如果你是一个对文档要求很高的创作者，或者是想要一窥究竟的好奇者，那么就应该去了解一下这门神奇语言！

## KaTeX介绍
KaTeX是一个在前端通过LaTeX语法展示数学公式的JS项目（类似的还有MathJax），它的特点是API非常简单、没有任何依赖以及浏览侧快速渲染。[主页](https://khan.github.io/KaTeX/)。

**注：本文主要聚焦于如何用KaTeX实现数学公式，用以书写Blog。其他关于LaTex的学习资料见文末。**

## 数学公式编辑

### 准备工作
* 准备本地LaTeX环境
  1. 安装LaTeX。可以从LaTeX项目的官网获取；[链接](https://www.latex-project.org/get/)
  2. 启动LaTeXiT。LaTeX iT顾名思义，就是直接将对应的LaTeX语句转化为显示结果（可另存为图片格式）；
* 使用KaTex或MathJaX在线编辑
  1. Markdown和LaTeX在线编辑器。[链接](https://upmath.me/)
  2. 在前端展示数学公式，可以使用KaTex或MathJaX。[链接](https://www.intmath.com/cg5/katex-mathjax-comparison.php)（关于两者渲染速度的对比）。

KaTeX支持大部分常用的数学语言，可以满足日常记录Blog。具体KaTeX对LaTeX的支持情况见[链接](https://github.com/Khan/KaTeX/wiki/Things-that-KaTeX-does-not-%28yet%29-support)。

### 单行多行输出

在KaTeX（MathJaX）中默认所有的数学公式都是在`$$ ... $$`之间。

如：要在行内书写正弦函数$$ f(x) = \sin{2x}$$，对应于

若要整行书写，则为：

$$ f(x) = \cos{2\pi} $$

```latex
$$ f(x) = \cos{2\pi} $$
```

有时在推导公式时，需要连续多行输出，可以使用`\begin{aligned} ... \end{aligned}`。

$$ 
\begin{aligned}
f(x) & = & \sin(2\pi - x) \\ 
     & = & \sin(x) 
\end{aligned}
$$

```latex
$$ 
\begin{aligned}
f(x) & = & \sin(2\pi - x) \\ 
     & = & \sin(x) 
\end{aligned}
$$
```

或者一些更加复杂的公式 $$ \left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right) $$

```latex
$$ \left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right) $$
```

### 幂和下标

幂和下标的表示使用的也是直觉化的方式，**^**表示幂次，**_**表示下标。若幂或下标涉及多个表达式，可以使用括号**{ ... }**和**( ... )**。

$$ k_{n+1} = k_{n}^2 + 1 $$

```latex
$$ k_{n+1} = k_{n}^2 + 1 $$
```

### 分数与二项式

分数的书写使用`\frac{分子}{分母}`。类似的二项式使用`\binom{n}{k}`。

$$ \binom{n}{k} = \frac{n!}{(n-k)!k!} $$

```latex
$$ \binom{n}{k} = \frac{n!}{(n-k)!k!} $$
```

如果要在行内写诸如$$ \bar{x} = \sum_{n=1}^N{x_n}/{N} $$的式子，可以采用`{分子}{分母}`的形式。


```latex
$$ \bar{x} = \sum_{n=1}^N{x_n}/{N} $$
```

### 积分与微分
积分与微分是我们常常需要书写的形式，在KaTex中书写也是非常简单的。积分`\int_{上限}^{下限}`。

$$ f(x) = \int_0^{\infty} e^x dx $$

```latex
$$ f(x) = \int_0^{\infty} e^x dx $$
```

而微分则是通过分数或者Nabla算子的方式表达。

$$ {df(x)}/{x} = e^x |_0^{\infty} $$

```latex
$$ {df(x)}/{x} = e^x |_0^{\infty} $$
```

$$ \nabla = \left( \frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z} \right) $$

```latex
$$ \nabla = \left( \frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z} \right) $$
```

### 矩阵

矩阵的书写方式也是比较相似的，`\begin{bmatrix} ... \end{bmatrix}`。这里只选择一种作为范例，其他的类型可以参见[KaTeX支持的矩阵表达方式](https://khan.github.io/KaTeX/function-support.html#environments)。

$$
A = \begin{bmatrix}
      1 & 0 & 0 \\
      0 & 1 & 0 \\
      0 & 0 & 1
    \end{bmatrix}
$$

```latex
$$
A = \begin{bmatrix}
      1 & 0 & 0 \\
      0 & 1 & 0 \\
      0 & 0 & 1
    \end{bmatrix}
$$
```

### 其他数学符号

LaTeX本身有非常多的数学公式、符号书写方式，前面只是简单讲述了几种常用的情形，下面在简单汇总下常用的一些数学符号，方便日常使用。:)

符号                          | 命令
----------------------------- | -------------
$$ \sqrt{x} $$                | `\sqrt{x}`
$$ \sqrt[3]{x} $$             | `\sqrt[3]{x}`
$$ \Delta \Theta \Lambda \Pi \Sigma \Phi \Psi \Omega $$ | `\Delta \Theta \Lambda \Pi \Sigma \Phi \Psi \Omega`
$$ \varDelta \varTheta \varLambda \varPi \varSigma \varPhi \varPsi \varOmega$$ | `\varDelta \varTheta \varLambda \varPi \varSigma \varPhi \varPsi \varOmega`
$$ \alpha \beta \gamma \delta \epsilon \zeta \eta \theta \lambda \mu $$ | `\alpha \beta \gamma \delta \epsilon \zeta \eta \theta \lambda \mu`
$$ \sigma \upsilon \phi \chi \psi \omega \varepsilon \varsigma \varphi $$ | `\sigma \upsilon \phi \chi \psi \omega \varepsilon \varsigma \varphi`
$$ \partial \nabla $$       | `\partial \nabla`
$$ \forall x \in X $$       | `\forall x \in X`
$$ \exists y \leq \epsilon $$ | `\quad \exists y \leq \epsilon`

## 总结

LaTeX就是如此简单、强大！通过学习基本的LaTeX数学公式编辑方法，就能基本满足日常写Blog时的公式推导，算法描述。不过LaTeX可远不止如此，它甚至可以用来用画复杂图形、写复杂化学物质、甚至绘制棋谱、创作五线谱等。当然，这些有趣的场景都等待着你的学习和发现。:)

#### 参考文献
1. 维基百科。介绍了LaTeX的历史，以及和TeX的关系。[链接](https://en.wikipedia.org/wiki/LaTeX)
2. KaTaX项目。本文使用的LaTeX前端数学公式实现JS，可以参考Github项目。[链接](https://khan.github.io/KaTeX/)
3. LaTeX Wiki。非常详细的LaTeX Wiki，可以用于日常查阅。[链接](https://en.wikibooks.org/wiki/LaTeX)
4. KaTeX vs. MathJaX。两种流行的LaTeX前端方案的渲染对比。[链接](https://www.intmath.com/cg5/katex-mathjax-comparison.php)
5. LaTeX符号转换。LaTeX支持非常多的符号，很难全部都记住，这个网站提供了一种便捷的方案，通过画图给出对应的LaTeX命令。[链接](http://detexify.kirelabs.org/classify.html)
