作为技术开发人员，没少和代码打交道，也没少往机房跑。创新技术的不断更新迭代，最终明白了一个道理，专业的人做专业的事情，优秀的开源软件千千万，善于使用这些高能开源软件远比自己开发的高效 100 倍 1000 倍。

事实上，我曾使用过各种各样的方式去开发或搭建各种各样的网站和系统。从早年的 asp 到 php，从 windows 到 Linux，从 z-blog、FoosunCMS、dedecms 到 WordPress，从机房托管服务器到云服务普及应用，到今天，原先那些繁杂的工作都可以一步一步，化繁为简，不写代码、不跑机房，自动化技术让这些工作都可以一键在线完成。

而作为跨境电商中小卖家，仅仅依靠平台过活，似乎也变得越来越艰难了。事实上，确实有不少卖家遭遇到不公平，也变得越来越焦虑。因为有一堆要担心的事情，担心 listing 被恶意修改、担心被恶意跟买、担心 listing 被下架、担心滞销死库存、担心店铺被冻结关闭、担心海外税务合规问题甚至还担心川普心情好不好，关税加不加等等。也许正是因为这种担心与焦虑，独立自建站迎来了新的一波开店热潮。2019，亚马逊不再是跨境电商最火的话题，而是独立自建站。

老实说，搭建独立自建站的方法方式实在太多了，有免费的，有廉价的也有商业版的，有[共享主机](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215)、有独立主机还有 [vps 服务器](https://www.vultr.com/?ref=8169051-4F)，选择哪种方式，哪款主机，也只有真正试了才知道。

没错，上述的这些方法方式，我都亲身折腾过。从个人实际需求和建站方式来看，Shopify 虽然足够省事也更加容易上手，不过因为价格偏高以及无法完全掌控，它并非我的首选方式。而 Magento 虽然是开源软件，从电商专业性来看，首屈一指，但老实说，即便像我这样的专业技术人员折腾起 Magento，也有些费劲，作为电商卖家，把时间浪费在折腾技术上，有些方向性错误，所以，只能放弃 Magento。最后，选择了相对轻量级的 WordPress 开源程序，搭配 WooCommerce 电商插件来搭建独立自建站。

既然选择了 WordPress 开源程序，搭配 WooCommerce 电商插件来做，首先第一件事情就是为它找一个好鞍。选择了 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215) 主机，老实说，之前，我并不知道 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215) 是 WordPress 官方推荐的主机服务商，也只是从一些海外自媒体在主机对比评价上才了解到 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215)。因为 [Hostwinds](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215) 对正常运行时间、速度、安全性和客户服务支持的出色表现，Hostwinds 在 [Facebook](https://github.com/xiaoming2028/kexueshangwang/wiki) 上多项民意调查中成为获得最高排名的网络主机服务商。

于是，抱着试试看的态度，购买了 Hostwinds 主机，经过一段时间的体验与测试，体验了主机的速度性能情况、体验了他们的客户支持情况，甚至还体验了他们的退款速度情况，最后，我想我找到了一款性价比超高的主机。我承认起初我有点怀疑，但现在我也把网站迁移到了 Hostwinds 上。也算是给 WordPress 和 Woocommerce 找到了好鞍。关键一点是少花钱，把事情办好。下面，我们就一步一步，化繁为简。分享如何用 WooCommerce 在Hostwinds 主机上搭建独立自建站完整教程。



开始之前，我先介绍一下 WooCommerce 。简单来说，WooCommerce 是迄今为止最受欢迎的 WordPress 电子商务插件，互联网上所有的在线商店中，有 21% 是采用 WooCommerce 构建的。

![1-1](https://user-images.githubusercontent.com/54033249/63225486-12f13980-c203-11e9-930b-a8160a40dede.jpg)

如果你还没有 WordPress 网站，请先按照[这篇教程](https://github.com/xiaoming2028/kexueshangwang/wiki/996%E5%B7%A5%E4%BD%9C%E5%88%B6%EF%BC%9F%E4%B8%8D%E5%A6%82%E8%8A%B1%E7%82%B9%E6%97%B6%E9%97%B4%E5%AD%A6%E7%9F%A5%E8%AF%86%EF%BC%81%E6%95%99%E4%BD%A0%E5%A6%82%E4%BD%95%E7%94%A8WordPress%E6%90%AD%E5%BB%BA%E4%B8%93%E4%B8%9A%E7%BD%91%E7%AB%99)创建一个，整个过程非常容易只要 60 分钟。

- 从技术上讲，WooCommerce 是一个 WordPress 插件，与任何其他插件一样，需要安装和激活才能运行；
- 它是免费和开源的，你不需要任何许可证，也不必支付任何费用；
- 它是最受欢迎，也是功能最丰富的 WordPress 电子商务插件；
- 配置过程非常简单，通常只需一个小时就能完成；
- 它适用于 WordPress 网站上的任何主题，你不需要放弃当前的网站设计。

我可以将上面的列表继续加长，但最重要的是，为了使用 WordPress 构建高质量的电子商务网站，WooCommerce 几乎为你提供了所需的一切。

 

## WooCommerce可以用来卖什么

答案有很多，例如：

- 数字产品，软件、下载、电子书等等
- 实物产品
- 在线或线下服务
- 在线预订
- 订阅服务
- 其他人的产品 —— 作为联盟营销人员
- 你能想到的其他产品

换句话说，你可以通过网站来赚钱。WooCommerce 允许你出售任何可以分配价格的东西，任何人都可以免费使用。

 

> #### 启动 WooCommerce 商店的5个步骤
>
> 1、创建一个 WordPress 网站
>
> 2、安装 WooCommerce 插件
>
> 3、添加产品
>
> 4、选择主题
>
> 5、扩展功能

 

## 1、创建一个WordPress网站

前文已经说过，WooCommerce 是 WordPress 的一个插件，所以为了创建成功的在线商店，你首先需要拥有一个 WordPress 网站。不要担心，创建 WordPress 网站非常容易，这篇教程将一步一步指导你完成整个过程：

[Hostwinds云主机限时五折优惠链接](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215)

[怎样使用Hostwinds快速搭建一个WordPress网站](https://github.com/xiaoming2028/kexueshangwang/wiki/996%E5%B7%A5%E4%BD%9C%E5%88%B6%EF%BC%9F%E4%B8%8D%E5%A6%82%E8%8A%B1%E7%82%B9%E6%97%B6%E9%97%B4%E5%AD%A6%E7%9F%A5%E8%AF%86%EF%BC%81%E6%95%99%E4%BD%A0%E5%A6%82%E4%BD%95%E7%94%A8WordPress%E6%90%AD%E5%BB%BA%E4%B8%93%E4%B8%9A%E7%BD%91%E7%AB%99)



## 2、安装WooCommerce插件

与所有的插件一样，打开 **Dashboard**，导航到 **Plugins** → **Install New** 菜单，在搜索字段中输入 WooCommerce，你会看到 WooCommerce 是第一个搜索结果：

![2](https://user-images.githubusercontent.com/54033249/63225488-17b5ed80-c203-11e9-816a-50d1fd4126fe.jpg)

只需点击插件旁边的 **Install Now** 按钮即可，几秒钟后，按钮上的文字将变为 **Active**，继续点击。

![3](https://user-images.githubusercontent.com/54033249/63225490-1ab0de00-c203-11e9-8828-058546f2dbae.jpg)

在这个阶段，你将看到 WooCommerce 的设置向导，它可以帮助你完成所有事情。在线商店是一种特殊的网站，需要一些特定页面才能正常运行，WooCommerce 向导的第一步就是为你创建这些页面：

- Shop：这是用于展示产品的页面
- Cart：这是购物车，客户可以在结帐前调整订单
- Checkout：这是客户选择收货方式，并完成结账的地方
- My Account：一种针对注册客户的页面，他们可以在这里查看订单，并管理其他的详细信息

 

#### 2.1、商店设置

你将在这里设置商店的区域位置，通过几个参数定义你的业务来源：

![4](https://user-images.githubusercontent.com/54033249/63225495-1edcfb80-c203-11e9-8b80-aa0daa88a2b2.jpg)

完成后，点击 **Let’s go!** 按钮。

 

#### 2.2、付款方式

能够接受在线付款是任何电子商务网站的核心，WooCommerce 提供了很多可用的解决方案，最初只向你提供两种：

![5](https://user-images.githubusercontent.com/54033249/63225497-23a1af80-c203-11e9-808a-5e4d3eb83087.jpg)

最受欢迎的 PayPal 位于顶部，下面是可用的线下支付选项，你可以根据自身需要勾选相应的复选框即可。当然，你还可以选择其他更丰富的付款方式（例如 Stripe 和 Square），WooCommerce 设置面板中的更多选项将在稍后提供。

注意：要使在线支付正常运行，你需要单独注册 Stripe 或 Square，WooCommerce 中的设置仅允许将你现有的 PayPal 或 Stripe 账户与电子商务网站进行集成。

完成后，点击 **Continue** 按钮进入下一步。

 

#### 3.3、官方推荐

这里是 WooCommerce 推荐的主题和插件：

![6](https://user-images.githubusercontent.com/54033249/63225498-27353680-c203-11e9-8a1c-2699f22401ca.jpg)

- Storefront 是 WooCommerce 的官方主题，默认版本是免费的，基本上可以满足一个新商店的建设需求；
- MailChimp 是一个订阅插件，客户提交电子邮件并订阅你的网站新闻，然后你可以向他们推送各种信息。

我建议你全部勾选，然后继续点击 **Continue** 按钮。

 

#### 2.4、Jetpack

Jetpack 是使用人数最多的 SEO 插件之一，但大部分都是被捆绑安装的，这款插件过于庞大和臃肿，我建议你跳过这一步，点击屏幕底部的 **Skip this step** 链接：

![7](https://user-images.githubusercontent.com/54033249/63225500-2a302700-c203-11e9-9e56-d646ff3df7d0.jpg)


#### 2.5、一切就绪

终于到了最后一步，你的网站设置已经完成，现在拥有一个空白的电子商务网站： 

![8](https://user-images.githubusercontent.com/54033249/63225503-2e5c4480-c203-11e9-9223-59e156d33a21.jpg)

点击左下角的 **Visit Dashboard** 按钮返回到后台，接下来我们开始添加产品。

 

## 3、添加商品

为了使商店能够正常运营，你需要添加一些商品（或服务、下载，以及任何其他你想出售的东西）。

转到 **Dashboard**，然后点击菜单 **Products** → **Add New** 。页面上方可能会有一些提示消息，我们先不予理会，主要关注下方的内容编辑模块：

![9](https://user-images.githubusercontent.com/54033249/63225504-31573500-c203-11e9-8f92-3a3e90e38e17.jpg)

下面是每个部分的说明：

1、产品名称。

2、产品说明：在这里录入详细的产品信息，除了文本之外，还可以放置图像、表格、视频，以及其他你能想到的媒体。

3、产品数据：在这里设置要添加的产品类型，物理还是数字产品，另外还能添加各种参数：

- General：设置正常价格和促销价格
- Inventory：设置库存信息
- Shipping：设置重量、尺寸和运输成本
- Linked Products：非常适合设置追加销售和交叉销售，例如：购买此产品的客户也购买了…
- Attributes：设置自定义属性，例如衣服的颜色和尺码
- Advanced：其他设置，不是必需的。

4、简短说明：这是显示在产品名称下面的文本，最适合作为产品的简短摘要。

5、产品类别：将类似的产品作为一个类别，例如上衣、裤子、鞋子等等。

6、产品标签：另一种帮助你组织产品的方法，例如潮流时尚、青春靓丽。

7、产品图片：产品的主图。

8、产品图库：产品的其他图片，一般用于轮播展示。

 

完成上述所有操作之后，点击页面右侧蓝色的 **Publish** 按钮，你的第一个产品就添加完成了。接下来，按照上述步骤添加其他的产品，然后点击菜单 **Products** → **All Products**，页面看起来应该是这样的：

![10](https://user-images.githubusercontent.com/54033249/63225505-34eabc00-c203-11e9-9ada-02ff2a6ba4ff.jpg)



## 4、选择主题

如果数据库中没有任何产品，那你无法直观地查看商店的各个页面，也无法确保一切正常。按照上述步骤，现在你应该添加了大部分产品，接下来我们从纯粹的视觉角度谈谈优化策略。

 

#### WooCommerce vs. 你当前的主题

默认情况下，WooCommerce 适用于任何 WordPress 主题。这是一个好消息，特别是如果你已经选择了自己的设计，并打算一直坚持下去。或者，你可以使用 WooCommerce 优化的主题，它们带有预设的样式，使所有页面元素看起来都很棒。

这是我的建议： 

- 如果你已经拥有一个独一无二的 WordPress 主题，那就继续使用，只需确保它在 WooCommerce 上看起来不错；
- 如果没有，那就挑选一个专为 WooCommerce 优化的新主题。 

官方的 WooCommerce 主题称为 Storefront，默认版本是免费的，足以支撑你的现有业务。 

![11](https://user-images.githubusercontent.com/54033249/63225506-3916d980-c203-11e9-940f-42ff326159fe.jpg)

或者，你可以访问 ThemeForest 的电子商务部分，这是网上最高级的 WordPress 主题目录。

![12](https://user-images.githubusercontent.com/54033249/63225510-3ddb8d80-c203-11e9-9d1f-39b68cb93f55.jpg)

不管是使用当前主题，还是专为WooCommerce优化的主题，你需要做的就是确保各个页面看起来不错。

 

#### 电子商务网站的设计规则

在进入细节之前，我们先讨论一些重要准则，主要是：什么让电子商务网站的设计变得更好？

下面是最重要的参数：

- 确保页面设计和功能足够清晰，不得以任何方式混淆，一个迷茫的访客不会购买任何东西；
- 中心内容需要迅速吸引访客的注意，这个地方应该用于展示产品；
- 侧边栏能够轻松调整，并且还要为某些页面完全禁用侧边栏；
- 响应式和移动优化：研究表明，互联网上大约有 80% 的用户拥有智能手机；根据另一项研究， 61% 的移动访客会立即离开。如果你的移动浏览体验不好，就会失去这些潜在客户；
- 良好的导航结构：你要提供一个清晰的菜单，以便访客能够找到他们正在寻找的任何页面。

考虑到上述情况，你可以对各个页面执行一些针对性的操作：

**1、商店页面**

这是你的主要产品列表页面，页面地址应该类似于：https://www.xiaobei.com/shop/。

这是一个标准的 WordPress 页面，你可以通过 **Dashboard** → **Pages** 进行编辑，现在需要做以下事情：

- 继续添加其他产品，鼓励访客在网站上购物；
- 决定是否要在页面上添加侧边栏，这是通过主题的页面模板完成的，但需要购买 Storefront Powerpack 扩展，包含大量丰富的功能，例如页面布局、色彩调整，以及多种风格等等。你现在可以不必购买。

在 Storefront 主题中，你的商店页面看起来应该像这样：

![14](https://user-images.githubusercontent.com/54033249/63225511-42a04180-c203-11e9-8861-1d43cb112823.jpg)

正如你所看到的，漂亮的产品图像是关键，这是你应该做好的第一件事情。

**2、单个产品页面**

要查看这些内容，请点击商店页面中的任意一个产品。

如果你使用的是高质量主题，那么应该不会在这里遇到任何困难。基本上，你唯一能做的就是调整产品描述，以确保所有内容都符合视觉效果。

![15](https://user-images.githubusercontent.com/54033249/63225513-46cc5f00-c203-11e9-8356-b88007522ce9.jpg)

**3、购物车**

另一个可以通过 **Dashboard** → **Pages** 调整的关键页面，除了结账功能之外，你不应该在这里为买家提供太多的其他选项。

在产品页面中，将其添加到购物车里面，然后购物车页面看起来应该是这样的：

![16](https://user-images.githubusercontent.com/54033249/63225515-4af87c80-c203-11e9-99af-7a0bab87db89.jpg)

**4、结账**

这是买家完成订单并付款的地方，你不应该对此进行任何调整：

![17](https://user-images.githubusercontent.com/54033249/63225519-50ee5d80-c203-11e9-8f83-28e9c8cb8533.jpg)

在这个阶段，你基本上已经调整好了商店设计，接下来我们看看扩展功能。

 

## 5、扩展功能

WooCommerce 如此受欢迎的另一个重要原因，就是你可以获得数百个可用的扩展和插件，我们已经精选出了一些最好的组件，你可以立即开始使用：

#### WooCommerce官方插件

Payment：这些插件允许你在标准的 PayPal 之上接受更多付款方式；

Shipping：自动与 UPS 或 FedEx 等公司的官方运费相整合；

Accounting：将你的 WooCommerce 商店与财务工具相集成；

WooCommerce Bookings：允许客户预订服务；

WooCommerce Subscriptions：客户订购你的产品或服务，并且每周、每月或每年支付费用；

EU VAT Number：适合在欧盟开展业务的卖家；

TaxJar：自动处理销售税。

 

#### 第三方插件

Yoast SEO：改善整个网站的 SEO；

Yoast WooCommerce SEO：改善电子商务领域的 SEO；

WooCommerce Multilingual.：运行一个多语言的 WooCommerce 网站；

Contact Form 7：让访客直接与你联系；

UpdraftPlus：备份网站的所有内容，包括产品和其他数据；

Social Share Buttons by GetSocial：让买家通过社交媒体分享你的产品；

MonsterInsights：将你的网站与 Google Analytics 集成；

iThemes Security：增加网站的安全性；

W3 Total Cache：通过缓存加速你的网站；

 

## 总结

正如你所看到的，使用 WordPress 创建自己的电子商务网站并不困难。对于新手而言，通常最多只需一两个下午就能完成上述所有步骤。

要是放在几年前，你可能需要雇佣几名开发人员，并且花费数万元才能获得类似的东西，但现在你可以自己掌控一切！初期成本甚至不超过 $10。

最后，为了帮助你完成所有任务，这里有一份完整的执行清单：



### 在开始之前

- 创建一个 WordPress 网站



### 安装WooCommerce

- 安装并激活 WooCommerce 插件
- 完成 WooCommerce 设置向导



### 商品

- 将大部分（或全部）商品添加到商店里面



### 设计

- 选择正确的 WordPress 主题
- 调整商店页面
- 调整单个产品页面
- 调整购物车页面
- 调整结账页面



### 扩展

- 安装需要使用的支付网关
- 考虑一些物流扩展
- 考虑财务扩展
- 浏览其他扩展程序



### 插件 

- Yoast SEO
- Yoast WooCommerce SEO
- WooCommerce Multilingual
- Contact Form 7
- UpdraftPlus
- Social Share Buttons by GetSocial
- MonsterInsights
- iThemes Security
- W3 Total Cache

 

准备好创建 WooCommerce 电子商务网站吗？我们推荐使用 Hostwinds，这是我们见过的最快的 WordPress 托管商，只需要点击几个按钮，你就可以在几分钟内部署好一个全新的 WooCommerce 在线商店。[Hostwinds限时五折优惠链接](https://affiliates.hostwinds.com/hostwinds.php?id=7011&url=1215)


