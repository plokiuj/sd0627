# Heroku-vless



[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https%3A%2F%2Fgithub.com%2Fplokiuj%2Fsd0627)




### 路径

`WebSocket` 路径(配置文件中的 `path` )为 `/` 。你也可以自行修改

### 端口

`端口` 为 `443` 。

### UUID

`UUID` 默认为 `10974d1a-cbd6-4b6f-db1d-38d78b3fb109` 你也可以在部署时自由修改（建议修改）。

## 流量中转

使用cloudflare的workers来`中转流量`，配置为： 

```
addEventListener(
      "fetch",event => {
         let url=new URL(event.request.url);
         url.hostname="HEROKU地址，例如 rptec.herokuapp.com";
         let request=new Request(url,event.request);
         event. respondWith(
           fetch(request)
         )
      }
    ) 
```


VLESS演示链接
自行修改其中 自选IP和你的heroku地址。不再提供演示，发现我提供了，就全用我的演示地址了，一天就能几百万连接，给账号都干趴下，自建很简单。
```
vless://10974d1a-cbd6-4b6f-db1d-38d78b3fb109@你的自选ip:443?encryption=none&flow=xtls-rprx-direct&security=tls&sni=你的HEROKU地址或CF反代地址&type=ws&host=你的HEROKU地址或CF反代地址#heroku

```
详细教程
https://92km.net/archives/VLESS-Heroku-cloudflareworkers.html

搭建中有任何问题，也可以联系我 https://t.me/herokuvless

## 云服务器自行搭建

手动搭建可参考我代码中 configure.sh内容，修改uuid等信息就可以手动部署。

建议新手使用x-ui一键安装，附带web面板。使用起来简单。

https://github.com/vaxilu/x-ui

## 测速
heroku服务器选美国区的话一般在亚马逊弗吉尼亚阿什本节点，套cf后，速度取决于你自选ip的速度。

自选IP后youtube非高峰期一般能跑30000-50000kbps。可以流畅播放4K视频。
![speedtest](https://img.21t.co/2022/04/19/8a697d.png)
原版、套CF、自选IP速度对比，自选IP明显要高出一大截。我这边在国内用手机测速speedtest一般可以跑150M以上。

## 自选IP教程
最近经常有人问如何自选ip，以前博客发过，后来因为觉得没什么作用，太简单就删了。现在重新贴出来吧，你下载下面工具自己执行即可。如果不想自己选的话，也可以使用我提供的ip.2024.ml

https://github.com/badafans/better-cloudflare-ip

![自选IP配置](https://so.21t.co/2021/06/15/ed87c8.png)

自选ip后，将图中Address中原地址修改为你自选ip（使用域名也可）。

## 临时替代品 2046 
或者你可以使用hax提供的vmess服务，国内速度不错
注册及使用教程
https://www.92km.net/archives/freevmess.html

#### 2046邀请码 

你可以找老用户索取邀请码
也可以访问 https://21t.co/admin 或https://t.me/herokuvless  获取


### 详细文字教程（面向0基础新手）感谢@我的未来不是梦 编写。
http://yun.21t.co/aliyun/电子资料/Heroku搭建教程.docx
