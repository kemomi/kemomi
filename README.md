![IMG_6121](https://user-images.githubusercontent.com/76780905/186084820-284cdf74-f0fa-4eb8-9d4f-2d43cf0f1854.GIF)

# 个人项目

最终效果：[欢迎进入月世界](https://ziav.cn/)

![QQ图片20220830105306](https://user-images.githubusercontent.com/76780905/187345608-6638f6f7-2d72-4169-b74f-a7e42d599a62.gif)
![QQ图片20220830105318 - 副本](https://user-images.githubusercontent.com/76780905/187345633-6bc5cc2b-688c-4379-81aa-8f920523294d.gif)
<video autoplay src="https://assets.huabyte.com/blog/image/Tab-1645529042263.webm"></video>

开源地址：[https://github.com/0xFloyd/Portfolio_2020](https://github.com/0xFloyd/Portfolio_2020)

## 项目环境

安装node8.0+, 没有安装node可以前往[官网](https://nodejs.org/zh-cn/)安装

安装一个编辑器，推荐[vscode](https://code.visualstudio.com/)

> 实不会的参考一下教程，也可以自行搜索
>
> node安装与配置：[https://www.bilibili.com/video/BV11V411o7Zh](https://www.bilibili.com/video/BV11V411o7Zh)
>
> vscode安装与配置：[https://www.bilibili.com/video/BV1P64y187Fh](https://www.bilibili.com/video/BV1P64y187Fh)

## 项目运行

```
// 安装依赖
npm install & cnpm install

// 本地运行
npm run dev

// 打包
npm run build
```

## 代码

+ 如果没有接触过`three.js`想对这个网站修改，可以看看官方文档，博客也有three相关文档。

+ 如果拿这个网站作为模板直接修改成自己的网站的话，关注以下`代码部分`，图片可以直接拖到PS中修改成自己的导出`png`透明格式替换即可。

```js
// texture.js

let billboardTextures = {};
// 第一块展板图片地址
billboardTextures.blogTexture = '"...src\jsm\blog.png"';
// 第二块展板图片地址
billboardTextures.musicTexture =
  '"...Screenshots\music.png"';
// 第三块展板图片地址
billboardTextures.fundTexture =
  '"...\src\jsm\fund.png"';

let boxTexture = {};
// 链接的图标地址
boxTexture.Github = '"...src\jsm\githubLogo.png"';
boxTexture.BiliBili = '"...src\jsm\BiliBili.png"';
boxTexture.QQ = '"...src\jsm\qq.png"';
boxTexture.mail = '"...src\jsm\envelope.png"';
boxTexture.reactIcon = '...src/jsm/react.png';
boxTexture.allSkills = '...src/jsm/allSkills.png';
boxTexture.lensFlareMain = '...src/jsm/lensflare0.png';
boxTexture.skrillex = '.../src/jsm/skrillex.png';
boxTexture.edmText = '...src/jsm/EDM.png';

// 砖块材质
let stoneTexture = '...src/jsm/stone.png';
// 展板木头材质
let woodTexture = '...src/jsm/woodTexture.jpg';

// 文字图片地址
let inputText = {};
inputText.terpSolutionsText = '...src/jsm/terp-solutions-text.png';
inputText.activities = '...src/jsm/activities_text.png';
inputText.bagholderBetsText = '...src/jsm/bagholderbets-text.png';
inputText.homeSweetHomeText = '...src/jsm/home-sweet-home-text.png';
inputText.staticPortfolio = '...src/jsm/static-portfolio.png';
inputText.pcControl = '...src/jsm/pc-control.png'
inputText.mobileControl = '...src/jsm/mobile-control.png'
inputText.link = '...src/jsm/link.png'

//SVG
let SVG = {};
SVG.reactLogo = '...src/jsm/react-svg.svg';

// 链接的跳转地址
let URL = {};
URL.blog =
  'https://ziav.cn';
URL.ryanfloyd = 'https://ziav.cn';
URL.fund = 'https://github.com/kemomi/kemomi';
URL.gitHub = 'https://github.com/kemomi';
URL.BiliBili = 'https://space.bilibili.com/379088274';
URL.email = 'https://fbee3157@gmail.com';
URL.music = 'https://music.163.com/#/user/home?id=564277776';
URL.devTo =
  'http://wpa.qq.com/msgrd?v=3&uin=1443563828&site=qq&menu=yes"><img border="0" src="http://wpa.qq.com/pa?p=2:1443563828:41';


## 部署github-pages

### 安装git

不会的可以查看这个教程：[https://www.bilibili.com/video/BV12E411k74T](https://www.bilibili.com/video/BV12E411k74T)

接下来我们就可以部署到免费的 Github Pages 上。
我们在 Github 上新建一个仓库，这里我取得仓库名为`kemomi.github.io`，注意建好自己的仓库都应该是(你的用户名.github.io)

![QQ图片20220830105255](https://user-images.githubusercontent.com/76780905/187345565-40306008-f036-4e22-ad99-84fafbe46289.gif)


找到`settings`下面的`pages`



注意查看自己创建的分支和这里是一样的，点击`Save`保存后，过一会点击链接就出现了。

> 一般部署完需要等待几分钟访问才会有，耐心等一会就行。




## 自动化脚本部署

可以把这个`shell`脚本放到项目目录中，新建`deploy.sh`,将仓库git地址修改成你自己的

```shell
#!/usr/bin/env sh

# 确保脚本抛出遇到的错误
set -e

# 生成静态文件
npm run build

# 如果是发布到自定义域名
# echo 'www.ziav.cn' > CNAME

git init
git add -A
git commit -m 'deploy'

# 如果你想要部署到 https://USERNAME.github.io
git push -f git@github.com:kemomi/kemomi.github.io.git main

# 如果发布到 https://USERNAME.github.io/<REPO>  REPO=github上的项目
# git push -f git@github.com:USERNAME/<REPO>.git master:gh-pages

```

然后在config.json中加入

```
"scripts": {
	C:\WEB_CODE\3d-website.
    "deploy": "bash deploy.sh"
  },
```

就可以运行`npm run deploy`实现自动化部署啦。

##
![QQ图片20220830105335 - 副本](https://user-images.githubusercontent.com/76780905/187353610-029d2df9-2a7e-4bd8-8aea-6fec4e74203b.gif)![QQ图片20220830105338](https://user-images.githubusercontent.com/76780905/187353628-9a0a9386-bf07-4ead-8872-cc929cb37ae2.gif)![QQ图片20220830105335 - 副本](https://user-images.githubusercontent.com/76780905/187353610-029d2df9-2a7e-4bd8-8aea-6fec4e74203b.gif)![QQ图片20220830105338](https://user-images.githubusercontent.com/76780905/187353628-9a0a9386-bf07-4ead-8872-cc929cb37ae2.gif)![QQ图片20220830105335 - 副本](https://user-images.githubusercontent.com/76780905/187353610-029d2df9-2a7e-4bd8-8aea-6fec4e74203b.gif)![QQ图片20220830105338](https://user-images.githubusercontent.com/76780905/187353628-9a0a9386-bf07-4ead-8872-cc929cb37ae2.gif)![QQ图片20220830105335 - 副本](https://user-images.githubusercontent.com/76780905/187353610-029d2df9-2a7e-4bd8-8aea-6fec4e74203b.gif)






