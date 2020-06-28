# <center>Markdown语法</center>
### 一、Markdown标题

有两种形式：
* __使用=和-标记一级和二级标题__

示例：
```
我展示的是一级标题
===================
我展示的是二级标题
-------------------
```
效果如下：

---
<center>
我展示的是一级标题
===================
</center>

<center>
我展示的是二级标题
-------------------
</center>

-----


* __使用#号标记__
示例：
```
#一级标题
##二级标题
###三级标题
####四级标题
#####五级标题
######六级标题
```
效果：

---

# <center>一级标题</center>
## <center>二级标题</center>
### <center>三级标题</center>
#### <center>四级标题</center>
##### <center>五级标题</center>
###### <center>六级标题</center>
---


### 二、字体
示例：
```
*斜体文本*  **粗体文本**   ***粗斜体文本***
_斜体文本_  __粗体文本__   ____粗斜体文本___
```
效果：

---
*<center>斜体文本*  **粗体文本**   ***粗斜体文本***
_斜体文本_  __粗体文本__   ___粗斜体文本</center>___


---

###三、分割线
示例：
```
***
* * *
- - -
--------
```

效果：
***
* * *
- - -
--------

###四、删除线

如果需要给文字添加删除线，只需要在文字的两端加上两个波浪线~~
示例：
`~~markdown~~ markdown`
效果：
***
~~<center>markdown~~ markdown</center>

***

###五、下划线
示例：
```
<u>markdown</u> markdown
```
效果：
***
<center><u>markdown</u> markdown</center>

***

###六、脚注
使用[^+标注名称]表示脚注，然后在下方注释脚注的内容。
示例：
```
[^markdown]

[^markdown]:markdown
```
效果：
***
<center>

[^markdown]

</center>

***

[^markdown]:markdown
### 七、列表

* __无序列表__
示例：
```
* 第一项
+ 第二项
- 第三项
```
效果：
***
* 第一项
+ 第二项
- 第三项
___

* __有序列表__
示例：
```
1. 第一项
2. 第二项
3. 第三项
```
效果：
___
1. 第一项
2. 第二项
3. 第三项
___

* __列表嵌套__
1. 第一项
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项
   - 第二项嵌套的第一个元素
   - 第二项嵌套的第二个元素

##八、Markdown 区块
* __基本嵌套__

示例：
```
> 区块应用
> markdown
> markdown
```
效果：
> 区块应用
> markdown
> markdown

* __嵌套区块__

示例：
```
> 最外层
>> 第一层嵌套
>>>第二层嵌套
```
效果：
___
> 最外层
>> 第一层嵌套
>>>第二层嵌套
___

##九、Markdown代码
* __单行代码__
示例：
\`markdown`代码
效果：
___
`markdown`代码
___
* __多行代码__

示例：
```
` ` `
markdown
markdown
` ` `
```
效果：
___
```
markdown
markdown
```
___


##十、Markdown链接

*  __[链接名称]\(链接地址)__

示例：
```
[GitHub](https://github.com/)
```
效果：
____
[GitHub](https://github.com/)
___

*  __<链接地址>__

示例：
```

<https://github.com/>
```
效果：
____
<https://github.com/>
___

* __高级链接__



我们可以通过变量来设置一个链接，变量赋值在文档末尾进行：
示例：

```
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [GitHub][GitHub]
然后在文档的结尾为变量赋值（网址）

  [1]: http://www.google.com/
  [GitHub]: http://www.github.com/
```
效果：

这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [GitHub][GitHub]
然后在文档的结尾为变量赋值（网址）

[1]: http://www.google.com/
[GitHub]: https://www.github.com/

##十一、Markdown图片
* 基本格式：
```
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

示例：
```
![肆零肆 图标](https://github.com/Sumsung524/learngit/blob/master/Student-resources-min.png?raw=ture)

![肆零肆 图标](https://github.com/Sumsung524/learngit/blob/master/Student-resources-min.png?raw=ture "GitHub")
```
效果：
![肆零肆 图标](https://github.com/Sumsung524/learngit/blob/master/Student-resources-min.png?raw=ture)

![肆零肆 图标](https://github.com/Sumsung524/learngit/blob/master/Student-resources-min.png?raw=ture "肆零肆")

* 引用格式
示例：
```
这个链接用 1 作为网址变量 [肆零肆][1].
然后在文档的结尾为变量赋值（网址）

[1]: https://github.com/Sumsung524/learngit/blob/master/Student-resources-min.png?raw=ture
```
效果：
____
这个链接用 1 作为网址变量 [肆零肆][fourzerofour].
然后在文档的结尾为变量赋值（网址）

  [fourzerofour]:https://github.com/Sumsung524/learngit/blob/master/Student-resources-min.png?raw=ture
___
##十二、Markdown表格

Markdown 制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。
示例：
```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```
效果：
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |

* 对齐方式
示例：
```
-: 设置内容和标题栏居右对齐。
:- 设置内容和标题栏居左对齐。
:-: 设置内容和标题栏居中对齐。
```
效果：
___
| 左对齐 左对齐 | 右对齐 右对齐 | 居中对齐 居中对齐 |
| :-| -: | :-: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
___

##十三、Markdown高级技巧
* 支持的HTML元素


`目前支持的 HTML 元素有：<kbd> <b> <i> <em> <sup> <sub> <br>等`

示例
`使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑`
效果：
___
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
___
示例：
`使用 <b>Ctrl</b>+<b>Alt</b>+<b>Del</b> 重启电脑`
效果：
___
使用 <b>Ctrl</b>+<b>Alt</b>+<b>Del</b> 重启电脑
___
示例：
`使用 <i>Ctrl</i>+<i>Alt</i>+<i>Del</i> 重启电脑`
效果：
___
使用 <i>Ctrl</i>+<i>Alt</i>+<i>Del</i> 重启电脑
___
示例：
`使用 <em>Ctrl</em>+<em>Alt</em>+<em>Del</em> 重启电脑`
效果：
____
使用 <em>Ctrl</em>+<em>Alt</em>+<em>Del</em> 重启电脑
___
示例：
`使用 <sup>Ctrl</sup>+<sup>Alt</sup>+<sup>Del</sup> 重启电脑`
效果：
___
使用 <sup>Ctrl</sup>+<sup>Alt</sup>+<sup>Del</sup> 重启电脑
___
示例：
`使用 <sub>Ctrl</sub>+<sub>Alt</sub>+<sub>Del</sub> 重启电脑`
效果：
___
使用 <sub>Ctrl</sub>+<sub>Alt</sub>+<sub>Del</sub> 重启电脑
___
示例：
`使用 <br>Ctrl</br>+<br>Alt</br>+<br>Del</br> 重启电脑`
效果：
___
使用 <br>Ctrl</br>+<br>Alt</br>+<br>Del</br> 重启电脑
___

#####转义
Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符

__Markdown 使用反斜杠转义特殊字符__
```
\*\*星号*\*\
**星号**
```
\*\*星号*\*\
**星号**

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
```
\   反斜线
`   反引号
*   星号
_   下划线
{}  花括号
[]  方括号
()  小括号
#   井字号
+   加号
-   减号
.   英文句点
!   感叹号
```


