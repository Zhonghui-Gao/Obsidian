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
我们需要PPTX的就下载即可
![[Pasted image 20260331210830.png]]
```shell
npx skills add https://github.com/anthropics/skills --skill pptx
```

如果出现使用该命令git clone 失败的话 可以采用先可git clone 或者单独去GitHub 下载对应的包即可 然后再手动添加环境
成功的：
![[Pasted image 20260331211010.png]]

失败的：
