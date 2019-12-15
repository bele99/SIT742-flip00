# FLIP(00) FAQ

Hi everyone, this is a FAQ document about FLIP (00). 

This is also a document that encourages everyone to upload questions.

**1.** *GitFlow*  和 *LaTexDiff* 的操作流程

建议自己寻找资料学习操作流程，*GitFlow*和*LaTexDiff*是比较基本的工具，多练习几遍就可以掌握。

提供参考博客：

[Blog 1]: https://blog.tulip.org.au/2018/07/31/Tools-LaTeX/
[Blog 2]: https://coco.tulip.org.au/post/git-latexdiff/

**2.** *Git LaTexDiff* 生成的文档不能显示*GitInfo*信息？

> 我的poster已经弄出来了，是一个比较意外的bug导致的生成失败。具体来说，是poster模板里不能在数学环境/文件路径之外的地方出现下划线_。在report和slide里都没有这个问题，所以一直没想到。
>
> （Answer by 周佳绘）

**3.** *Tex* 编辑器是不是不能共存在系统变量的路径上?

只需要选择一个适合的 *Tex* 编辑器即可，不需要安装多个编辑器。一般来说，首先，为了搭建 *LaTeX* 工作环境，你需要安装：

- *TeX Live* 或者 *MiKTeX* 
- *Visual Studio Code*
- *LaTeX Workshop （VS Code 插件）*

安装和配置tex推荐博客：

[Blog1]: https://www.latexstudio.net/archives/12260.html
[Blog2]: https://www.cnblogs.com/1625--H/p/11524968.html
[Blog3]: http://www.wenxingsen.com/blog/blogdetail.php?pageid=524

**4.** *LaTexDiff* 形成不了差异文件？

> 把功能分支完成（merge到develop分支），然后推送更改到远程仓库，这样以后*LaTexDiff* 显示正常。（Answer by 徐荣欣）

**5.** 为什么直接用 *TexStudio* 编译，*GitInfo* 是有效的。但使用 *Git LatexDiff* 生成的差异文档，*GitInfo* 不生效？

[解决方法 by 周佳绘]: http://blog.sanhuax2.xyz/

**6.** 使用 *TexStudio+TexLive* 编译 *Slides* 会出现编译不出来的情况?

可能是编译命令没有设置好的问题，如编译slides命令需要设置为：

*user0: LaTex.DVIPS.PS2PDF*

*latex --synctex=1 -interaction=nonstopmode --shell-escape %.tex | dvips -o %.ps %.dvi| ps2pdf %.ps*

​      ![img](https://uploader.shimo.im/f/d4c2X0gqZXcpgFpU.png!thumbnail)      

**7.** *LaTexDiff*生成差异文件一直报错？

​        ![img](https://uploader.shimo.im/f/uYkHBfB2E708l8d2.png!thumbnail)      

解决方案很简单，就是按照上面的提示，在原有的命令上加 *--pdf-viewer CMD*

