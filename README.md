# 延安大学本科毕业论文Latex模板2019

标签（空格分隔）:  Latex

---


### 项目说明

YAUthesis是延安大学非官方的毕业论文(设计)的LaTeX模板. 目前本校还未有Latex模板甚至Word模板.  我对武汉大学黄正华老师早些年写的模板进行了修改,以更好的适应延安大学的写作规范. 


旨在帮助延安大学毕业生高效的完成毕业论文写作, 既可以提高论文排版质量又可以将更多的精力放在论文内容的输出上, 合理使用本模板可以大大减轻延安大学毕业生在毕业论文撰写过程中的排版工作量.  

该由数计学院2015级毕业生赵驰同学制作而成. 一个人精力有限, 只能适配最新版的环境. 所以使用该模板请按照我下面所说的配置按照软件, 这样才能将编译失败率降到最低. 

**环境说明**

TeX Live 在 macOS/OS X 上的名字是 MacTeX. 所以mac用户可以安装MacTex代替TeX Live. 
windows/Linux: Texlive2018+VScode 或者 Texlive2018+Texstudio. 
mac: MacTex2018+VScode 或者 MacTex2018+Texstudio. 
vscode 需要两个插件: LaTeX language support和LaTeX Workshop. 
后面我会提到环境配置方法. 

预览图如下: 

**封面页:**

![封面页][1]

**声明页:**

![声明页][2]

全文预览地址如下: [https://github.com/MLZC/YAUthesis/releases/download/V0.1/YAUthesis-sample.pdf][3]

### 环境安装

这里只写windows安装过程, 对于mac和Linux用户而言, 安装软件肯定难不倒你们. 

#### windows下Texlive2018的安装与配置

* 下载

    TeX Live 的当前版本是 2018, 你可以从官方站点下载它们的安装包.
    
    [http://mirror.ctan.org/systems/texlive/Images/texlive2018.iso
    ][4]
    
    如果你发现下载速度很慢, 可以尝试清华大学和中国科技大学的镜像站. 
    
    [https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/texlive2018.iso
    ][5]
    [https://mirrors.ustc.edu.cn/CTAN/systems/texlive/Images/texlive2018.iso][6]

* 安装
    
    对于 Windows 8 及更高版本的微软用户, 可以直接加载下载得到的光盘镜像. (其他用户则需要下载虚拟光驱加载镜像)然后, 执行安装脚本, 将 TeX Live 安装在你的系统中. 
    
    Windows 用户右键单击 install-tl-advanced.bat, 以管理员权限执行; 
    ![安装][7]
    按照上图所示选择好之后点击"安装 TeXLive", 接下来等就是了. 
    
    * 安装版本确认
    安装完成之后, win+r输入cmd, 分别输入: 
    ```
    tex -v
    latex -v
    xelatex -v
    pdflatex -v
    ```
    如果看到的版本信息能够正常输出, 那么TeX Live的安装就是成功的！
    
    接下来是编辑器的安装, TeXstudio和VScode二选一即可. 
#### TeXstudio安装

TeXstudio有很多按钮, 无需记住太多命令就可上手, 输入数学公式比较方便,比较适合小白. 如下图所示: 
![TeXstudio界面][8]

* 下载

    下载地址: [http://texstudio.sourceforge.net/][9], 直接点击下载安装就可以. 

* 配置

    打开TexStudio->option->Configure TexStudio->Build, 设置成如下配置: 
    
    ![TexStudio配置][10]
    选中Commands, 设置成如下配置: 
    
    ![命令设置][11]
    
    中文设置方法: 选中General将Language中的en改成zh_CN即可. 
    
    这样, Texstudio就安装成功了. 

#### VScode LaTeX环境设置

VScode界面美观, 定制化很强, 如下所示: 

![VScode界面][12]

* 下载安装

    自行下载VScode并安装LaTeX language support和LaTeX Workshop这两个插件. 

* 插件配置

    点击左下角->settings,搜索<code>latex-workshop.latex.recipes</code>. 点击<code>Edit setttings.json</code>. 
    ![vscode][13]
    
    将下列代码复制粘贴到右边即可.
    
    
    ```json
    {
        "latex-workshop.latex.tools": [
    	    {
    	        "name": "xelatex",
    	        "command": "xelatex",
    	        "args": [
    	          "-synctex=1",
    	          "-interaction=nonstopmode",
    	          "-file-line-error",
    	          "%DOC%"
            	]
            },
    		{
    	        "name": "pdflatex",
    	        "command": "pdflatex",
    	        "args": [
    	          "-synctex=1",
    	          "-interaction=nonstopmode",
    	          "-file-line-error",
    	          "%DOC%"
    	        ]
    	    },
    	    {
    	        "name": "bibtex",
    	        "command": "bibtex",
    	        "args": [
    	          "%DOCFILE%"
    	    	]
    	    }
    	],
        "latex-workshop.latex.recipes": [
            {
              "name": "latexmk",
              "tools": [
                "latexmk"
              ]
            },
            {
              "name": "pdflatex -> bibtex -> pdflatex*2",
              "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
              ]
            }
          ],
          
    }
    
    ```



### 获取YAUthesis

下载地址: [https://github.com/MLZC/YAUthesis/releases][14]
下载最新版本解压就可以.

**注意: 文件所在路径和文件名不要有中文, 不然会编译失败.**

### 使用YAUthesis

拿到YAUthesis应该怎样用？请看以下步骤.

#### TeXstudio使用方法

1. 打开TeXstudio;
2. 用TeXstudio打开文件夹里面的YAUthesis.tex文件;
3. 仔细阅读文件夹里面的YAUthesis.pdf; 
4. 根据中文说明进行填空;
5. 点击下图所示按钮编译并查看.
![TexStudioBuild][15]

#### VScode使用方法
1. 打开VScode;
2. File->Open Folder->选中解压出来的文件夹;
3. 点击YAUthesis.tex文件;
4. 仔细阅读文件夹里面的YAUthesis.pdf; 
5. 根据中文说明进行填空;
6. 点击下图选项;
![VScode1][16]
7. 点击Build LaTeX project;
8. 点开View LaTeX PDF->View in VSCode tap 如下图所示.
![VScode2][17]

### 技术交流

如有问题请在项目Issue模块提出, 或者邮件联系作者(dandanv5@hotmail.com).

  [1]: http://image.i-ll.cc/blog/20190214/7xUqY1aI0UlI.png
  [2]: http://image.i-ll.cc/blog/20190214/GmUG6niVGzYY.png
  [3]: https://github.com/MLZC/YAUthesis/releases/download/V0.1/YAUthesis-sample.pdf
  [4]: http://mirror.ctan.org/systems/texlive/Images/texlive2018.iso
  [5]: https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/texlive2018.iso
  [6]: https://mirrors.ustc.edu.cn/CTAN/systems/texlive/Images/texlive2018.iso
  [7]: http://image.i-ll.cc/blog/20190214/VSAujx6AcK8I.png
  [8]: http://image.i-ll.cc/blog/20190214/061opnbrvOqo.png
  [9]: http://texstudio.sourceforge.net/
  [10]: http://image.i-ll.cc/blog/20190214/rGuUhFMUQEJq.png
  [11]: http://image.i-ll.cc/blog/20190214/3T7iDNvBBUL9.png
  [12]: http://image.i-ll.cc/blog/20190214/9PFX385kxDp6.png
  [13]: http://image.i-ll.cc/blog/20190214/jObJi1ifByoT.png
  [14]: https://github.com/MLZC/YAUthesis/releases
  [15]: http://image.i-ll.cc/blog/20190214/TfYcA3BXBIlH.png
  [16]: http://image.i-ll.cc/blog/20190214/ITrDJ6W2WxRK.png
  [17]: http://image.i-ll.cc/blog/20190214/JjAJ7BoBHw3o.png