## 什么是Brook

Brook 是一款新兴的代理软件，其版本横垮 Windows、安卓、iOS、MacOS、Linux 等多个系统平台，功能类似于我们经常使用的 Shadowsocks/ShadowsocksR。Brook 的目标是简单易用、傻瓜化、速度快（新协议）。通过在服务器端安装 Brook 服务器端，同时在本地设备中使用 Brook 客户端，两者成功连接之后，可以为我们提供科学上网服务。如果你想在 SS/SSR/V2ray 之外，尝试一种新的代理软件，那么 Brook 是一个不错的选择！



> ### 搭建Brook服务的教程分四步：
>
> 1、购买VPS服务器
>
> 2、连接VPS服务器
>
> 3、一键部署Brook服务
>




## 1、购买 Hostinger VPS

[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 成立于 2004 年 11 月，在美国、亚洲和欧洲都设有机房，骨干网络采用1000Mbps宽带连接，这可以大幅提升你的访问速度。目前为 178 个国家和地区的超过 3000 万名客户提供服务。[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 的承诺是创建一个易于使用、稳定可靠，适合于开发人员的网络托管服务，并且以所有人都能接受的价格提供一流的功能和安全性，以及快速、优质的客户服务。[Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 为了开拓中国市场，推出了 [中文版](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 网站，并且接受支付宝、微信、银联等本地付款方式。

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



## 2、SSH连接VPS服务器

首先你需要通过 SSH 连接 [Hostinger](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39) 的 Linux VPS，连接 Linux VPS 需要使用 SSH 工具，这里推荐使用 Xshell 可以复制粘贴命令，Xshell 本身是需要付款的，作为中国人当然是使用 XX 版了，这里提供下载包如下所示：

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



## 3、一键部署Brook服务

在上图的待输入内容处，粘贴下面的命令（复制下面的命令，然后在 Xshell 待输入内容处“鼠标右键”/“粘贴”即可）：

```
# 安装wget
sudo yum -y install wget
wget -N --no-check-certificate wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/brook.sh
chmod +x brook.sh
./brook.sh
```

![1](https://user-images.githubusercontent.com/52620310/62551701-0d106580-b89f-11e9-8678-b3d304063a0e.png)

然后跟着提示一步一步往下走就可以了，会有 0-10 这个 11 个选项，因为我们是要安装 Brook， 所以输入数字**1**，然后按回车开始进入下一步。

接着会提示输入端口号，你可以按默认的端口来，这里我输入 10234 。

接着会提示你输入 Brook 密码，这里输入你自己心仪的密码即可。

最后会叫你输入 Brook 协议，按默认的来，这里我输入 1，整个步骤截图如下：

![2](https://user-images.githubusercontent.com/52620310/62551722-14d00a00-b89f-11e9-8027-c6759ffd5a0b.png)

然后按下回车开始安装：

![3](https://user-images.githubusercontent.com/52620310/62551734-18fc2780-b89f-11e9-9cdf-8210b912017f.png)

整个安装过程很快，花不了多长时间，安装成功后界面会提示你的 Brook 连接地址、端口、密码与及使用的协议，如下：

![4](https://user-images.githubusercontent.com/52620310/62551742-1c8fae80-b89f-11e9-80ed-13018f549a89.png)




## Brook客户端下载及使用方法

搭建完成后，就可以下载安装客户端，然后愉快的使用代理了。

Brook 客户端最新版下载地址: https://github.com/txthinking/brook/releases 如：

![5](https://user-images.githubusercontent.com/52620310/62551764-23b6bc80-b89f-11e9-8686-694de14f1bf6.png)

这里以 window 客户端为例，下载完后，直接解压然后打开 Brook.Setup.exe 即可开始安装：

![6](https://user-images.githubusercontent.com/52620310/62551776-27e2da00-b89f-11e9-96c7-05396d589de8.png)

安装成功后，打开客户端，然后输入连接类型、连接地址和端口、连接密码，按 save 即可保存连接。如下：

![7](https://user-images.githubusercontent.com/52620310/62551794-2ca78e00-b89f-11e9-9ebc-00d1f64a559a.png)

#### 启动Brook

你用鼠标右击 Brook 右下角管理栏的小图标（一个黑钥匙的图标），会有一个 Toggle 选项：

![8](https://user-images.githubusercontent.com/52620310/62551804-316c4200-b89f-11e9-9e35-5727f17c255e.png)

Toggle 代表启动/停止 Brook 代理。当你启动 Brook 后，你把鼠标移动到右下角管理栏的小图标，会提示：Brook：started，如下：

![9](https://user-images.githubusercontent.com/52620310/62551818-36c98c80-b89f-11e9-9db7-db889548d1d3.png)

连接成功后，就可以开始愉快的使用外网了。



## 总结

以上就是用Hostinger 一键搭建 Brook 服务的教程，通过教程可以轻松实现 Hostinger 搭建 Brook，希望可以帮助需要使用 Hostinger 搭建 Brook 的朋友。

[Hostinger 最快VPS低至3.95美元/月](https://www.hostg.xyz/aff_c?offer_id=6&aff_id=18493&aff_sub=GitHub&url_id=39)，有中文界面，支持支付宝、微信付款，欢迎购买注册。