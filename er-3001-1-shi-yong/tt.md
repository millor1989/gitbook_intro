Learn

Git

SVN和CVS都是集中式的版本控制系统、Git是分布式的版本控制系统

两个分支合并rebase

  


git指令教程：

\#\#将当前目录变成git可以管理的仓库 git

init \#\#添加文件到stage区［暂存区］ git

add

&lt;

file

&gt;

 \#\#提交stage区的文件到分支［本地库］ git

commit

-m

"comment" \#\#查看［工作区］文件差异（git

add

之前可以用） git

diff

&lt;

file

&gt;

 \#\#查看工作区文件和版本库最新版本的差异 git

diff

HEAD

--

&lt;

file

&gt;

 \#\#查看两个分支（也可以和远程分支比较）的差异\(加^后，以^后的分支为基准\) git

diff

develop

^origin/develop \#\#查看修改记录 git

log \#\#（每条记录显示一行） \#\#样式：［commit

id］＋［comment］ git

log

--pretty=oneline \#\#结果：b5cde077396d8ef8da3a5b41e5166d1a478e408d

\(HEAD

-

&gt;

master\)

change

again git

reflog \#\#样式：［head版本／ID（commit

id的前7位）］ \#\#\#\#b5cde07

\(HEAD

-

&gt;

master\)

HEAD@{0}:

commit:

change

again \#\#\#\#cd18a04

HEAD@{1}:

commit:

change \#\#\#\#554174c

\(origin/master\)

HEAD@{2}:

commit:

github

push

test \#\#\#\#bb2ab17

HEAD@{3}:

commit:

rm

test.txt \#\#\#\#8895c88

HEAD@{4}:

commit:

add

test

file \#\#\#\#a835f50

HEAD@{5}:

reset:

moving

to

a835f50 \#\#\#\#f3a94a9

HEAD@{6}:

reset:

moving

to

f3a94a98a624e1cd1a410e975bc098c0d9ce3b29 \#\# -p展示每次提交的内容差异，-2仅显示最近的两次提交 git

log

-p

-2

 \#\#回退文件到当前版本\(把暂存区的修改回退到工作区\) git

reset

--hard

HEAD \#\#回退到上一个版本 git

reset

--hard

HEAD^ \#\#回退到指定的head版本 git

reset

--hard

&lt;

head版本

&gt;

 \#\#撤销工作区的文件修改（如果修改后没有add到暂存区，则恢复到版本库的当前状态；如果修改后add到暂存区，然后又做了修改，则恢复到添加到暂存区的版本） \#\#（在执行“git

commit”之前，可以用“git

checkout”恢复删除的文件） git

checkout

--

&lt;

file

&gt;

 \#\#删除文件 git

rm

&lt;

file

&gt;

 \#\#生成SSH-KEY ssh-keygen

-t

rsa

-C

"

&lt;

emailAddress

&gt;

" \#\# 添加ssh-key\(私钥\) ssh-add ~/.ssh/id\_gitlab \#\#如果报错：Could not open a connection to your authentication agent. \#\#使用命令ssh-agent bash，切换ssh-agent到bash后，再次执行 \#\#关联远程库 git

remote

add

origin

&lt;

git-url

&gt;

 \#首次把本地所有文件push到远程库 git

push

-u

origin

master \#之后push可以用 git

push

origin

master \#\#克隆远程库到本地目录 git

clone

&lt;

版本库网址［git、http等］

&gt;

&lt;

本地目录［可选参数］

&gt;

 \#\#查看分支 git

branch \#\#\#结果的当前分支前会有一个“\*” \#\#\#

dev \#\#\#\*

master \#\#创建dev分支 git

branch

dev \#\#切换到dev分支 git

checkout

dev \#\#创建并切换到dev分支（作用同［git

branch

dev］和［git

checkout

dev］两条指令） git

checkout

-b

dev \#\#将两个或两个以上的开发历史进行合并 git

merge

&lt;

name

&gt;

 \#\#\#exp.

git

merge

FETCH\_HEAD \#\#合并dev分支到当前分支 git

merge

dev \#\#删除分支 git

branch

-d

&lt;

branch-name

&gt;

 \#\#强行删除\[\[没有合并过的\]\]分支 \#\#分支的强行删除（git默认不能删除未合并的分支） git

branch

-D

&lt;

branch-name

&gt;

 \#\#通常合并分支时，Git会采用fast

forward模式，当删除分支后，会丢掉分支的信息 \#\#如果使用‘--no-ff’禁用fast

forward模式，Git就会在merge时产生一个新的commit，这样从分支历史上就可以看出分支信息 git

merge

--no-ff -m

"comment"

&lt;

branch-name

&gt;

 \#\#查看分支合并图 git

log

--graph \#\#推送分支 git

push

origin

&lt;

branch-name

&gt;

 \#\#强制推送到远程仓库（如果本地版本小于远程版本，不带--force将不能提交） git

push

origin

&lt;

branch-name

&gt;

--force \#\#创建远程分支 git

push

origin

&lt;

branch-name

&gt;

:

&lt;

remote-branch\_name

&gt;

 \#\#本地分支和远程分支关联（合并） git

pull

origin

&lt;

branch-name

&gt;

 \#\#获取远程分支、但是不自动合并 git

fetch

origin

&lt;

branch-name

&gt;

 \#\#删除远程分支.1 git

push

origin

--delete

&lt;

remote-branch-name

&gt;

 \#\#删除远程分支.2：将空分支推送到远程的分支，也可以将远程分支删除 git

push

origin

:

&lt;

remote-branch-name

&gt;

 \#\#git的工作区是各个分支公用的，如果新建bug分支时，不想正在进行的工作被提交，可以用“git

stash”命令，将当前工作场隐藏保护起来，这样在其它分支进行commit操作的时候就不会将之前的修改提交。 \#\#隐藏工作场 git

stash \#\#如果是没有被git管理的文件、新建的文件\目录（Untracked

files） \#\#用以下指令可以将未add的文件stash git stash --include-untracked git stash save -u \#\#查看隐藏的工作场 git

stash

list \#\#恢复隐藏的工作场（并清空stash隐藏内容） git

stash

pop \#\#恢复隐藏工作场（不清空stash隐藏内容，要用“git

stash

drop”清空） git

stash

apply \#\# 查看当前配置的远程仓库 git

remote \#\#\#\# 执行结果：origin \#\# 查看远程仓库和对应的地址 git

remote

-v \#\#\#\# 执行结果： \#\#\#\# origin ssh://git@10.33.xx.xxx:10022/dubbo-data/wf\_data.git \(fetch\) \#\#\#\# origin ssh://git@10.33.xx.xxx:10022/dubbo-data/wf\_data.git \(push\) \#\# 建立本地仓库和远程仓库的关联关系 \#\# 格式：git remote add \[shortname\] \[url\] git

remote

add

origin

git@github.com:cestlavia/springboot.git \#\# 删除指定的远程仓库 git remote rm origin \#\# 重命名远程仓库 git remote rename 

&lt;

former-name

&gt;

&lt;

new-name

&gt;

  


  


多人协作模式

\#\#1.首先用“git

push

origin

&lt;

branch-name

&gt;

”推送自己的修改 \#\#2.推送失败，是因为远程分支版本比本地的要新，需要先用“git

pull”尝试合并 \#\#3.如果合并有冲突则解决冲突，并在本地提交 \#\#4.冲突解决后再次推送 \#\#如果“git

pull”提示“no

tracking

information”，说明本地分支和远程分支的连接关系没有创建； \#\#创建本地分支和远程分支的连接关系 git

branch

--set-upstream-to

&lt;

branch-name

&gt;

origin/

&lt;

branch-name

&gt;

 \#\#在本地创建和远程分支关联的分支 git

checkout

-b

&lt;

branch-name

&gt;

origin/

&lt;

branch-name

&gt;

  


git标签

\#\#git标签tag，是一个与commit

id关联的易于记忆的名字 \#\#给分支打标签（默认打在最新的commit版本上） git

tag

&lt;

tag-name

&gt;

 \#\#给指定的commit版本打标签 git

tag

&lt;

tag-name

&gt;

&lt;

commit版本

&gt;

 \#\#查看标签信息 git

show

&lt;

tag-name

&gt;

 \#\#指定标签信息 git

tag

-a

&lt;

tag-name

&gt;

-m

"

&lt;

comment

info

&gt;

" \#\#查看所有的标签 git

tag \#\#标签删除 git

tag

-d

&lt;

tag-name

&gt;

 \#\#推送标签到远程（标签默认存储再本地，不会自动推送到远程） git

push

origin

&lt;

tag-name

&gt;

 \#\#推送所有的标签 git

push

origin

--tags \#\#如果标签已经推送到远程，要删除标签就麻烦些 \#\#1.先从本地删除“git

tag

-d

&lt;

tag-name

&gt;

” \#\#2.从远程删除“git

push

origin

:refs/tags/

&lt;

tag-name

&gt;

”

忽略文件：编写.gitignore文件

给git命令配置别名

git

config

--global

alias.

&lt;

alias-name

&gt;

&lt;

git-command-name

&gt;

\*\*git将本地已经存在的项目推送到新建的远程仓储

\*\*

1.在项目的根目录执行

git

init

命令，初始化git项目

\*\*

2.执行git

add和git

commit命令，将本地项目提交到本地仓库

\*\*

3.执行git

remote

add

origin

git@github.com:cestlavia/springboot.git命令，将本地仓库和远程仓库关联

\*\*

4.执行git

push

-u

origin

master命令，将本地项目推送到远程仓库

GIT

FLOW

