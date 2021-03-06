目前相对主流的 VPS 恐怕就是 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) 、[Vultr](https://www.vultr.com/?ref=8169047)、[搬瓦工banwahost](https://bwh88.net/aff.php?aff=54381&pid=94)和 [Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 这几个吧。经历过这么多的折腾之后，如何选择有的时候真的是个问题。本文针对这四家的最低配置，搭建好应用，测试下具体真实表现。坐标北京联通。



**测试对比结果：（满分10分）**

| 主机商                                                       | 测试期间 | 测试宽带 | 数据中心 | 价格     | 1080视频 | 4K视频 | 稳定性 | 延迟   |
| ------------------------------------------------------------ | -------- | -------- | -------- | -------- | -------- | ------ | ------ | ------ |
| [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) | 晚高峰   | 北京联通 | 西雅图   | 4.49美元 | 10分     | 9分    | 9分    | 180ms+ |
| [Vultr](https://www.vultr.com/?ref=8169047)                  | 晚高峰   | 北京联通 | 日本     | 5.00美元 | 10分     | 7分    | 6分    | 90ms+  |
| [搬瓦工](https://bwh88.net/aff.php?aff=54381&pid=94)         | 晚高峰   | 北京联通 | 洛杉矶   | 5.99美元 | 9分      | 7分    | 8分    | 150ms+ |
| [Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) | 晚高峰   | 北京联通 | 马来西亚 | 3.95美元 | 10分     | 8分    | 9分    | 160ms+ |

**综合性价比：[Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) > [Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) > [搬瓦工](https://bwh88.net/aff.php?aff=54381&pid=94) > [Vultr](https://www.vultr.com/?ref=8169047)**

无责任结论如下，四家 VPS 分别适合以下三类用户使用。

需求全球多个节点的，能看4K视频的购买 [Vultr](https://www.vultr.com/?ref=8169047)、[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39)

要求打开网页速度快，能看4K视频的购买 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) 、[搬瓦工](https://bwh88.net/aff.php?aff=54381&pid=94)

要求速度快和稳定的选 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) （关键是现在可以免费更换IP）

[Vultr](https://www.vultr.com/?ref=8169047)：5美元一月的日本节点，Youtube 的速度。

![Vultr](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218144202023-133782186.jpg)

[Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224)：4.49美元西雅图节点在 Youtube 的速度。

![hostwinds](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218144208441-110767763.jpg)



[**Hostwinds**](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1216) 是一家美国主机商，成立于 2010 年，国内站长使用较多的是 Hostwinds 美国 VPS 主机产品。由于 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) 美国 VPS 主机采用的是 SSD 硬盘，而且所有方案都有全球 CDN 加速功能，因而也备受用户青睐。 如今 Hostwinds 主机商提供的产品方案也非常丰富，包括虚拟主机、云主机、VPS主机以及独立主机等。目前 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1216) 主要有达拉斯、西雅图 2 个数据中心，其中西雅图数据中心在国内访问速度最快。现在 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224) 提供免费更换IP了，没错，就是免费，免费，随意更换，可以一键解决 IP 被墙的问题了。通过 Hostwinds 搭建 SSR 是不错的选择，今天就讲解下 Hostwinds 搭建 SSR 教程。

## 1、购买 Hostwinds VPS

首先确认不要使用任何代理，网络是什么 IP 就是什么 IP ，不然可能需要人工审核，导致 Hostwinds VPS 购买显示 "Pending" 状态， 不能即时创建服务激活。

1、通过[ Hostwinds 优惠链接进入](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224)Hostwinds 首页，选择 “VPS” 下的 "Unmanaged VPS" ，这里是最便宜的**(注意千万不要选择页面上 3.29 美元那个，那个是虚拟空间，不是 VPS !!!)**。

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123839832-773141474.jpg)

2、进入 VPS 选择页面后，根据自己的需要的配置选择套餐，一般我们选择最低配置就够用了，然后点击 “Order” 按钮进入信息填写页面，如下所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123900867-1301510135.jpg)

3、进入信息填写页面后首先填写账号信息，一般是新用户我们填写左边的姓、名、邮箱、密码，然后点击 “Submit” 进入下一步，如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123924864-1748236610.jpg)

4、页面跳转后填写用户信息，如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123926145-1078179475.jpg)

5、然后选择购买时间、数据中心 、操作系统，红色部分需要自己选择，绿色一般我们默认，可以按月购买，但是建议第一次购买时间选择长一点，这样优惠要大很多，不然后面续费优惠力度就没有这么大了。 如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218144258557-35784363.jpg)

6、默认是自动云备份的，如果不需要去掉勾选， 如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123930711-100437514.jpg)

7、然后选择付款方式，一般我们选择支付宝进行付款 （只有国内 IP 访问的时候才有支付宝付款方式），如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123932418-465353102.jpg)

8、最后确认价格（不同时期可能价格有些许不同，如果通过前面优惠链接点击购买会有优惠），勾选同意协议，然后点击“Complete Order”按钮进行下单， 如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218144305766-1117833017.jpg)

9、下单完成后订单结果如下图所示：

![img](https://img2018.cnblogs.com/blog/1765496/202002/1765496-20200218123936407-829196891.jpg)

剩下的工作就可以用SSH远程工具来进行了。



#### HostWinds主机常见问题汇总

购买后服务器连接不上。

解决方法：一般服务器刚买就连接不上的，主要有各个方面原因，请先用IP检测工具检测下你的IP：点击检测 打开网址输入你的IP和22端口点击检测（一定要多检测几次），如果国内和国外ICMP都不通的话就是网络崩溃了，重装下VPS系统就可以。如果一直出现只有国内ICMP不通，那就考虑**免费更换一个IP**吧。

[HOSTWINDS官方10%优惠直达链接](https://affiliates.hostwinds.com/hostwinds.php?id=7011&tid2=github&url=1224)