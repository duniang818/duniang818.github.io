# jupyter notebook
---
1. [安装Anaconda](https://www.anaconda.com/), 安装好Anaconda后，打开Anaconda, 点击安装jupyter notebook
2. 运行，网页查看效果，默认地址：*http://localhost:8888*
3. 设置jupyter notebook主题[GitHub jupyter notebook themes](https://github.com/dunovank/jupyter-themes)  
```
pip install jupyterthemes
pip install --upgrade jupyterthemes
```
4. chesterish主题设置  
查看主题：jt -l  
设置主题：jt -t chesterish -T  
恢复默认主题：jt -r  
5. 对默认的工作路径进行修改，首先我们打开anaconda cmd窗口，然后执行命令 jupyter notebook --generate-config,在用户目录下找到.jupyter文件，并打开，修改notebook_dir这个值为需要的工作路径实际值。
6. 常用快捷键  
你需要查看菜单栏上的help-keyboard shortcuts，包含了最新的快捷键列表。另外可以用ctrl+shift+p组合键，能调出search框，哪里不会搜哪里。  
run：Ctrl+enter  
edit mode：enter  
exit edit mode(enter command mode):Esc  
insert cell below:b  
insert cell above:a  
delete cell:dd  

在一个cell中（在command模式下）

1. 按下 y, 进入Code;

2. 按下m, 进入Markdown;
7. 在notebook和code中切换  
在command模式下按下 y, 进入Code;按下m, 进入Markdown;  
# markdown  
---
*jupyter notebook自带，不需要单独安装，简单介绍一下常用的语法*  
+ 推荐一款编辑器[typora](https://www.typora.io/#)  
+ 标题：#，##，##
+ 无序列表：+，-，*
+ 有序列表：罗马数字+英文句号，比如：1. ，2. ，
+ 分割线：行首三个以上的-，*，中间可以加空格，但是不可以有其它字符
+ 换行：连续两个空格+回车  
+ 不转义Markdown语法：用代码块的符号，在esc下面的那个键  
+ 行首缩进1个全角字符：`&emsp`;  
+ &emsp;检查是否真的缩进了1个字符  
+ &emsp;&emsp;检查是否真的缩进了两个字符  
+ 引用:>
>一级引用
>>二级引用  

+ 代码块：一行代码“`”,多行代码三个“`”开始和结束  
`import os`  
```
pip install jupyterthemes
pip install --upgrade jupyterthemes
```
+ 链接：[This link](http://example.NET/) has no title attribute.
+ 插入图片：
![插入图片URL]() 
# 公式编辑器：LaTex  
---
1.单行公式：$s=\pi*r^2$   
2.行间公式：$$r=\pi*r^2$$
3.公式中的希腊字母：反斜杠+字母，`\alpha`，$\alpha$  
4.开方：$y=\sqrt{x^2+x^4}+\sqrt[4]{x^3}$  
5.分数：$y=\frac{x}{x^2}$  
6.加帽：帽子有很多，`\hat{A}`,`\widehat{A}`,`\tilde{A}`，$\hat{A}$，$\widehat{A}$，$\tilde{A}$  
# 微信公众号使用Markdown，LaTex
---
找一个在线Markdown编辑器，将Markdown文本复制，粘贴后，能看见预览，在预览侧点击复制，在粘贴到公众号图文编辑里面就好了。  
目前这个[Md2All](http://md.aclickall.com/)能很好的转换md,latex公式到微信公众号。
Md2All其实是将公式全部转换为图片，然后上传的，经常会有失败，可以先将转换好的图片保存在素材库，直接引用素材库的图片就好了。

