## **什么是shadowsocks**

shadowsocks 可以指一种 SOCKS5 的加密传输协议，也可以指基于这种加密协议的各种数据传输包。

**shadowsocks 实现科学上网原理？**

shadowsocks 正常工作需要服务器端和客户端两端合作实现，首先，客户端（本机）通过 SS（shadowsocks）对正常的访问请求进行 SOCK5 加密，将加密后的访问请求传输给 SS 服务器端，服务器端接收到客户端的加密请求后，解密得到原始的访问请求，根据请求内容访问指定的网站（例如Google，YouTube，Facebook，instagram 等），得到网站的返回结果后，再利用 SOCKS5 加密并返回给客户端，客户端通过 SS 解密后得到正常的访问结果，于是就可以实现你直接访问该网站的“假象”。

**为什么选择 shadowsocks？**

不限终端（安卓，苹果，Windows，Mac 都可用），流量便宜（服务器 1TB 只要 30 元），方便（一键脚本，不需要专业知识）。

### 为什么要自己搭建 SS/SSR？

你也许会觉得买 SS 服务也很方便，但是你得要考虑以下几个问题。首先，买的 SS 服务，限制很多，终端可能只能同时在线 2 个，每个月就一点点流量可能价格却不便宜，有时候还被别人做手脚，流量跑的贼快；其次，别人收钱跑路怎么办？很多这种情况的；更重要的是，如第一个问题中描述的shadowsocks 原理，如果有心人做了一点手脚，是可以得到你的访问记录的；而自己搭建 SS/SSR 服务，一键脚本也就 10 来分钟就可以搞定。



[Vultr VPS](https://www.vultr.com/?ref=8169051-4F) 主机是一家 2014 年成立的美国 VPS 主机服务商，它的母公司 Choopa 是已经有将近 20 年全球主机提供经验的老牌主机服务商。Vultr 至今才成立不到 4 年的时间，但是发展速度很快，目前拥有日本、美国、新加坡、英国、德国、法国、荷兰等全球 15 个数据中心。这个 VPS 服务商是按小时收费的，这意味着，架设一台 VPS 的成本几乎为零。假如你不想用美国的了，关机销毁然后再换到全球任何一个地区无压力。新手入门强烈推荐。



## 1、购买 Vultr VPS

#### 1. Vultr VPS主机官网账户注册

Vultr 官网账户注册，我们打开官网后输入邮箱和密码进行点击 Create Account 进行账户创建！限时活动，**通过文中链接注册并在30天内充值25美金可获赠50美金额度**。

访问 Vultr 活动官网地址：[Vultr活动官网](https://www.vultr.com/?ref=8169051-4F)

[![1](https://user-images.githubusercontent.com/52620310/62409248-0a93de80-b607-11e9-9da8-99182bb51016.png)](https://user-images.githubusercontent.com/52620310/62409248-0a93de80-b607-11e9-9da8-99182bb51016.png)

##### **账户注册注意问题**

账户注册密码要求至少十位，而且必须至少包含一个大写字母、一个小写字母和一个数字，如果提示注册成功需要邮箱验证的话，请到注册邮箱查看邮件并点击 Verify Your E-mail 验证邮箱（收件箱如果没有收到，查看下垃圾箱）！

[![2](https://user-images.githubusercontent.com/52620310/62409253-11baec80-b607-11e9-8e85-7eb324fefa60.png)](https://user-images.githubusercontent.com/52620310/62409253-11baec80-b607-11e9-8e85-7eb324fefa60.png)

#### 2. Vultr 账户充值

我们将 Vultr 账户注册好之后登录到 Vultr 官网后台景象账户充值。目前 Vultr 支持信用卡（Credit Card）、PayPal、比特币（Bitcoin）、支付宝（Alipay）和微信支付（WeChat Pay）五种付款方式。我们可以选择常用的支付宝和微信来进行充值即可。我们选择支付宝付款，确定首次充值金额，并且勾选同意条款后，点击按钮 **Pay with Alipay** 即可。

***PS：**如果我们有优惠码的话还可以在 Enter Code 输入优惠码并点击 Apply 进行应用，目前暂无官方优惠码！*

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200220170947047-1755045251.jpg)

我们稍等片刻后便会跳转到我们熟悉的支付宝付款页面，直接扫一扫或者登录账户付款就可以了，我们付款成功后可以在 Vultr 后台查看余额。

***PS：**为防止滥用账号重复申请，Vultr 会检测支付帐号，如果使用了同一个 PayPal 或信用卡去支付，会被 vultr 封号。*

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200220170951605-1862860575.jpg)

#### 3.Vultr 创建服务器

我们将左侧栏菜单切换到 Servers 进行服务器创建，我们首先选择服务器机房位置地址。这里我们搭建 SS 或 SSR 的话推荐日本东京（Tokyo，Japan）和美国洛杉矶（Los Angeles，United States）。

[![4](https://user-images.githubusercontent.com/52620310/62409258-1e3f4500-b607-11e9-8566-7712ed814588.png)](https://user-images.githubusercontent.com/52620310/62409258-1e3f4500-b607-11e9-8566-7712ed814588.png)

Vultr VPS 主机操作系统我们选择默认 CentOS。

[![5](https://user-images.githubusercontent.com/52620310/62409260-2303f900-b607-11e9-992b-75cabb3a0ddc.png)](https://user-images.githubusercontent.com/52620310/62409260-2303f900-b607-11e9-992b-75cabb3a0ddc.png)

我们选择 Vultr 套餐计划，套餐计划的最低价格根据主机位置的不同而不同，目前选择的日本东京最低套餐计划每月 5 美元，每小时 0.007 美元，配置是 1 个 CPU，1G 内存和 1000GB 流量。这个最低套餐计划完全可以满足我们个人需要了。

[![6](https://user-images.githubusercontent.com/52620310/62409262-26978000-b607-11e9-961e-375ef9c7e782.png)](https://user-images.githubusercontent.com/52620310/62409262-26978000-b607-11e9-961e-375ef9c7e782.png)

***PS：****我们根据自己的需求去选择相应的 VPS 主机配置，Vultr 采用小时计费，如果我们不想继续使用或创建新的 VPS 的时候，可以销毁多余的 VPS，扣除的费用是已使用小时数乘以小时单价，而不是按月扣费！*

我们如果对 IPv6 有需求的话可以勾选一下，其余的就保持默认就可以了，配置完成后我们直接点击 **Deploy Now** 进行 VPS 部署。

[![7](https://user-images.githubusercontent.com/52620310/62409265-2b5c3400-b607-11e9-950f-766539fe587e.png)](https://user-images.githubusercontent.com/52620310/62409265-2b5c3400-b607-11e9-950f-766539fe587e.png)

我们大约等待一分钟后就可以成功部署，当显示 **Running** 时，就表示部署已完成。之后你可以随时停用、重启或销毁它。

[![8](https://user-images.githubusercontent.com/52620310/62409267-2f885180-b607-11e9-9b16-cb89e92448ee.png)](https://user-images.githubusercontent.com/52620310/62409267-2f885180-b607-11e9-9b16-cb89e92448ee.png)

我们将 VPS 部署成功后就可以看到服务器的基本信息：ROOT 密码、IP 地址、内存、硬盘和带宽等相关信息，这样我们就成功部署了 VPS，接下来就要进行 SS 或 SSR 的搭建了。

[![9](https://user-images.githubusercontent.com/52620310/62409268-331bd880-b607-11e9-90cc-a0b2b1da7188.png)](https://user-images.githubusercontent.com/52620310/62409268-331bd880-b607-11e9-90cc-a0b2b1da7188.png)

我们创建好 VPS 之后在搭建 SS 或 SSR 之前我们可以通过 [IPIP.net](https://tools.ipip.net/traceroute.php) 这个网站对 IP 地址进行测试，VPS 正常响应的话我们就可以正常使用，如果无法连接的话我们就删除重新建一个 VPS。

[![10](https://user-images.githubusercontent.com/52620310/62409272-3747f600-b607-11e9-92fe-9aea33a49423.png)](https://user-images.githubusercontent.com/52620310/62409272-3747f600-b607-11e9-92fe-9aea33a49423.png)

## 2、SSH 连接 Vultr

首先你需要通过 SSH 连接 [Vultr](https://www.vultr.com/?ref=8169051-4F) 的 Linux VPS，连接 Linux VPS 需要使用 SSH 工具，这里推荐使用 Xshell 可以复制粘贴命令，Xshell 本身是需要付款的，作为中国人当然是使用 XX 版了，这里提供下载包如下所示：

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

## 3、在 Vultr 上部署 SS 或 SSR

在上图的待输入内容处，粘贴下面的命令（复制下面的命令，然后在 Xshell 待输入内容处“鼠标右键”/“粘贴”即可）：

```
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

（提示：如果运行上面第一条命令时，出现找不到wget之类的提示，则表明系统没有预装wget，先运行以下命令完成wget的安装）

```
CentOS：
yum -y install wget
Ubuntu/Debian：
apt-get -y install wget
```

3.接下来会有几个参数需要选择，依次为：

- 1.出现 SSR 安装的引导界面，输入数字2，按回车键进行 SSR 安装，如下图所示：

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170444298-1781403471.jpg)

- 2.然后会提示设置SSR密码，输入自定义密码后按回车，建议不要使用默认密码。

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170459564-483295482.jpg)

- 3.接下来选择SSR要使用的服务器端口，尽量选择一个比较大的数字，避免端口冲突，建议选择 8099，经验证 8080、8090 端口是被封了的，千万不要用这个（如果后面遇到可以登录 VPS，但是 ssr 上不了网，可能就是端口封了，修改一下 ssr 端口就可以了）， 然后回车，如下图所示：

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170505895-1680287078.jpg)

- 4.然后选择加密方式，如果选择chacha20的话，就输入对应序号12，按回车继续。

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170514488-1849603840.jpg)

- 5.接下来选择协议，建议选择自auth_aes128_md5开始以下的几种，输入对应序号按回车。

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170543807-1693020693.jpg)

- 6.然后选择混淆方式，如下图所示，选择好后按回车。

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170553509-1844501351.jpg)

- 7.以上参数选择完成后，按任意键开始安装。

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170557621-2142405219.jpg)

- 8.安装完成后，会有如下图安装成功的提示。

![](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200219170559370-1432378159.jpg)

按照上面的图片就可以看到设置的 SSR 账号信息，包括 IP、端口、密码、加密方式、协议插件、混淆插件，这些信息都需要填入对应的 SSR 客户端。

- 9.经过以上几个简单的参数选择后，SSR服务器端已经自动安装成功了。保险起见，输入reboot重启VPS服务器，SSR会自动随系统重启。

## 4、Vultr 搭建 BBR 加速

虽然 SSR 搭建好了，但是速度还不是很快，要搭建 BBR 才快，下面我们就说说怎么搭建 BBR。

BBR 是 Google 的一款 SSR 加速产品，使用下面的命令就可以实现 BBR 加速，只有 [Vultr](https://www.vultr.com/?ref=8169051-4F) 等少数 KVM VPS 才支持 BBR 加速，这也是我们推荐选择 Vultr 的原因。

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



## 6、Vultr 搭建 SS 或 SSR 总结

以上就是美国 VPS Vultr 搭建 SS 或 SSR 的教程，通过教程可以轻松实现 Vultr 搭建 SS 或 SSR，希望可以帮助需要使用 Vultr 搭建 SS 或 SSR 的朋友。

[**通过本链接注册并在30天内充值25美金可获赠50美金额度**](https://www.vultr.com/?ref=8169051-4F)，支持支付宝付款，欢迎购买注册。