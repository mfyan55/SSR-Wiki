## **什么是shadowsocks**

shadowsocks 可以指一种 SOCKS5 的加密传输协议，也可以指基于这种加密协议的各种数据传输包。

**shadowsocks 实现科学上网原理？**

shadowsocks 正常工作需要服务器端和客户端两端合作实现，首先，客户端（本机）通过 SS（shadowsocks）对正常的访问请求进行 SOCK5 加密，将加密后的访问请求传输给 SS 服务器端，服务器端接收到客户端的加密请求后，解密得到原始的访问请求，根据请求内容访问指定的网站（例如Google，YouTube，Facebook，instagram 等），得到网站的返回结果后，再利用 SOCKS5 加密并返回给客户端，客户端通过 SS 解密后得到正常的访问结果，于是就可以实现你直接访问该网站的“假象”。

**为什么选择 shadowsocks？**

不限终端（安卓，苹果，Windows，Mac 都可用），流量便宜（服务器 1TB 只要 30 元），方便（一键脚本，不需要专业知识）。

## 为什么要自己搭建 SS/SSR？

你也许会觉得买 SS 服务也很方便，但是你得要考虑以下几个问题。首先，买的 SS 服务，限制很多，终端可能只能同时在线 2 个，每个月就一点点流量可能价格却不便宜，有时候还被别人做手脚，流量跑的贼快；其次，别人收钱跑路怎么办？很多这种情况的；更重要的是，如第一个问题中描述的shadowsocks 原理，如果有心人做了一点手脚，是可以得到你的访问记录的；而自己搭建 SS/SSR 服务，一键脚本也就 10 来分钟就可以搞定。

[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 成立于 2004 年 11 月，在美国、亚洲和欧洲都设有机房，骨干网络采用1000Mbps宽带连接，这可以大幅提升你的访问速度。目前为 178 个国家和地区的超过 3000 万名客户提供服务。[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 的承诺是创建一个易于使用、稳定可靠，适合于开发人员的网络托管服务，并且以所有人都能接受的价格提供一流的功能和安全性，以及快速、优质的客户服务。[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 为了开拓中国市场，推出了 [中文版](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 网站，并且接受支付宝、微信、银联等本地付款方式。通过 Hostinger 搭建 SSR 是不错的选择，今天就讲解下 Hostinger 搭建 SSR 教程。

## 1、购买 Hostinger VPS

1、通过 [Hostinger 优惠链接进入](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) Hostinger 中文版首页，选择 “产品” 下的 " VPS主机" 。

![1](https://user-images.githubusercontent.com/54033249/64271400-d4cc7780-cf6f-11e9-9730-61ae0e0c52f9.jpg)

2、进入 VPS 选择页面后，根据自己的需要的配置选择套餐，一般我们选择最低配置就够用了，然后点击 “添加购物车” 按钮进入信息填写页面，如下所示：

![2](https://user-images.githubusercontent.com/54033249/64271407-dac25880-cf6f-11e9-9799-17415bd5fc2c.jpg)

3、进入购物车界面，购买时间最少一个月，第一次购买时间越长优惠力度越大，长期使用建议购买时间长点，不然后面续费就没有那么大优惠了。确认无误后，点击 “现在结账”按钮 进入下一步，如下图所示：

![3](https://user-images.githubusercontent.com/54033249/64271432-e57ced80-cf6f-11e9-951f-30518ad91c78.jpg)

4、进入下一页，输入你的账户信息，请确保使用有效的电子邮件地址，如下图所示：

![5](https://user-images.githubusercontent.com/54033249/64271445-e9a90b00-cf6f-11e9-8bb1-3ffe49bed013.jpg)

确认无误后，点击**创建账号并结账**按钮。

5、接下来，填写你的结算信息， Hostinger 目前提供多种支付方式：

![6](https://user-images.githubusercontent.com/54033249/64271451-eca3fb80-cf6f-11e9-840f-6858036fe4dd.jpg)

6、在这篇文章中，我们以支付宝为例，选择第二排的 Alipay 图标：

![7](https://user-images.githubusercontent.com/54033249/64271461-f168af80-cf6f-11e9-9f20-ce5d31ae9a40.jpg)

7、点击 **Continue** 按钮，浏览器会打开支付宝结算窗口，扫码付款之后，订单就完成了。

这时候，你应该会收到 3 封电子邮件，其中一封是邮箱验证，为了避免以后可能遇到的麻烦，请点击邮件中的 **Verify my email** 按钮以激活账户：

![8](https://user-images.githubusercontent.com/54033249/64271481-f4fc3680-cf6f-11e9-8989-466e88477be0.jpg)



## 2、SSH 连接 Hostinger

首先你需要通过 SSH 连接 [Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 的 Linux VPS，连接 Linux VPS 需要使用 SSH 工具，这里推荐使用 Xshell 可以复制粘贴命令，Xshell 本身是需要付款的，作为中国人当然是使用 XX 版了，这里提供下载包如下所示：

Xshell 下载地址：<https://pan.baidu.com/s/1v7RCM0IjZGn_q5aWS1WXWg>，提取码: q3jw

下载后解压安装即可。

#### 使用 Xshell 连接 Linux VPS

1、打开 Xshell，点击左上角“文件”-“新建”，打开连接弹出库。

![10](https://user-images.githubusercontent.com/54033249/64271493-f88fbd80-cf6f-11e9-9cff-6de26f272c64.jpg)

2、在 Xshell 弹出框中输入 IP 和端口，端口一般是 22 默认，然后点击确认按钮，如下图所示：

![11](https://user-images.githubusercontent.com/54033249/64271505-fded0800-cf6f-11e9-809a-1b261629c317.jpg)

3、然后输入用户名 root，勾选记住用户名。

![12](https://user-images.githubusercontent.com/54033249/64271512-02192580-cf70-11e9-82c2-71921287081e.jpg)

4、然后输入密码，勾选记住密码，点击确定。

![13](https://user-images.githubusercontent.com/54033249/64271521-07767000-cf70-11e9-808f-6fba86ae281a.jpg)

完成以上步骤后就可以看到连接成功的界面，如下图所示：

![14](https://user-images.githubusercontent.com/54033249/64271557-178e4f80-cf70-11e9-93a9-4a73760f5c81.jpg)



## 3、Hostinger 安装 SSR 开始

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



## 4、客户端搭建ssr代理

各种客户端版本下载地址：[各版本SSR客户端官方下载地址](https://github.com/xiaoming2028/kexueshangwang/releases)

以Windows为例：

![ssr-pc-windows-config](https://user-images.githubusercontent.com/54033249/64271745-75bb3280-cf70-11e9-94a0-9fa30ebcf6e2.png)

在状态栏右击shadowsocksR，在**系统代理模式**中选择**PAC模式**，再左击两次状态栏的图标打开编辑服务器界面，如上图所示，按照自己的服务器配置填充内容**，**保存即可~

**PAC模式**是指国内可以访问的站点直接访问，不能直接访问的再走shadowsocksR代理~

OK！一键脚本搭建shadowsocksR完毕！科学上网吧，兄弟！



## 5、Hostinger 搭建 SSR 总结

以上就是 [Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 搭建 SSR 的教程，通过教可以轻松实现 Hostinger 搭建 SSR，希望可以帮助需要使用 Hostinger 搭建 SSR 的朋友。

[Hostinger 最快VPS低至3.95美元/月](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39)，有中文界面，支持支付宝、微信付款，欢迎购买注册。