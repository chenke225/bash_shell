windows下免除每次连接github要输入密码之烦恼
打开~/.bash_profile，将以下内容粘贴到该文件，保存。当你初次运行git_bash时，将提示输入密码（SSH建立密钥时的密码），此时ssh-agent进程将持续运行，知道关闭git_bash。如此，连接github时将无需输入密码。

VScode中利用git通过ssh连接github
1 初始化
   git config --global user.name chenke225 #设定连接用户名
   git config --global user.email chenke225@gmail.com #建立github的用户邮箱

2 建立git仓库

   mkdir /d/gittest   # 建立本地目录
   cd /d/gittest      # 进入本地目录
   git init           # 建立git本地仓库，可拷贝一些文件到此目录。

3 产生ssh密钥 将公钥复制到github

   vscode终端输入运行
   ssh-keygen -t rsa -C "chenke225@gmail.com"  #产生一对ssh密钥
   此后，在需要输入密码时，可以直接回车，就会忽略连接启动时的密码。 若之前已产生过密钥，选择覆盖。
   这样在~/目录下产生.ssh目录，至少有两个文件 id_rsa, id_rsa.pub，即私钥和公钥。
   
   clip < ~/.ssh/id_rsa.pub                #复制公钥到剪贴板。 ~是用户的目录，windows下我的是 c:\users\chk

   将公钥复制到github。 登录你的github，右上角点开下拉菜单，选settings，settings界面选择 SSH and GPG keys里面的SSH。
   删除可能已有的公钥，粘贴你的新建公钥，点击new ssh key按键。 由此将公钥保存到github。
   使用命令 ssh -T git@github.com    测试，输入password时直接回车。 将显示成功信息
   Hi, chenke225! You've successfully authenticated, but Github does not provide shell access.

4  设置vscode工作目录与git的连接
	1）首先github中必须新建一个项目，例如bash_shell，这个就不赘述了.
	2）在vscode的终端中，输入 
	git remote add origin git@github.com: chenke225/bash_shell 
	如果有 fatal: remote origin already exists，则输入
	git remove rm origin
	重新运行 git remote add origin git@github.com: chenke225/bash_shell
	3）输入推送工作区 
	git push -u origin master
	如果推送成功就会在网站中看到你的项目。有时不成功，可以强行push
	git push -u origin master -f
	这样把本地目录中的文件上传到bash_shell目录下，也可以叫bash_shell仓库 repositories
	4）之后只需要在vscode中的菜单中操作上传即可，大功告成。


	在vscode中进行git版本控制
	选择你的项目目录（仓库目录）
	点击左侧git图标（一个连接样子的图标）。
	打开要修改的文件，进行修改，保存。
	点击该文件上方的+（stage changes）。
	添加注释message，必须写不能空。 Ctrl+Enter。 由此保存了修改。
	下拉菜单中选 push。如此将本地修改的文件上传到github。
	要从云端github下拉文件，从下拉菜单选pull。


