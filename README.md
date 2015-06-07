# Vim-zsh-config

<h1>一、VIM插件</h1>

<h2>截图</h2>
 
<img src="https://raw.githubusercontent.com/mupengX/Vim-zsh-config/master/img/vim.png" style="max-width:100%;">
<h2>1. pathogen</h2>

 pathogen是一个采用bundle的理念来管理插的插件。pathogen在.vim目录下建立bundle文件夹，所有插件都在目录管。

   <h3>安装</h3>
   
    在.vim文件夹下建立autoload和bundle目录
    
    从下载地址 https://github.com/tpope/vim-pathogen 获取pathogen.vim文件，
    将其复制到autoload目录下，在.vimrc文件中增加如下代码：
    
    call pathogen#infect()

<h2>2. NERDTree</h2>
    
    NERDTree是Vim最常用的插件之一，可以在Vim运行时显示目录和文件结构

    <h3>安装</h3>
    
    进入.vim/bundle目录执行git clone git://github.com/scrooloose/nerdtree.git
    
    下载完成后，在bundle下会多出一个nerdtree的文件夹，所有相关插件都在该文件夹下
    
    在Vim中运行:Helptags来生成NERDTree的在线帮助tags
    
    使用说明
    
    打开Vim，输入:NERDTree，即可呼出执行Vim命令的当前目录的文件目录。
    为了方便使用，我在.vimrc中定义了快捷键F7，可以用F7打开NERDTree，你可以定义自己习惯的快捷键。
    
<h2>3. Powerline</h2>
    
    Powerline是Vim的一个非常漂亮的状态栏插件，安装了Powerline之后，Vim底部将会出现一个增强型状态栏，
    当Vim处于NORMAL、INSERT、BLOCK等状态时，状态栏会呈现不同的颜色，同时状态栏还会显示当前编辑文件
    的格式（uft-8等）、文件类型（java、xml等）和光标位置等。

   <h3> 安装 </h3>
    
    进入.vim/bundle目录
    执行git clone git://github.com/Lokaltog/vim-powerline.git
    在.vimrc中设置状态栏主题
    
     "powerline{
     
     set guifont=PowerlineSymbols\ for\ Powerline
     
     set nocompatible
     
     set t_Co=256
     
     let g:Powerline_symbols = 'fancy'
     
     "}
     
<h2>4. ctags</h2>
  
	通过ctags -R命令可以对当前目录下源代码中的类、函数、方法、变量、宏等元素进行索引处理，
	并生成索引文件。Vim使用ctags生成的tag文件，即可实现IDE中常用的代码跳转功能。

  <h3>安装</h3>
  
  	对于Ubuntu，可以使用如下命令安装：
  	sudo apt-get install ctags
  	安装完成后在终端键入ctags--help，看到正常的帮助信息就说明安装成功了。
  
<h2>5. taglist</h2>
  
	taglist是Vim的一个代码浏览的插件，类似IDE中的Outline视图，可以根据不同语言
	的代码显示代码中的包、类、接口、方法、函数、变量、属性等内容。taglist同样需要依赖ctags命令生成tag

  <h3> 安装 </h3>
  
  进入~/.vim/bundle目录执行： git clone git://github.com/vim-scripts/taglist.vim.git
  
  在.vimrc文件设置taglist的配置信息
  
  "taglist{
  
    let Tlist_Show_One_File = 1            "只显示当前文件的taglist，默认是显示多个
    
    let Tlist_Exit_OnlyWindow = 1          "如果taglist是最后一个窗口，则退出vim
    
    let Tlist_Use_Right_Window = 1         "在右侧窗口中显示taglist
    
    let Tlist_GainFocus_On_ToggleOpen = 1  "打开taglist时，光标保留在taglist窗口
    
    let Tlist_Ctags_Cmd='/opt/local/bin/ctags'  "设置ctags命令的位置
    
    nnoremap <leader>tl : Tlist<CR>        "设置关闭和打开taglist窗口的快捷键
    
    "}
    
    taglist参数介绍：
    
    Tlist_Ctags_Cmd：设置ctags命令的位置
    
    Tlist_Use_Horiz_Window：设置为1时，taglist窗口横向显示。默认纵向显示
    
    Tlist_WinHeight：设置taglist窗口的宽度
    
    Tlist_WinWidth：设置taglist窗口的高度
    
    Tlist_Show_One_File：设置Tlist_Show_One_File为1则只显示当前文件的taglist，缺省显示多个文件中的tag
    
    Tlist_Sort_Type：taglish默认按tag在文件中出现的顺序进行排序，设置为"name"并以tag名字进行排序
    
    Tlist_Exit_OnlyWindow：设置为1时，如果taglist是最后一个窗口，则退出vim
    
    Tlist_Use_Right_Window：设置为1时，taglist窗口出现在右侧，缺省显示在左侧
    
    Tlist_Auto_Open：如果想在启动VIM后自动打开taglist窗口，该参数设置为1
    
    Tlist_Close_On_Select：如果想在选择了tag后自动关闭taglist窗口，该参数设置为1
    
    Tlist_GainFocus_On_ToggleOpen：设置为1时，打开taglist光标保留在taglist窗口
    
    当使用vim打开某个程序文件时，我们可以用:Tlist打开taglist窗口，如果该程序具备类、
    接口、属性等元素，就会在taglist窗口显示出来。
    些常用快捷键来操作taglist：
    
    通过光标选择tag，回车可以跳到定义该tag的程序位置
    
    选中tag时按空格键，会在状态栏下方显示该tag的完整定义
    
    x，横向放大或缩小taglist窗口
    
    =，折叠所有的tag
    
    +，打开所有的tag
    
    
   <h1>二、终极shell：ZSH</h1> 
   
   <h2>截图</h2>
   <img src="https://raw.githubusercontent.com/mupengX/Vim-zsh-config/master/img/zsh.png" style="max-width:100%;">
   
   <h3>安装zsh</h3>
   Redhat Linux, 执行：sudo yum install zsh
   Ubuntu Linux, 执行：sudo apt-get install zsh
   
   <h3>安装oh my zsh</h3>
   
    自动安装：
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
    
    手动安装：
    git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
    cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
