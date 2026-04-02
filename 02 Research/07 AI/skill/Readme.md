## 一、环境配置
PPT skills 需要v18或更高版本 作者的版本是
`v20.15.0` `10.7.0` `10.7.0`
### Node.js
```shell
node --version
npm --verison
npx -version
```
### Claude Code
安装参考链接：https://www.runoob.com/claude-code/claude-code-install.html
```shell
npm install -g @anthropic-ai/claude-code
claude --version
```

在安装好Claude Code 之后不要运行 因为Claude Code会锁区域，只要通过第二条命令是否安装成功即可。效果如下

```shell
~ ❯ claude --version
2.1.88 (Claude Code)
```

### PackeAPI配置

安装参考链接：https://docs.packyapi.com/docs/ccswitch/#claude-code%E9%85%8D%E7%BD%AE
这个很重要 务必看 
⭐⭐⭐该文档我们主要查看 CC-Switch 使用
https://docs.packyapi.com/docs/ccswitch/
CC-Switch类似提供一体化管理平台
https://github.com/farion1231/cc-switch/releases/tag/v3.12.3

![[Pasted image 20260331210443.png]]
打开这个 在登陆到Claude Code 即可解锁区域 这时候在登陆Claude Code就可以对话了 然后选择模型和调用API即可 具体看链接说明文档

### skills
官网：https://skills.sh/
这里有很多skill的rank榜

skills 是一个命令行工具，用来统一管理各种「AI 编程代理（code agents）」的可复用技能（Agent Skills），比如 Claude Code、Cursor、OpenCode、GitHub Copilot、QWen Code 等在内的35种AI编程代理。

我们需要PPTX的就下载即可
![[Pasted image 20260331210830.png]]
```shell
npx skills add https://github.com/anthropics/skills --skill pptx
```

如果出现使用该命令git clone 失败的话 可以采用先可git clone 或者单独去GitHub 下载对应的包即可 然后再手动添加环境
成功的：
![[Pasted image 20260331211010.png]]

失败的：
```shell
afeter 60s 添加失败Failde to clone respositor之类的话术
◓  Cloning repository..│
■  Failed to clone repository
│
│  Clone timed out after 60s. This often happens with private repos that require authentication.
│
│    Ensure you have access and your SSH keys or credentials are configured:
│
│    - For SSH: ssh-add -l (to check loaded keys)
│
│    - For HTTPS: gh auth status (if using GitHub CLI)
│
│  Tip: use the --yes (-y) and --global (-g) flags to install without prompts.
│
└  Installation failed
```

手动安装 全局变量 也可以设置当前工程(目录下)使用局部变量
```shell
npx skills add D:\PPT\skills\skills --skill pptx --yes --global
```

参考：https://blog.csdn.net/qq_41914181/article/details/159528959

成功加载：

![[Pasted image 20260402140919.png]]


## 使用方法
## PackeyAPI
https://docs.packyapi.com/ 其实就是大模型的“供应商"

使用文档：
https://docs.packyapi.com/docs/register/ 

切换模型：
https://juejin.cn/post/7611769471619645478

填入注册好的API即可 选择模型
![[Pasted image 20260402140827.png]]
打开Cluade code 成功


![[Pasted image 20260402141654.png]]


## PPT制作 

打开Cluade code 这是我的提示词

![[Pasted image 20260402140937.png]]
目录下创建了pic/ .pdf .md
pic目录，里面存放一些图片的素材，

![[Pasted image 20260402141144.png]]

编写规则xxx.md 
这部分按照对PPT的预期想法进行编写


结果：
![[Pasted image 20260402141440.png]]

