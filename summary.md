# 快速查询命令

记录了一些常用命令

### 一、tmux分屏

| 功能             | 命令                                                         |
| ---------------- | ------------------------------------------------------------ |
| 新建             | `tnew 会话名`（需要在.vimrc中设置alias）或者直接`tmux new -s 会话名` |
| 垂直分割         | `C-b %` （C-b表示ctrl+b组合键，下同）                        |
| 水平分割         | `C-b "`                                                      |
| 调整窗口大小     | `C-b  C-方向键`                                              |
| 列出会话         | `tmux ls`                                                    |
| 进入某个会话     | `tmux attach -t 会话名`                                      |
| 关闭当前窗口     | `C-b x`                                                      |
| 关闭会话，不保存 | `C-b &`                                                      |
| 切换标签         | `C-b 方向键`                                                 |

### 二、已安装的常用插件命令

| 功能  注： <leader> 设置为英文逗号 ，    | 快捷键                                                       |
| ---------------------------------------- | ------------------------------------------------------------ |
|YCM补全|`C-p`（insert mode）|
|匹配括号移动|`%`|
|匹配当前光标所在单词|`#`  或  `*` |
|快速定位到某行|`行号 + shift-g`|
| 选择整个单词                             | 空格                                                         |
| Esc                                      | `C-c` 或者 `C-[`                                             |
| 手动打开 NERDTree                        | `<leader>g`                                                  |
| 使用NERDTree找到文件所在位置             | `<leader>v`                                                  |
| 跳转到上一个窗口/其他方向窗口            | `C-w p` / `C-w + hjkl`                                       |
| 文件搜索器 （ctrlp只能从根目录开始搜索） | `C-p`（normal mode）                                           |
| 快速定位                                 | `ss 搜索词`                                                  |
| 成对编辑（不修改符号内文本）             | `ds + 要删除的符号` （delete a surrounding）                 |
|                                          | `cs + 原符号 + 要修改的符号`（change a surrounding）         |
|                                          | `ys + iw + 要增加的符号` （you add a surrounding）           |
| 代码项目中模糊搜索一些文本               | `Ag + [PATTERN]`  模糊搜索字符串                             |
|                                          | `Files + [PATH]` 模糊搜索目录                                |
| Python格式化                             | `:Neoformat`                                                 |
| Python跳转到函数定义                     | `C-]`                                                        |
| tagbar浏览代码结构                       | `<leader>t`                                                  |
| 高亮感兴趣的单词                         | `<Leader>k` 光标移动到感兴趣的单词上按,k                     |
|                                          | Navigate highlighted words with `n` and `N`                  |
| 快速注释代码                             | `gcc`                                                        |
| 批量搜索替换(可对整个文件夹操作)         | 例如要把当前文件夹代码中的item替换为test<br />`:Far item test **/*`   `（**表示上层目录，*表示当前目录）` |
|粘贴模式|`F2`(插入模式下)|
|||


### 三、Vim常用内置命令

| Vim模式及插入模式技巧      | 命令                                                         |
| -------------------------- | ------------------------------------------------------------ |
| 普通模式下全局替换         | `% s/foo/bar/g`  （s代表switch。将所有foo替换为bar，g表示全局替换） |
| 可视模式                   | 使用`V`选择行、使用`ctrl+v`进行方块选择                      |
| 插入模式                   | ctrl h 删除上一个字符                                        |
|                            | ctrl w 删除上一个单词                                        |
|                            | ctrl u 删除当前行                                            |
| 终端命令中的其他快捷键     | ctrl a 移动到开头                                            |
|                            | ctrl e 移动到结尾                                            |
|                            | ctrl b 光标前移                                              |
|                            | ctrl f 光标后移                                              |
| 快速切换insert和normal模式 | 使用ctrl c代替esc（可能会中断某些插件） 或者ctrl [           |
|                            | `gi` 快速跳转到最后一次编辑的地方并进入插入模式              |

| Vim快速移动   | 命令                                                         |
| ------------- | ------------------------------------------------------------ |
| 单词间移动：  | w/W 移动到下一个word/WORD开头                                |
|               | e/E 移动到下一个word/WORD结尾                                |
|               | b/B 移动到上一个word/WORD开头（backward）                    |
| 行间搜索移动: | f{char} 可以移动到char字符上，t移动到char的前一个字符        |
|               | ; 继续搜该行下一个 , 继续搜该行上一个 F 表示反过来搜光标前面的字符 |
| 垂直移动      | ss + char （easy-motion）                                    |
| 页面移动      | ctrl u 、ctrl f 上下翻页   zz 把当前行置为屏幕中间           |
|               | ctrl o 快速返回上个位置                                      |
|               | H/M/L 跳转到文件开头、中间和结尾                             |

| Vim快速增删改查 | 命令                                                         |
| --------------- | ------------------------------------------------------------ |
| Vim快速删除     | daw（delete around word）快速删除一个单词  diw删除单词但不删除单词周围空格 |
|                 | dt) 删除直到右括号内所有内容   d$ 快速删除到行尾             |
| Vim快速修改     | caw  删除当前单词并进入插入模式(change a word）C删除整行并进入插入模式 |
| Vim查询         | 使用/或?进行前向/反向搜索                                    |
|                 | 使用n/N跳转到下一个或者上一个匹配                            |
|                 | 使用*或者#进行当前单词的前向和后向匹配                       |
|删除竖列|`C-d` 选择中后按d删除|

| Vim搜索替换        | 命令                                                        |
| ------------------ | ----------------------------------------------------------- |
| vim替换命令        | `:[range] s[ubstitute]/{pattern}/{string}/[flags]`          |
|                    | range表示范围 比如 :10,20 表示10-20行，%表示全部            |
|                    | pattern是要替换的模式，string是替换后文本                   |
|                    | flags 是替换标志位：                                        |
|                    | g（global）表示全局范围内执行                               |
|                    | c（confirm）表示确认，可以确认或者拒绝修改                  |
|                    | n（number）报告匹配到的次数而不替换，可以用来查询匹配次数   |
| 替换时的正则表达式 | {pattern}除了可以直接输入要替换的单词外，还能输入正则表达式 |
|                    | 比如下面这个精确匹配quack，而不匹配do_quack                 |
|                    | `:% s/\<quack\>/jiao/g`                                     |

| text object                      | 命令          |
| -------------------------------- | ------------- |
| 快速选中双引号中内容             | `vi"`         |
| 选中双引号内容删除并进入插入模式 | `ci"`         |
| 连双引号一起删除                 | `ca"`         |
| 举例：要删除python字典中的内容   | `ci}` 或`ci{` |

### 四、z.lua

https://github.com/skywind3000/z.lua/blob/master/README.cn.md

| z foo |  跳转到包含 foo 并且权重（Frecent）最高的路径 |
| ----- | ---------------------------------------------- |
|       |                                                |
|       |                                                |
|       |                                                |
|       |                                                |
|       |                                                |
|       |                                                |
|       |                                                |
|       |                                                |
|       |                                                |



### Vim 如何用宏完成强大的批量操作

##### macro

![1564404791605](assets/1564404791605.png)

宏可以看成是一系列命令的集合

我们可以使用宏录制一些操作，然后用于回放

宏可以非常方便地把一系列命令用在多行文本上（批量编辑）

##### 如何使用宏

宏的使用分为录制和回放

vim用q来录制/结束录制宏，

使用q{register}选择要保存的寄存器，把录制的命令保存其中

使用@{register} 回放寄存器中保存的一系列命令

因此可以使用q录制给一行加上双引号，之后使用q退出，在剩下的所有行回放



执行`qa`：此时已经开始录制到a寄存器（recording @a）

![1564405196061](assets/1564405196061.png)

再执行 `I"` `Esc` `A"` `Esc` `q` 完成增加双引号工作，结束录制

然后再按 V G 进入行选并选中剩下所有行

: 进入命令行模式 加上normal @a    （在normal模式下执行命令）

![1564405444810](assets/1564405444810.png)

这样就完成了。



另一种方法

V G 全选所有行，`:'<,'>normal I"`  `:'<,'>normal A"`  也可以完成需求

