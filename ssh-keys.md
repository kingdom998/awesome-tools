1. 生成钥匙对：ssh-keygen -t rsa -C "995350347@qq.com"
2. cat ~/.ssh/id_rsa.pub 复制对应的文本到 gitlab/github ssh keys
3. 添加到[ssh-agent](http://man.linuxde.net/ssh-agent)的高速缓存中：ssh-add ~/.ssh/id_rsa
4. 测试：ssh -T git@github.com（输入yes回车，添加认证成功）

