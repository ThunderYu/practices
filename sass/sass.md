[参考课程：Sass入门篇（慕课网）](http://www.imooc.com/learn/311)

## 1. 什么是CSS预处理器？

#####定义：

“CSS 预处理器用一种专门的编程语言，进行 Web 页面样式设计，然后再编译成正常的 CSS 文件，以供项目使用。CSS 预处理器为 CSS 增加一些编程的特性，无需考虑浏览器的兼容性问题”，例如你可以在 CSS 中使用变量、简单的逻辑程序、函数等等在编程语言中的一些基本特性，可以让你的 CSS 更加简洁、适应性更强、可读性更佳，更易于代码的维护等诸多好处。

## 2. 什么是Sass？

Sass 是一门高于 CSS 的元语言，它能用来清晰地、结构化地描述文件样式，有着比普通 CSS 更加强大的功能。
Sass 能够提供更简洁、更优雅的语法，同时提供多种功能来创建可维护和管理的样式表。

## 3. Sass编译

### 3.1 命令编译

##### 单文件编译

`sass <要编译的Sass文件路径>/style.scss:<要输出CSS文件路径>/style.css`

##### 多文件编译

`sass sass/:css/`
上面的命令表示将项目中“sass”文件夹中所有“.scss”(“.sass”)文件编译成“.css”文件，并且将这些 CSS 文件都放在项目中“css”文件夹中。

##### 监测编译

`sass --watch <要编译的Sass文件路径>/style.scss:<要输出CSS文件路径>/style.css`

### 3.2 GUI界面工具编译

* [Koala](http://koala-app.com/) ☆
* [Compass.app](http://compass.kkbox.com/)
* [Scout](http://mhs.github.io/scout-app/)
* [CodeKit](https://incident57.com/codekit/index.html) ☆
* [Prepros](https://prepros.io/)

### 3.3 自动化编译

使用Grunt、Gulp、Webpack等自动化工具配置Sass的编译。

> 编译注意事项：在Sass的编译的过程中，是不支持“GBK”编码的。所以在创建 Sass 文件时，就需要将文件编码设置为“utf-8”。

## 编译样式风格

### 1. 嵌套输出方式 nested

在编译的时候带上参数 `--style nested`

    sass --watch test.scss:test.css --style nested

编译输出样式：

```css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none; }
nav li {
  display: inline-block; }
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none; }
```

### 2. 展开输出方式 expanded

在编译的时候带上参数 `--style expanded`

    sass --watch test.scss:test.css --style expanded

编译输出样式：

```css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

### 3. 紧凑输出方式 compact

在编译的时候带上参数 `--style compact`

    sass --watch test.scss:test.css --style compact

编译输出样式：

```css
nav ul { margin: 0; padding: 0; list-style: none; }
nav li { display: inline-block; }
nav a { display: block; padding: 6px 12px; text-decoration: none; }
```

### 4. 压缩输出方式 compressed

在编译的时候带上参数 `--style compressed`

    sass --watch test.scss:test.css --style compressed

编译输出样式：

```css
nav ul{margin:0;padding:0;list-style:none}nav li{display:inline-block}nav a{display:block;padding:6px 12px;text-decoration:none}
```

## Sass的基本特性-基础

### 1.声明变量

![image](https://github.com/ThunderYu/practices/raw/master/sass/images/varible.jpg)