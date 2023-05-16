# 工具合集 

## [vim](https://missing-semester-cn.github.io/2020/editors/)
1. 进入退出 Vim 编辑器
   - `vim 文件名`：进入vim
   - `ESC :q!` ：放弃所有改动并退出
   - `ESC :wq` ：保存改动并退出
2. 模式切换：
   - `ESC` ：正常模式
   - `i` ：插入模式
   - `v` ：视图模式（光标选取）
   - `V`：行视图模式（`I`多行插入）
   - `CTRL-V`：方块视图
   - `R`：替换模式
3. 重复操作：指令格式：`operator`+`number`+`motion`
   - `operator` ：操作符，比如 `d` 代表删除，`c` 代表修改
   - `number`：可以附加的数字，代表动作重复的次数
   - `motion`：在所操作的文本上的移动步长，例如 `w` 代表单词(word)，`$`代表行末等等
4. 光标移动：
    - `kjhl`：上下左右
    - `b`：到前一个单词头部
    - `w`：到下一个单词头部
    - `ge`：到前一个单词尾部
    - `e`：到下一个单词尾部
    - `0`：到行首
    - `gg`：到文件第一行
    - `$`：到行末
    - `%`：若当前位置是括号，则跳转至配对的括上
    - `gd`：跳转到变量定义处
    - `:$`或`G`：到文件最后一行
    - `CTRL-G`：显示当前光标所在位置和文件状态信息
    - `行号`+`G`：将光标移动至该行号代表的行
    - `行号`+`$`：将光标移动至该行号末尾
5. 插入：
   - `i`：在光标前插入文本
   - `I`：在行首插入文本
   - `a`：在光标后添加文本
   - `A`：在行末添加文本
   - `o`：在光标所在行下方插入新行
   - `O`：在光标所在行上方插入新行
6. 删除：
    - `x`：删除光标所在位置的字符
    - `d`：删除视图模式下光标选中的部分
    - `d$`：删除光标当前位置到当前行末的部分
    - `dd`：删除整行
7. 撤销：
   - `u`：撤销上一个操作
   - `U`：撤销在一行中的改动
   - `CTRL-R`：回退撤销操作
8.  修改： 
    - `y`：复制视图模式下光标选中的部分
    - `yy`：复制光标所在行
    - `p`：置入已删除或复制的部分
    - `r`：覆盖原位置上的单个字符
    - `ce`：替换光标当前位置到单词末尾的内容
    - `c$`：替换光标当前位置到行末的内容
    - `~`：修改大小写
9.  查找：
    - `/`+`字符串`：在当前文档中正向查找该字符串
    - `?`+`字符串`：在当前文档中反向查找该字符串
    - `n`：找到下一个匹配
    - `N`：反向找到下一个匹配
    - `#`：正向搜索当前单词
    - `*`：反向搜索当前单词
    - `CTRL-O`：跳转回较旧的位置
    - `CTRL-I`：跳转到较新的位置
10.  替换：指令格式：`:`+`range`+`s/old/new`+`/flag`
     - `:21s/old/new`：将21行第一个 old 替换为为 new
     - `:21s/old/new/g`：将21行所有的 old 替换为 new
     - `:5,21s/old/new/g` 将5到21行所有的 old 替换为 new
     - `:.,21s/old/new/g` 将当前行到21行所有的 old 替换为 new
     - `:.+4,.+8s/old/new/g` 将当前行+4到+8行所有的 old 替换为 new
     - `:ls/old/new/g`：将第一行所有的 old 替换 new
     - `:$s/old/new/g`：将最后一行所有的 old 替换为 new
     - `:%s/old/new/g`：将文件内所有的字符串 old 替换为新的字符串 new
     - `:%s/old/new/gc`：进行全文替换时询问用户确认每个替换
     - `:%s/old/new/gi`：进行全文替换时忽略大小写
     - `:%s/old/new/gI`：进行全文替换时敏感大小写
11.  外部指令：
     - `:!command` 用于执行一个外部命令 command。
       - `:!dir`或`:!ls`：用于显示当前目录的内容
       - `:!del FILENAME`或`:!rm FILENAME`：用于删除名为 FILENAME 的文件
       - `:w FILENAME`：可将当前 VIM 中正在编辑的文件保存到名为 FILENAME 的文件中
     - 视图模式下`:w FILENAME`：可将当前编辑文件中可视模式下选中的内容保存到文件 FILENAME 中
     - `:r FILENAME`：可提取磁盘文件 FILENAME 并将其插入到当前文件的光标位置后面
     - `:r !dir`：可以读取 dir 命令的输出并将其放置到当前文件的光标位置后面
12. 设置
    - `:set ic`或`:set ignorecase`：查找时忽略字母大小写
    - `:set is`或`:set incsearch`：查找短语时显示部分匹配
    - `:set hls`或`:set hlsearch`：高亮显示所有的匹配短语
    - `:set noic`：在选项前加上 no 可以关闭选项
13. 窗口
    - `sp`：上下分割窗口
    - `vsp`：左右分割窗口
    - `CTRL-W`+`[hjkl]`：窗口切换

## [cmd](https://github.com/jlevy/the-art-of-command-line/blob/master/README-zh.md)
1. `pwd`：获取当前工作路径
2. `chmod 777 file.txt`：修改文件权限，三位数分别对应当前用户、用户组、所有用户。7代表二进制111，分别代表rwx读写执行权限
3. `echo hello > hello.txt`：将echo的输出重定向到txt文件中
4. `ls | grep hello log.txt`：在ls结果中找出含"hello"的项，`|`表示将ls程序与grep程序的输入输出连接起来，grep更适合单纯的查找或匹配文本
5. `awk '{print $1}' log.txt`：打印log.txt中每行第一个参数，awk更适合对格式化文本进行较复杂格式处理
6. `sed -n "20 p" log.txt`：打印log.txt第20行，sed更适合编辑匹配到的文本
7. `bash ./test.sh`：执行test.sh脚本
8. `sort -g log.txt`：按照数字顺序排序
9. `wc log.txt log2.txt`：word counts结果为三个数字，分别是行数、单词数、字节数
10. `sudo echo 3 > /sys/class/backlight/thinkpad_screen/brightness`权限不足，应改为`echo 3 | sudo tee /sys/class/backlight/thinkpad_screen/brightness`：因为echo 并不知道 | 的存在，它们只知道从自己的输入输出流中进行读写。因此shell (权限为您的当前用户) 在设置 sudo echo 前尝试打开 brightness 文件并写入，但是系统拒绝了 shell 的操作因为此时 shell 不是sudo根用户
11. 程序进程管理
    - `CTRL-C`：发送SIGINT信号，终止程序
    - `CTRL-Z`：发送SIGQUIT信号，终止程序
    - `kill -TERM %2`：发送SIGTERM信号，退出2号进程
    - `CTRL-Z`：发送SIGTSTP信号，暂停程序
    - `fg`：在前台恢复暂停的程序
    - `bg`：在后台恢复暂停的程序
    - `jobs`：查看当前终端中尚未完成的任务pid
    - `pgrep`：找出pid
    - `%<pid>`：引用pid


## [TODO:终端多路复用器tmux](http://linuxcommand.org/lc3_adv_termmux.php)

## [shell脚本](https://missing-semester-cn.github.io/2020/shell-tools/)
1. `foo=bar`而非`foo = bar`：变量赋值，空格会导致语义分割
2. `$foo`：访问变量的值
3. `'`：定义的字符串为原义字符串，其中的变量不会被转义，`echo "$foo"`会打印 bar
4. `"`：定义的字符串会将变量值进行替换，`echo '$foo'`会打印 $foo
5. 参数
   - `$0`：脚本名
   - `$1`到`$9`：脚本的参数，`$1`是第一个参数，依此类推
   - `$@`：所有参数
   - `$#`：参数个数
   - `$?`：前一个命令的返回值
   - `$$`：当前脚本的进程识别码
   - `!!`：完整的上一条命令，包括参数。常见应用：当你因为权限不足执行命令失败时，可以使用 sudo !!再尝试一次。
   - `$_`：上一条命令的最后一个参数。如果你正在使用的是交互式 shell，你可以通过按下 Esc 之后键入 . 来获取这个值。


## git
1. 基础
   - `git init`：仓库本地初始化
   - `git status`：仓库状态查看
   - `git add *.txt`：添加所有txt文件
   - `git commit -m "add test.txt" -s`：提交注释说明，并签名
   - `git commit --amend`：修改说明信息
   - `git reset HEAD <file>`：撤回已经add的file文件
   - `git checkout -- <file>`：将已修改未add的file文件回滚到未修改状态
   - `git log --graph --decorate`：查看git记录，显示分支图和名称
   - `git diff test.txt`：查看编辑区与已add部分的区别
2. 分支
   - `git checkout [commit id]`：切换commit版本
   - `git checkout -b debug`：创建debug新分支，并切换
   - `git merge debug`：在main分支上，将debug分支合并进来
   - `git rebase -onto main next debug`：将next分支上的debug分支变基到main分支上
3. 远程仓库
   - `git remote`：显示远程仓库信息
   - `git remote add <本地仓库名> <远程仓库url>`：基于本地仓库建立远程仓库
   - `git push <远程主机名> <本地分支名>：<远程分支名>`
   - `git branch --set-upstream-to=<远程仓库名>/<远程分支名>`：将本地仓库与远程仓库构建关联
   - `git fetch`：下拉远程仓库
   - `git pull`：下拉远程仓库，并合并到本地
   - `git clone`：从远程仓库下载
4. 高阶
   - `git blame <file>`：查看file文件每一行的贡献人
   - `git stash push/pop/list`：将当前临时修改压入git临时存储栈
   - .gitignore
5. [Trouble shooting](https://ohshitgit.com/zh)
   - 回退到已删除的commit
     - `git reflog`
     - `git reset HEAD@{index}`
   - 在刚提交的本地分支commit上添加小改动
     - 继续改动你的文件
     - `git add .`
     - `git commit --amend --no-edit`
   - 修改刚刚提交的commit信息：`git commit --amend`
   - 错把本应在新分支上提交的东西提交到了master
     - `git branch new_branch_name`基于当前master新建分支
     - `git reset HEAD~ --hard`在master上删除最近的那次commit
     - `git checkout new_branch_name`此时只有新分支上有最新的commit
   - commit提交错分支了
     - `git checkout name-of-the-correct-branch`抓取 master 分支上最新的那个 commit
     - `git cherry-pick master`然后删掉 master 上的那个 commit
     - `git checkout master`
     - `git reset HEAD~ --hard`


## [makefile](https://seisman.github.io/how-to-write-makefile/overview.html) 
```makefile
include foo.make *.mk                           # 包含其他makefile，执行make时会在当前目录下查找，也可通过-I参数指定
objects = main.o kbd.o command.o display.o \    # "\"表示换行
    insert.o search.o files.o utils.o           # 定义变量，简化重复项

edit : $(objects)          # 第一项edit为make的目标生成文件，此处引用objects变量作为依赖项
    cc -o edit $(objects)  # 编译指令

main.o : defs.h            # 中间文件:编译依赖项
kbd.o : defs.h command.h
command.o : defs.h command.h
display.o : defs.h buffer.h
insert.o : defs.h buffer.h
search.o : defs.h buffer.h
files.o : defs.h buffer.h command.h
utils.o : defs.h

.PHONY : clean             # .PHONY 表示 clean 是个伪目标文件
clean :                    # clean指令默认放在make文件末尾
   -rm edit $(objects)     # 小减号的意思就是，也许某些文件出现问题，但不要管，继续做后面的事
```