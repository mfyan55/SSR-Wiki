## **什么是shadowsocks**

shadowsocks 可以指一种 SOCKS5 的加密传输协议，也可以指基于这种加密协议的各种数据传输包。

**shadowsocks 实现科学上网原理？**

shadowsocks 正常工作需要服务器端和客户端两端合作实现，首先，客户端（本机）通过 SS（shadowsocks）对正常的访问请求进行 SOCK5 加密，将加密后的访问请求传输给 SS 服务器端，服务器端接收到客户端的加密请求后，解密得到原始的访问请求，根据请求内容访问指定的网站（例如Google，YouTube，Facebook，instagram 等），得到网站的返回结果后，再利用 SOCKS5 加密并返回给客户端，客户端通过 SS 解密后得到正常的访问结果，于是就可以实现你直接访问该网站的“假象”。

**为什么选择 shadowsocks？**

不限终端（安卓，苹果，Windows，Mac 都可用），流量便宜（服务器 1TB 只要 30 元），方便（一键脚本，不需要专业知识）。

### 为什么要自己搭建 SS/SSR？

你也许会觉得买 SS 服务也很方便，但是你得要考虑以下几个问题。首先，买的 SS 服务，限制很多，终端可能只能同时在线 2 个，每个月就一点点流量可能价格却不便宜，有时候还被别人做手脚，流量跑的贼快；其次，别人收钱跑路怎么办？很多这种情况的；更重要的是，如第一个问题中描述的shadowsocks 原理，如果有心人做了一点手脚，是可以得到你的访问记录的；而自己搭建 SS/SSR 服务，一键脚本也就 10 来分钟就可以搞定。

[搬瓦工VPS（BandwagonHost）](https://bandwagonhost.com/aff.php?aff=54381) 隶属于美国IT7公司旗下的一款便宜年付KVM架构的VPS主机商家，从2013年开始推出低价VPS主机配置进入市场，确实受到广大网友的喜欢。2019年春节期间，[搬瓦工VPS](https://bandwagonhost.com/aff.php?aff=54381)主机商又提供包括香港PCCW、洛杉矶CN2 GIA、洛杉矶CN2 GIA-E，以及CN2 GT等12个数据中心，相比同类商家，[搬瓦工VPS](https://bwh88.net/aff.php?aff=54381&pid=57) 主机商的配置是比较高，线路还是比较好的。[搬瓦工VPS](https://bwh88.net/aff.php?aff=54381&pid=94) 商家支持支付宝、微信、PAYPAL、银联以及信用卡多种付款方式，这个也是很多国内用户选择的原因之一。通过 搬瓦工VPS 搭建 SSR 是不错的选择，今天就讲解下 搬瓦工VPS 搭建 SSR 教程。

## 1、购买 搬瓦工VPS

**注意：**

- 不要挂代理！否则会被判为欺骗；
- **注册时地址填中国；**
- 如果点击购买链接进入页面显示 “Out of Stock” 即为售空，可选择更高一级或其它套餐。

### 1、选择套餐

5个搬瓦工套餐机房的**速度比较**：搬瓦工香港PCCW  > 搬瓦工CN2 GIA-E  > 搬瓦工CN2 GIA  > 搬瓦工CN2  > 搬瓦工KVM套餐，价格自然也是这个顺序。

简单推荐如下：

1. 需要**低延迟建站**或者**游戏加速**：搬瓦工香港PCCW；
2. **性价比建站方案**：搬瓦工CN2 GIA-E（[点击直达](https://bwh88.net/aff.php?aff=54381&pid=87)）
3. **性价比方案**：搬瓦工CN2 年付49.99美元（[点击直达](https://bwh88.net/aff.php?aff=54381&pid=57)）
4. **补货通知**：对于不急着购买的用户，可以等待搬瓦工CN2 GIA-E限量版补货（[点击直达](https://bwh88.net/aff.php?aff=54381&pid=94)（如果你看到的时候正好有货，那么不要迟疑，就它了，性价比最高）），目前大概1-4周会补货一次。

**优惠码：**`BWH26FXH3HIQ`，付款时使用可优惠 6.25% 。**（重要！）**

> **选择建议：在预算范围内尽量选择质量最高的，免得买完不满意再折腾。优先选择 CN2 GT 和 GIA 套餐。为方便大家选择，下面列出了搬瓦工目前所有套餐和简介。**

推荐购买的搬瓦工套餐如下

| 线路    | CPU  | 内存     | 硬盘   | 带宽      | 流量        | 价格              | 链接                                               |
| ------- | ---- | -------- | ------ | --------- | ----------- | ----------------- | -------------------------------------------------- |
| 香港    | 2 核 | 2048 MB  | 40 GB  | 1 G       | 500GB / 月  | **$89.99 / 月**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=95) |
| 香港    | 4 核 | 4096 MB  | 80 GB  | 1 G       | 1000GB / 月 | $155.99 / 月      | [购买](https://bwh88.net/aff.php?aff=54381&pid=96) |
| 香港    | 6 核 | 8192 MB  | 160 GB | 1 G       | 2000GB / 月 | $299.99 / 月      | [购买](https://bwh88.net/aff.php?aff=54381&pid=97) |
| 香港    | 8 核 | 16384 MB | 320 GB | 1 G       | 4000GB / 月 | $589.99 / 月      | [购买](https://bwh88.net/aff.php?aff=54381&pid=98) |
| -       | -    | -        | -      | -         | -           | -                 | -                                                  |
| CN2 GIA | 2 核 | 1 GB     | 20 GB  | **2.5 G** | 1000GB / 月 | **$65.99 / 半年** | [购买](https://bwh88.net/aff.php?aff=54381&pid=87) |
| CN2 GIA | 3 核 | 2 GB     | 40 GB  | **2.5 G** | 2000GB / 月 | $69.99 / 季       | [购买](https://bwh88.net/aff.php?aff=54381&pid=88) |
| CN2 GIA | 4 核 | 4 GB     | 80 GB  | **2.5 G** | 3000GB / 月 | $49.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=89) |
| CN2 GIA | 6 核 | 8 GB     | 160 GB | **5 G**   | 5000GB / 月 | $75.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=90) |
| -       | -    | -        | -      | -         | -           | -                 | -                                                  |
| CN2 GIA | 1 核 | 512 MB   | 10 GB  | 1 G       | 300GB / 月  | **$39.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=71) |
| CN2 GIA | 1 核 | 512 MB   | 10 GB  | 1 G       | 500GB / 月  | **$49.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=94) |
| CN2 GIA | 2 核 | 1024 MB  | 20 GB  | 1 G       | 1000GB / 月 | **$25.99 / 季**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=72) |
| CN2 GIA | 3 核 | 2048 MB  | 40 GB  | 1 G       | 2000GB / 月 | $51.99 / 季       | [购买](https://bwh88.net/aff.php?aff=54381&pid=73) |
| CN2 GIA | 4 核 | 4096 MB  | 80 GB  | 1 G       | 3000GB / 月 | $32.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=74) |
| CN2 GIA | 6 核 | 8GB      | 160 GB | 1 G       | 5000GB / 月 | $62.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=75) |
| CN2 GIA | 8 核 | 16GB     | 320 GB | 1 G       | 8000GB / 月 | $119.99 / 月      | [购买](https://bwh88.net/aff.php?aff=54381&pid=76) |
| -       | -    | -        | -      | -         | -           | -                 | -                                                  |
| CN2     | 1 核 | 1024 MB  | 20 GB  | 1 G       | 1000GB / 月 | **$49.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=57) |
| CN2     | 1 核 | 2048 MB  | 40 GB  | 1 G       | 2000GB / 月 | $52.99 / 半年     | [购买](https://bwh88.net/aff.php?aff=54381&pid=58) |
| CN2     | 2 核 | 4096 MB  | 80 GB  | 1 G       | 3000GB / 月 | $59.99 / 季       | [购买](https://bwh88.net/aff.php?aff=54381&pid=59) |
| CN2     | 2 核 | 8 GB     | 160 GB | 1 G       | 5000GB / 月 | $39.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=67) |
| CN2     | 3 核 | 16 GB    | 320 GB | 1 G       | 8000GB / 月 | $79.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=68) |
| -       | -    | -        | -      | -         | -           | -                 | -                                                  |
| 普通    | 2 核 | 1024 MB  | 20 GB  | 1 G       | 1 TB / 月   | **$49.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=44) |
| 普通    | 3 核 | 2 GB     | 40 GB  | 1 G       | 2 TB / 月   | $52.99 / 半年     | [购买](https://bwh88.net/aff.php?aff=54381&pid=45) |
| 普通    | 4 核 | 4 GB     | 80 GB  | 1 G       | 3 TB / 月   | $19.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=46) |
| 普通    | 5 核 | 8 GB     | 160 GB | 1 G       | 4 TB / 月   | $39.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=47) |
| 普通    | 6 核 | 16 GB    | 320 GB | 1 G       | 5 TB / 月   | $79.99 / 月       | [购买](https://bwh88.net/aff.php?aff=54381&pid=48) |
| 普通    | 7 核 | 24 GB    | 480 GB | 1 G       | 6 TB / 月   | $119.99 / 月      | [购买](https://bwh88.net/aff.php?aff=54381&pid=49) |

选择哪个套餐？如果你不知道选择哪个套餐
下面这是最常见的购买套餐

| 线路    | CPU  | 内存    | 硬盘  | 带宽      | 流量        | 价格              | 链接                                               |
| ------- | ---- | ------- | ----- | --------- | ----------- | ----------------- | -------------------------------------------------- |
| 普通    | 2 核 | 1024 MB | 20 GB | 1 G       | 1 TB / 月   | **$49.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=44) |
| CN2     | 1 核 | 1024 MB | 20 GB | 1 G       | 1000GB / 月 | **$49.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=57) |
| CN2 GIA | 1 核 | 512 MB  | 10 GB | 1 G       | 300GB / 月  | **$39.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=71) |
| CN2 GIA | 1 核 | 512 MB  | 10 GB | 1 G       | 500GB / 月  | **$49.99 / 年**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=94) |
| CN2 GIA | 2 核 | 1024 MB | 20 GB | 1 G       | 1000GB / 月 | **$25.99 / 季**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=72) |
| CN2 GIA | 2 核 | 1 GB    | 20 GB | **2.5 G** | 1000GB / 月 | **$65.99 / 半年** | [购买](https://bwh88.net/aff.php?aff=54381&pid=87) |
| 香港    | 2 核 | 2048 MB | 40 GB | 1 G       | 500GB / 月  | **$89.99 / 月**   | [购买](https://bwh88.net/aff.php?aff=54381&pid=95) |

（**注：年付会优惠大概两个月的金额；**部分套餐可能会缺货；或太火了取消了月付方案，只有年付/季付）

### 1.2 添加商品

在上面选择合适的套餐，点击对应购买链接，进入添加界面，选择付费方式、机房，然后点击 **“Add to Cart”** 添加。

![1](https://user-images.githubusercontent.com/54033249/70500777-50cdf100-1b57-11ea-81e9-a549026c6631.png)



### 1.3 确认订单

订单确认：输入**优惠码** **BWH26FXH3HIQ** → “Validata Code” → “Checkout” 付款。

![2](https://user-images.githubusercontent.com/54033249/70500779-51668780-1b57-11ea-9e5a-bf2b93c3f0ff.png)

![3](https://user-images.githubusercontent.com/54033249/70500780-51668780-1b57-11ea-97d5-fbf4ea03cbdb.png)

订单页面，输入注册信息。**如实填写，中国就填中国！**否则可能判断为欺骗购买失败。

付款方式选择支付宝，**“Complete Order”**，完成订单。

![4](https://user-images.githubusercontent.com/54033249/70500781-51668780-1b57-11ea-9466-56cb6b594b23.png)



支付完成功后会收到邮件通知。**SSH 的 IP、密码和端口号会发送到我们的邮箱。**可以通过 Xshell 等 SSH 工具登录 VPS 系统进行操作。（未收到请检查垃圾箱）

![7](https://user-images.githubusercontent.com/54033249/70500787-53304b00-1b57-11ea-8729-8bcd91a19a7b.png)

**购买创建 VPS 完成！**

## 2、SSH 连接 Hostwinds

首先你需要通过 SSH 连接 [搬瓦工](https://bandwagonhost.com/aff.php?aff=54381) 的 Linux VPS，连接 Linux VPS 需要使用 SSH 工具，这里推荐使用 Xshell 可以复制粘贴命令，Xshell 本身是需要付款的，作为中国人当然是使用 XX 版了，这里提供下载包如下所示：

Xshell 下载地址：<https://pan.baidu.com/s/1v7RCM0IjZGn_q5aWS1WXWg>，提取码: q3jw

下载后解压安装即可。

#### 使用 Xshell 连接 Linux VPS

1、打开 Xshell，点击左上角“文件”-“新建”，打开连接弹出库。

[![img](https://user-images.githubusercontent.com/52620310/62405920-537f6f00-b5d6-11e9-8665-b9ff1741d477.jpg)](https://user-images.githubusercontent.com/52620310/62405920-537f6f00-b5d6-11e9-8665-b9ff1741d477.jpg)

2、在 Xshell 弹出框中输入 IP 和端口，端口一般是 22 默认，然后点击确认按钮，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405922-567a5f80-b5d6-11e9-8b7a-2662799e0585.jpg)](https://user-images.githubusercontent.com/52620310/62405922-567a5f80-b5d6-11e9-8b7a-2662799e0585.jpg)

3、然后输入用户名 root，勾选记住用户名。

[![img](https://user-images.githubusercontent.com/52620310/62405925-5a0de680-b5d6-11e9-87bf-426f33dab264.jpg)](https://user-images.githubusercontent.com/52620310/62405925-5a0de680-b5d6-11e9-87bf-426f33dab264.jpg)

4、然后输入密码，勾选记住密码，点击确定。

[![img](https://user-images.githubusercontent.com/52620310/62405927-5e3a0400-b5d6-11e9-9b46-231b6b152909.jpg)](https://user-images.githubusercontent.com/52620310/62405927-5e3a0400-b5d6-11e9-9b46-231b6b152909.jpg)

完成以上步骤后就可以看到连接成功的界面，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405930-64c87b80-b5d6-11e9-9f01-3a5ab54e1dda.jpg)](https://user-images.githubusercontent.com/52620310/62405930-64c87b80-b5d6-11e9-9f01-3a5ab54e1dda.jpg)

## 3、搬瓦工 安装 SSR 开始

在上图的待输入内容处，粘贴下面的命令（复制下面的命令，然后在 Xshell 待输入内容处“鼠标右键”/“粘贴”即可）：

```
yum -y install wget
wget -N –no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh
```

粘贴后会下载相关安装包，等待屏幕不动的时候按“回车键”，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405971-c5f04f00-b5d6-11e9-8347-343e29e69a29.jpg)](https://user-images.githubusercontent.com/52620310/62405971-c5f04f00-b5d6-11e9-8347-343e29e69a29.jpg)

然后等待一会儿，出现 SSR 安装的引导界面，输入数字1，按回车键进行 SSR 安装，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405974-cab50300-b5d6-11e9-92ef-28ba7701a5c1.jpg)](https://user-images.githubusercontent.com/52620310/62405974-cab50300-b5d6-11e9-92ef-28ba7701a5c1.jpg)

然后输入端口，尽量选择一个比较大的数字，避免端口冲突，建议选择 8099，经验证 8080、8090 端口是被封了的，千万不要用这个（如果后面遇到可以登录 VPS，但是 ssr 上不了网，可能就是端口封了，修改一下 ssr 端口就可以了）， 然后回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405976-d0124d80-b5d6-11e9-91dc-dba0511bea55.jpg)](https://user-images.githubusercontent.com/52620310/62405976-d0124d80-b5d6-11e9-91dc-dba0511bea55.jpg)

然后输入 SSR 账号的密码，随便输入一个密码，这里输入123qweasd，然后回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405978-d6082e80-b5d6-11e9-8ab2-c987c2a60129.jpg)](https://user-images.githubusercontent.com/52620310/62405978-d6082e80-b5d6-11e9-8ab2-c987c2a60129.jpg)

然后输入 SSR 账号的加密方式，随便输入 10，选择 aes-256-cfb 的加密方式，然后回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405979-dbfe0f80-b5d6-11e9-8238-bc7b391a1191.jpg)](https://user-images.githubusercontent.com/52620310/62405979-dbfe0f80-b5d6-11e9-8238-bc7b391a1191.jpg)

然后输入 SSR 账号的协议插件，随便输入 2，选择 auth_sha1_v4 的协议插件，然后回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405981-e0c2c380-b5d6-11e9-8b98-01d17b915e8f.jpg)](https://user-images.githubusercontent.com/52620310/62405981-e0c2c380-b5d6-11e9-8b98-01d17b915e8f.jpg)

然后选择是否设置协议插件兼容原版，随便输入 y，表示要设置，然后回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405984-e7513b00-b5d6-11e9-8580-e0dfeef1fdd5.jpg)](https://user-images.githubusercontent.com/52620310/62405984-e7513b00-b5d6-11e9-8580-e0dfeef1fdd5.jpg)

然后选择混淆插件，这里选择 1，然后回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405985-ec15ef00-b5d6-11e9-92a7-4756e17a332b.jpg)](https://user-images.githubusercontent.com/52620310/62405985-ec15ef00-b5d6-11e9-92a7-4756e17a332b.jpg)

然后设置限制的设备数，如果要限制就输入对于的数字，如果不限制就直接回车，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405989-f1733980-b5d6-11e9-8ce5-763ece4d8dee.jpg)](https://user-images.githubusercontent.com/52620310/62405989-f1733980-b5d6-11e9-8ce5-763ece4d8dee.jpg)

然后设置每个端口的速度，如果要限制就输入对于的数字，单位是 KB/S，如果不限制就直接回车，建议不限制速度，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405996-fb953800-b5d6-11e9-92dd-2908259317e5.jpg)](https://user-images.githubusercontent.com/52620310/62405996-fb953800-b5d6-11e9-92dd-2908259317e5.jpg)

然后设置总的速度，如果要限制就输入对于的数字，单位是 KB/S，如果不限制就直接回车，建议不限制速度，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62405997-0059ec00-b5d7-11e9-8e3e-af05163717a0.jpg)](https://user-images.githubusercontent.com/52620310/62405997-0059ec00-b5d7-11e9-8e3e-af05163717a0.jpg)

然后会开始部署，到下图所示的位置，提示你下载文件，输入：y

[![img](https://user-images.githubusercontent.com/52620310/62405999-05b73680-b5d7-11e9-82ad-04028d5af096.jpg)](https://user-images.githubusercontent.com/52620310/62405999-05b73680-b5d7-11e9-82ad-04028d5af096.jpg)

然后就耐心等待一会儿安装，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62406003-0c45ae00-b5d7-11e9-9ccf-6d949a2e177e.jpg)](https://user-images.githubusercontent.com/52620310/62406003-0c45ae00-b5d7-11e9-9ccf-6d949a2e177e.jpg)

等安装完成之后就可以看到 SSR 账号 配置信息，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62406005-110a6200-b5d7-11e9-8d87-bbf262b22218.jpg)](https://user-images.githubusercontent.com/52620310/62406005-110a6200-b5d7-11e9-8d87-bbf262b22218.jpg)

按照上面的图片就可以看到设置的 SSR 账号信息，包括 IP、端口、密码、加密方式、协议插件、混淆插件，这些信息都需要填入对应的 SSR 客户端。

## 4、搬瓦工 搭建 BBR 加速

虽然 SSR 搭建好了，但是速度还不是很快，要搭建 BBR 才快，下面我们就说说怎么搭建 BBR。

BBR 是 Google 的一款 SSR 加速产品，使用下面的命令就可以实现 BBR 加速，只有 [搬瓦工](https://bwh88.net/aff.php?aff=54381&pid=57) 等少数 KVM VPS 才支持 BBR 加速，这也是我们推荐选择 搬瓦工 的原因。

在 xShell 连接端输入，如下命令，然后回车：

```
yum -y install wget
wget –no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
chmod +x bbr.sh
./bbr.sh
```

[![img](https://user-images.githubusercontent.com/52620310/62406006-18317000-b5d7-11e9-8146-b9b05d4240d7.jpg)](https://user-images.githubusercontent.com/52620310/62406006-18317000-b5d7-11e9-8146-b9b05d4240d7.jpg)

然后按任意键进行部署

[![img](https://user-images.githubusercontent.com/52620310/62406007-1c5d8d80-b5d7-11e9-822f-fd9ed195a88b.jpg)](https://user-images.githubusercontent.com/52620310/62406007-1c5d8d80-b5d7-11e9-822f-fd9ed195a88b.jpg)

然后需要等待命令执行，大约5分钟，如下图所示：

[![img](https://user-images.githubusercontent.com/52620310/62406009-22536e80-b5d7-11e9-826b-e1f1b0774db9.jpg)](https://user-images.githubusercontent.com/52620310/62406009-22536e80-b5d7-11e9-826b-e1f1b0774db9.jpg)

会在下面的图片过程中等待一会儿

[![img](https://user-images.githubusercontent.com/52620310/62406011-267f8c00-b5d7-11e9-8ac1-67599ff1facb.jpg)](https://user-images.githubusercontent.com/52620310/62406011-267f8c00-b5d7-11e9-8ac1-67599ff1facb.jpg)

最后完成后需要重启，根据提示输入：y，重启服务器即可生效

[![img](https://user-images.githubusercontent.com/52620310/62406015-2bdcd680-b5d7-11e9-9aec-fdf762a5f191.jpg)](https://user-images.githubusercontent.com/52620310/62406015-2bdcd680-b5d7-11e9-9aec-fdf762a5f191.jpg)

如果错过了重启步骤，直接输入重启命令命令：

```
reboot
```

[![img](https://user-images.githubusercontent.com/52620310/62406018-31d2b780-b5d7-11e9-819b-baa65e585c47.jpg)](https://user-images.githubusercontent.com/52620310/62406018-31d2b780-b5d7-11e9-819b-baa65e585c47.jpg)

然后耐心等待，待服务器重启后即可自动开启 SSR 加速。



## 5、客户端搭建ssr代理

各种客户端版本下载地址：[各版本SSR客户端官方下载地址](https://github.com/xiaoming2028/kexueshangwang/releases)

以Windows为例：

![ssr-pc-windows-config](https://user-images.githubusercontent.com/54033249/63205723-35883300-c0db-11e9-885b-985b140d48a4.png)

在状态栏右击shadowsocksR，在**系统代理模式**中选择**PAC模式**，再左击两次状态栏的图标打开编辑服务器界面，如上图所示，按照自己的服务器配置填充内容**，**保存即可~

**PAC模式**是指国内可以访问的站点直接访问，不能直接访问的再走shadowsocksR代理~

OK！一键脚本搭建shadowsocksR完毕！科学上网吧，兄弟！



## 6、搬瓦工 搭建 SSR 总结

以上就是美国 VPS 搬瓦工搭建 SSR 的教程，通过教可以轻松实现搬瓦工搭建 SSR，希望可以帮助需要使用搬瓦工搭建 SSR 的朋友。

[搬瓦工最好美国VPS](https://bwh88.net/aff.php?aff=54381&pid=57)，支持支付宝付款，欢迎购买注册。