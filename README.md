# Detail Step


#git 同时配置gitlab github
###生成并添加ssh key
ssh-keygen -t rsa -C "your gitlab/github email" -f ~/.ssh/rsa_gitlab(自定义密钥名称)
###查看.shh目录结构
cd ~/.ssh 
ls
###生成config文件
touch config
添加如下内容：
    # gitlab
    Host gitlab.com
        HostName gitlab.com
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/gitlab_jslite

    # github
    Host github.com
        HostName github.com
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/id_rsa
###添加密钥列表
ssh-add ~/.ssh/id_rsa
如果出现提示：could not open a connection  to your authentication agent,则执行
ssh-agent bash
再执行ssh-add 
###测试连接
ssh -T git@gitlab.com

:blush:
