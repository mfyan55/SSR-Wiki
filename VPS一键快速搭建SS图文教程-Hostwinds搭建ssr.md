## **什么是shadowsocks**

shadowsocks 可以指一种 SOCKS5 的加密传输协议，也可以指基于这种加密协议的各种数据传输包。

**shadowsocks 实现科学上网原理？**

shadowsocks 正常工作需要服务器端和客户端两端合作实现，首先，客户端（本机）通过 SS（shadowsocks）对正常的访问请求进行 SOCK5 加密，将加密后的访问请求传输给 SS 服务器端，服务器端接收到客户端的加密请求后，解密得到原始的访问请求，根据请求内容访问指定的网站（例如Google，YouTube，Facebook，instagram 等），得到网站的返回结果后，再利用 SOCKS5 加密并返回给客户端，客户端通过 SS 解密后得到正常的访问结果，于是就可以实现你直接访问该网站的“假象”。

**为什么选择 shadowsocks？**

不限终端（安卓，苹果，Windows，Mac 都可用），流量便宜（服务器 1TB 只要 30 元），方便（一键脚本，不需要专业知识）。

## 为什么要自己搭建 SS/SSR？

你也许会觉得买 SS 服务也很方便，但是你得要考虑以下几个问题。首先，买的 SS 服务，限制很多，终端可能只能同时在线 2 个，每个月就一点点流量可能价格却不便宜，有时候还被别人做手脚，流量跑的贼快；其次，别人收钱跑路怎么办？很多这种情况的；更重要的是，如第一个问题中描述的shadowsocks 原理，如果有心人做了一点手脚，是可以得到你的访问记录的；而自己搭建 SS/SSR 服务，一键脚本也就 10 来分钟就可以搞定。

美国 VPS [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) 是一家老牌 VPS 服务商，价格便宜、性能稳定、速度快、24小时客服、支持支付宝付款，关键是不会跑路。通过 Hostwinds 搭建 SSR 是不错的选择，今天就讲解下 Hostwinds 搭建 SSR 教程。

## 1、购买 Hostwinds VPS

首先确认不要使用任何代理，网络是什么 IP 就是什么 IP ，不然可能需要人工审核，导致 Hostwinds VPS 购买显示 "Pending" 状态， 不能即时创建服务激活。

1、通过[ Hostwinds 优惠链接进入](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224)Hostwinds 首页，选择 “VPS” 下的 "Unmanaged VPS" ，这里是最便宜的**(注意千万不要选择页面上 3.29 美元那个，那个是虚拟空间，不是 VPS !!!)**。

![img](https://user-images.githubusercontent.com/52620310/62405902-216e0d00-b5d6-11e9-8361-a3a75797b52f.jpg)

2、进入 VPS 选择页面后，根据自己的需要的配置选择套餐，一般我们选择最低配置就够用了，然后点击 “Order” 按钮进入信息填写页面，如下所示：

![img](https://user-images.githubusercontent.com/52620310/62405905-27fc8480-b5d6-11e9-85d3-70c4f202ef17.jpg)

3、进入信息填写页面后首先填写账号信息，一般是新用户我们填写左边的姓、名、邮箱、密码，然后点击 “Submit” 进入下一步，如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405907-2cc13880-b5d6-11e9-8dd3-bca5e119f97d.jpg)

4、页面跳转后填写用户信息，如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405909-321e8300-b5d6-11e9-8efc-d25563e38ea1.jpg)

5、然后选择购买时间、数据中心 、操作系统，红色部分需要自己选择，绿色一般我们默认，可以按月购买，但是建议第一次购买时间选择长一点，这样优惠要大很多，不然后面续费优惠力度就没有这么大了。 如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405910-36e33700-b5d6-11e9-916a-21611cae95ba.jpg)

6、默认是自动云备份的，如果不需要去掉勾选， 如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405913-3c408180-b5d6-11e9-908d-d475887eda70.jpg)

7、然后选择付款方式，一般我们选择支付宝进行付款 （只有国内 IP 访问的时候才有支付宝付款方式），如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405915-406c9f00-b5d6-11e9-90d8-7eed10538637.jpg)

8、最后确认价格（不同时期可能价格有些许不同，如果通过前面优惠链接点击购买会有优惠），勾选同意协议，然后点击“Complete Order”按钮进行下单， 如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405916-4498bc80-b5d6-11e9-8ecd-77d1f9587e94.jpg)

9、下单完成后订单结果如下图所示：

![img](https://user-images.githubusercontent.com/52620310/62405918-482c4380-b5d6-11e9-970d-4fce99d5d1e6.jpg)



## 2、SSH 连接 Hostwinds

首先你需要通过 SSH 连接 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1216) 的 Linux VPS，连接 Linux VPS 需要使用 SSH 工具，这里推荐使用 Xshell 可以复制粘贴命令，Xshell 本身是需要付款的，作为中国人当然是使用 XX 版了，这里提供下载包如下所示：

Xshell 下载地址：<https://pan.baidu.com/s/1v7RCM0IjZGn_q5aWS1WXWg>，提取码: q3jw

下载后解压安装即可。

#### 使用 Xshell 连接 Linux VPS

1、打开 Xshell，点击左上角“文件”-“新建”，打开连接弹出库。

[![11](https://user-images.githubusercontent.com/52620310/62409274-3b741380-b607-11e9-86f4-6841945da8f2.jpg)](https://user-images.githubusercontent.com/52620310/62409274-3b741380-b607-11e9-86f4-6841945da8f2.jpg)

2、在 Xshell 弹出框中输入 IP 和端口，端口一般是 22 默认，然后点击确认按钮，如下图所示：

[![12](https://user-images.githubusercontent.com/52620310/62409279-3f079a80-b607-11e9-829a-dc6db2d6ce8e.jpg)](https://user-images.githubusercontent.com/52620310/62409279-3f079a80-b607-11e9-829a-dc6db2d6ce8e.jpg)

3、然后输入用户名 root，勾选记住用户名。

[![13](https://user-images.githubusercontent.com/52620310/62409280-429b2180-b607-11e9-8438-48451de0dbaf.jpg)](https://user-images.githubusercontent.com/52620310/62409280-429b2180-b607-11e9-8438-48451de0dbaf.jpg)

4、然后输入密码，勾选记住密码，点击确定。

[![14](https://user-images.githubusercontent.com/52620310/62409282-462ea880-b607-11e9-9da0-68ddc4f05bc0.jpg)](https://user-images.githubusercontent.com/52620310/62409282-462ea880-b607-11e9-9da0-68ddc4f05bc0.jpg)

完成以上步骤后就可以看到连接成功的界面，如下图所示：

[![15](https://user-images.githubusercontent.com/52620310/62409283-49299900-b607-11e9-86be-f16913c9fcf3.jpg)](https://user-images.githubusercontent.com/52620310/62409283-49299900-b607-11e9-86be-f16913c9fcf3.jpg)

## 3、在 Hostwinds 上部署 SS 或 SSR

我们首先输入第一条命令后回车：

**SS代码：**

```
wget --no-check-certificate -O shadowsocks-all.sh 
https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
```

**SSR代码：**

```
wget --no-check-certificate 
https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh
```

[![16](https://user-images.githubusercontent.com/52620310/62409286-4e86e380-b607-11e9-9521-913b40159d1f.jpg)](https://user-images.githubusercontent.com/52620310/62409286-4e86e380-b607-11e9-9521-913b40159d1f.jpg)

等待如图所示之后，我们输入第2条命令，回车：

**SS代码：**

```
chmod +x shadowsocks-all.sh
```

**SSR代码：**

```
chmod +x shadowsocksR.sh
```

[![17](https://user-images.githubusercontent.com/52620310/62409289-52b30100-b607-11e9-8fdf-ad0403d9ff2d.jpg)](https://user-images.githubusercontent.com/52620310/62409289-52b30100-b607-11e9-8fdf-ad0403d9ff2d.jpg)

等待如图所示之后，我们输入第3条命令，回车：

**SS代码：**

```
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

**SSR代码：**

```
./shadowsocksR.sh 2>&1 | tee shadowsocksR.log
```

我们将代码输入完成后便会看到如下图所示，提示我们为 Shadowsocks 服务设置一个个人密码。

[![18](https://user-images.githubusercontent.com/52620310/62409291-5777b500-b607-11e9-98f5-2972c608ce69.jpg)](https://user-images.githubusercontent.com/52620310/62409291-5777b500-b607-11e9-98f5-2972c608ce69.jpg)

我们输入完密码后回车，接下来设置 Shadowsocks 服务端口，默认端口号 8989，或者我们输入 1–65535 间的数字都行。

[![19](https://user-images.githubusercontent.com/52620310/62409293-5b0b3c00-b607-11e9-8b42-63e61b6b6638.jpg)](https://user-images.githubusercontent.com/52620310/62409293-5b0b3c00-b607-11e9-8b42-63e61b6b6638.jpg)

我们输入端口号后继续回车，接下来设置 Shadowsocks 加密方式，默认 **aes-256-gcm**即可。

[![20](https://user-images.githubusercontent.com/52620310/62409294-5e062c80-b607-11e9-9e78-39e4c8269c35.png)](https://user-images.githubusercontent.com/52620310/62409294-5e062c80-b607-11e9-9e78-39e4c8269c35.png)

我们接下来按照上图所示按任意键开始部署 Shadowsocks，我们等待部署结束后就会看到我们所部署的 Shadowsocks 的配置信息。我们需要记下Shadowsocks的配置信息：***服务器IP**（Sever IP ）、**服务器端口号**（Serer Port）、**登录密码**（Password）和**加密方式**（Encryption Method）*，接下来就需要我们下载Shadowsocks客户端进行相关配置了！

[![21](https://user-images.githubusercontent.com/52620310/62409295-61011d00-b607-11e9-8fcb-75f6b07efee4.jpg)](https://user-images.githubusercontent.com/52620310/62409295-61011d00-b607-11e9-8fcb-75f6b07efee4.jpg)

## 4、Hostwinds 搭建 BBR 加速

虽然 SSR 搭建好了，但是速度还不是很快，要搭建 BBR 才快，下面我们就说说怎么搭建 BBR。

BBR 是 Google 的一款 SSR 加速产品，使用下面的命令就可以实现 BBR 加速，只有 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1216) 等少数 KVM VPS 才支持 BBR 加速，这也是我们推荐选择 Hostwinds 的原因。

**安装 BBR：**

```
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
```

**获取读写权限：**

```
chmod +x bbr.sh
```

**启动BBR安装：**

```
./bbr.sh
```

接着按任意键，开始安装，坐等一会。最后完成后需要重启，根据提示输入：y，重启服务器即可生效

[![22](https://user-images.githubusercontent.com/52620310/62409296-65c5d100-b607-11e9-8ab6-e7945452cab3.jpg)](https://user-images.githubusercontent.com/52620310/62409296-65c5d100-b607-11e9-8ab6-e7945452cab3.jpg)

如果错过了重启步骤，直接输入重启命令命令：

```
reboot
```

[![23](https://user-images.githubusercontent.com/52620310/62409299-6a8a8500-b607-11e9-91db-c5397402e708.jpg)](https://user-images.githubusercontent.com/52620310/62409299-6a8a8500-b607-11e9-91db-c5397402e708.jpg)

重新启动之后，输入 `lsmod | grep bbr` 如果看到 tcp_bbr 就说明 SSR 已经启动了。

```
lsmod | grep bbr
```



## 5、客户端搭建SS代理

各种客户端版本下载地址：[各版本shadowsocks客户端下载地址](https://github.com/xiaoming2028/kexueshangwang/releases)

以Windows为例：

![shadowsocks-pc-windows](https://user-images.githubusercontent.com/54033249/63205980-476bd500-c0df-11e9-8cb7-5508b5cd0801.png)

在状态栏右击shadowsocks，勾选**开机启动**和**启动系统代理**，在**系统代理模式**中选择**PAC模式**，**服务器**->**编辑服务器**，一键安装shadowsocks的脚本默认服务器端口是1024，加密方式是aes-256-cfb，密码是你设置的密码，ip是你自己的VPS ip，保存即可~

**PAC模式**是指国内可以访问的站点直接访问，不能直接访问的再走shadowsocks代理~

OK！一键脚本搭建shadowsocks完毕！科学上网吧，兄弟！



## 6、Hostwinds 搭建 SS 或 SSR 总结

以上就是美国 VPS Hostwinds 搭建 SSR 的教程，通过教可以轻松实现 Hostwinds 搭建 SSR，希望可以帮助需要使用 Hostwinds 搭建 SSR 的朋友。

[Hostwinds 最好美国VPS低至4.49美元/月](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1216)，支持支付宝付款，欢迎购买注册。