title: 凹凸技术揭秘·羚珑页面可视化·成长蜕变之路
subtitle: 羚珑智能页面设计引擎是一款全场景通用页面可视化搭建解决方案，专注于泛零售领域的设计
cover: https://img10.360buyimg.com/ling/jfs/t1/169901/19/224/248690/5fed91cdE19a056c9/e1710336e7d35db1.jpg
categories: 凹凸
tags:
  - 凹凸
author:
  nick: Atom
  github_name: youing
date: 2020-12-31 12:00:00
---


## 前言

京东零售集团 · 用户体验设计部打造的「羚珑智能设计平台」于 2019 年 5 月为内部运营及商家推出了智能页面设计工具，羚珑智能页面设计是一款在线可视化页面搭建平台，拥有在线搭建 PC、H5、小程序等多平台页面能力，覆盖频道页、活动页、店铺页、滑屏宣传页、答题类、互动游戏类、小程序等多个应用场景，为商家、运营人员提供在线服务，让不懂设计、不懂代码的用户也可以一键上线页面。


基于「Taro」强大的多端能力，能够实现一次搭建，生成 H5、小程序、RN等跨端应用，极大地解决重复开发的问题，提高开发效率。



## 聊聊羚珑智能页面设计的历史


### 业务中求突破

在 2017 年以前，京东线上大量的 PC 频道页都是通过手工开发的，开发周期非常长，当时公司内部也有一个 CMS 系统，前端开发完的页面，需要通过这个系统进行发布上线。整个页面的开发依赖这个系统，并且需要在线上完成这些工作。另外还要录入一些数据坑位，才能预览到页面。当时为了解决前端的开发效率，我们把线上开发及数据坑位录入的工作，搬到本地通过一系列自研工具完成。完全颠覆了整个频道页的开发方式，整体的开发思路沿用至今。




日积月累，我们手上已经开发了非常多的频道页，而且到后面发现，很多页面都非常相似，只是一些样式上的差异。当发现工作重复的时候，应该是造车的时候了，可以让我们跑得更快。




## 搭建平台雏形

羚珑智能页面设计的前身，它只能说是一个页面拼装系统，有一位频道运营的同事找过来，希望能快速开发一个页面，问：“能不能把线上的某几页面中的不同楼层拼在一起，快速上线几个页面”，很显然对于不懂技术的人来说似乎非常简单的事情，但是对于我们开发来说，并非如此简单。我们尝试把不同页面的代码找出来，快速开发一个新的页面，发现很多问题，如样式冲突、脚本冲突等一系列问题。




于是后面我们对已有的页面，进行楼层级的改造，改造后的楼层，能够独立运行，并且不同的代码及样式只作用于当前楼层，这样，不同楼层组合出来的页面，能够正常显示。




经过改造后的公共楼层，为了让用户能够自由组合楼层去拼装出一个页面，我们搭建了一个在线可视化平台，把所有公共楼层以列表形式展示出来，支持通过拖拽形式组装页面，支持一些常规的属性配置，如公共头部、颜色等，基本上能满足部分用户诉求。




![拼装系统](https://img11.360buyimg.com/ling/s750x1000_jfs/t1/170110/24/87/3823588/5fec784aE68ae6b98/bca162d1df94da3d.png)




## 真正的可视化之路




### 页面拼装系统的痛点




页面拼装系统，它主要解决了开发及用户的一小部分诉求，离真正的可视化之路，还很远。很快拼装系统暴露了它一些问题：




1. 在技术层面，由于楼层的粒颗度不够小，要做一些布局上的调整，需要调整到代码才能支持，缺乏一定的灵活性。以及使用过时的技术栈 jQuery，后期维护成本也非常高。
2. 在用户运营方面，在我们的平台上不支持根据真实的数据预览效果，系统只是完成了页面框架搭建的事情。
3. 在数据录入方面，还是难以摆脱前面提及的 CMS 系统，用户需要回到 CMS 系统上面填写真实的素材，所以存在不同系统之间的切换。

### 可视化编辑器设计思路

**给合拼装系统的一些问题，我们开始重新设计一款真正基于组件化的页面搭建平台。**

羚珑智能页面可视化编辑器，包括几个基本核心要素：组件库、设计器、属性编辑。

1. 组件库分为基础组件和业务组件，由于 PC 页面比较复杂，有布局的概念，所以我们需要设计一套布局系统，借鉴于业界优秀的栅格设计思想，再结合我们页面的实际情况，完成了页面的框架与基础组件设计。业务组件穷举了大量线上页面，把常用的组件进行组件化改造，并且支持灵活的属性配置。
2. 设计器负责组件拖拽、组件加载、渲染逻辑、组件树操作、动态属性注入等功能。通过高阶组件的方式，能帮助我们轻松给组件添加一些特定功能。

3. 属性编辑，组件每个属性都对应着一个类型，那么它属性数据编辑的方式也不一样。我们设计的类型基本覆盖所有组件。另外还设计了一套条件规则，让属性之间能够联动显示。





实际上要完成一个高可用的可视化编辑器，需要了解的知识点与细节非常之多，这里不做详细展开介绍。




经过近一年的沉淀，频道页开发已经从人工开发，全面转型为可视化，目前京东线上大部分频道页都是通过自助搭建方式完成上线。




![PC搭建平台](https://img13.360buyimg.com/ling/s750x1000_jfs/t1/166213/25/65/3787254/5fec7849E6df0bbe6/24aded053d6985b3.png)




## 编辑器全面升级

2019年初，借鉴于过去在公司内可视化领域取得了小有成绩，我们产品方向重新定位为聚焦商家在线上经营过程中的页面设计需求，希望通过降低页面上线门槛，从而提高商家、运营人员上线页面的效率，因此，对页面可视化编辑器进行了一次迁往移动端的升级。整个视觉风格及交互方式，都进行了全面升级，去除了复杂的布局，用户使用起来更加便捷。

![编辑器全面升级](https://img11.360buyimg.com/ling/s750x1000_jfs/t1/160193/30/714/2214002/5fec783aEdea7838a/11b7026b6c74a29a.png)


### 组件库升级
我们把组件库升级为一个全新的平台「Quark」，它作为一个独立的设计资产平台。为编辑器提供组件、图标库等物料，目前已经沉淀的官方组件有50多个，200多种布局形态，能够满足大部分页面需求。同时还支持公司内部其他研发团队开发自己的组件，接入到我们的可视化平台中，通过我们的上线页面服务上线。

![组件库升级](https://img30.360buyimg.com/ling/s750x1000_jfs/t1/158787/20/813/555262/5fec7809Ee62a191a/643072dfed37656c.png)


### 属性面板升级

**配置体验影响用户搭建效率：** 用户在日常使用编辑器时，需通过更改组件配置项以满足页面个性化需求。我们发现，组件配置项的面板结构复杂、组件配置项理解成本高、操作方式不符合用户习惯等体验问题已经严重影响了用户的配置体验与搭建效率。

**旧版组件配置项面板：** 分类以「功能」、「样式」、「数据」做区分，用户理解成本高，经常出现同一配置项出现在多个分区的情况，极大增加了用户的操作成本。

**新版组件配置项面板：** 重新定义了面板结构规范，从用户配置操作行为区分，划分为「组件名称」、「组件布局」、「数据录入」、「样式配置」与「楼层配置」5大区域，不仅利于用户理解，缩短了用户的操作路径，对于产品本身而言，清晰的布局划分与功能定义还提效了新增组件的配置项拆解工作。

![属性面板升级](https://img10.360buyimg.com/ling/s750x1000_jfs/t1/166568/29/89/1458453/5fec7827E71adc2b2/90a37d8d32816fe4.png)


> 改版前 v.s 改版后 配置项面板整体结构分区、配置项元件化示意





### 元素编辑器

当我们的官方组件无法满足用户个性化需求的时候，我们思考着能否为用户提供一种自定义组件的能力，所以元素编辑器应运而生。它提供了一个自定义画板的能力，用户可以自由拖拽一些基础元素，如文本、图片、图形等，添加上一些自定义事件和动画，一个生动的的自定义组件，便能轻松完成。

![元素编辑器](https://img10.360buyimg.com/ling/s750x1000_jfs/t1/165613/1/82/2179662/5fec783aE63fe722a/5e4b18a57c74b1d1.png)


### 设计资产沉淀

设计师沉淀了上千套模板提供给用户使用，这些模板全部接入「羚珑」智能图片设计能力，用户能够直接在线修改图片素材内容，轻松实现高质量的页面。另外我们的模板还支持智能配色，用户可以根据配色方案进行页面整体换肤。

![设计资产沉淀](https://img10.360buyimg.com/ling/s750x1000_jfs/t1/163613/28/95/1761265/5fec782eE03d7122b/0e10b41ef35eb47e.png)


### 羚珑智能作图

为解决用户做图的痛点，羚珑页面编辑器与羚珑图片编辑器深度结合，为用户提供在线图片编辑的能力，用户无须使用一些做图软件，便能在线上完成图片编辑。

![羚珑智能作图](https://img20.360buyimg.com/ling/s750x1000_jfs/t1/169492/31/65/2387056/5fec783fE8894d823/532f9966c841dc4f.png)

## 多应用场景适配

### 活动场景

我们的活动页是如何完美适配移动端和桌面端的呢？

一个移动端页面要适配桌面端，通常的做法是通过响应式的手段来实现，这种方式比较简单粗暴，但是效果其实并不好，例如移动端的首焦图，如果在桌面端等比放大，那将会占满首屏，用户体验极差。

**所以我们采取了一系列的转换规则来实现：**

**举个例子**

PC端的内容其实是跟移动端的内容做了对应关系。并且根据端的特性做了一系列通用的变换规则。比如秒杀商品中秒杀倒计时与商品在移动端为上下布局，而在PC端则为左右布局，商品单元在移动端为一排2个，在PC端则增加为一排4个。

![秒杀商品](https://img14.360buyimg.com/ling/s750x1000_jfs/t1/158235/35/790/122652/5fec77f8Ef65c00c2/8c8ed6f25a3fbeb2.png)


#### **转化的规则是什么？**

**拉伸：** 在布局不发生改变、内容没有增减的情况下进行拉伸，如广告组模块：

![拉伸](https://img10.360buyimg.com/ling/s750x1000_jfs/t1/160233/37/722/11993/5fec77f2E61cd614a/7351ac83b083f9f3.png)

**文本：** 文本内容较重要时我们会做无增减的拉伸，当空间位置受限，同时文本内容又不是非常关键的信息时会选择文本截断的方式进行拉伸。

![文本](https://img11.360buyimg.com/ling/s750x1000_jfs/t1/170401/28/82/28222/5fec77f2Ed72fd46d/94f0e94e98685489.png)

**图片：** 一般来说细节图去做等比拉伸，这样尽最大可能的保证两端效果的一致性。

![图片](https://img14.360buyimg.com/ling/s750x1000_jfs/t1/155440/31/12744/14668/5fec77f2Ee34a3b32/494c2ca0a6dcdb2a.png)

由于移动端宽高比相比 PC 端要小很多，为了保证在大屏上的效果不至于出现“霸屏”的情况，还会有取舍的进行裁切。

![图片](https://img11.360buyimg.com/ling/s750x1000_jfs/t1/163211/12/79/11317/5fec77f2E3b852da6/f4ab981b9a652a82.png)


**模块：** 移动端通常会将一个楼层划分为一个模块，对应到PC端会将模块在横向进行拉伸。

![模块](https://img12.360buyimg.com/ling/s750x1000_jfs/t1/160872/35/171/12155/5fec77f2E2d4d9f6b/351f060e291adc83.png)


**布局改变：** 布局发生改变时需要将元素进行重排

如头图banner模块，如果采取等比拉伸的策略会导致头图特别高，在 PC 端影响第一屏的页面效率，如果采取裁切的形式将会影响图片的展示效果，所以采取图片内元素重排的形式进行变化。

![布局改变](https://img30.360buyimg.com/ling/s750x1000_jfs/t1/164145/18/95/12132/5fec77f2E74633ef4/d7ca1a971853c2a8.png)


锚点导航模块在移动端是横向的导航，上滑页面时会吸附到页面的顶部，而在 PC 端我们一般会吸附在页面的侧边固定位置。

![锚点导航](https://img10.360buyimg.com/ling/s750x1000_jfs/t1/156172/7/3505/23818/5fec77f2E51d914af/ba59d3778d67e3ac.png)

**内容增减：** 单元重复展示模块一般会用内容增加和删减的形式来处理，比如商品模块在 PC 端横向空间比较大的情况下会多展示单元格数。

![内容增减](https://img30.360buyimg.com/ling/s750x1000_jfs/t1/154677/21/12655/11493/5fec77f2Eebdd6893/8ab0862a435eb11f.png)

结合这些转换规则，能让用户只要搭建一次页面，便能快速同时生成两端活动页，投放到移动、PC端平台，节省运营成本。




### 互动营销场景

过去商家想做一个互动类的页面，基本上是很难实现的。有着成本高、开发周期长等问题。互动营销场景为了解决这一系列痛点，把互动玩法进行组件拆解，再通过页面可视化平台进行配置上线。原来一个互动玩法从方案到上线大概需要一个月左右，现在通过可视化搭建方式只需要十分钟，大大提高了效率。

![互动营销场景](https://img10.360buyimg.com/ling/s750x1000_jfs/t1/167014/4/76/563712/5fec7854E6100d045/c8f6510fe866f6ec.jpg)

![互动营销场景2](https://img14.360buyimg.com/ling/s750x1000_jfs/t1/160707/11/157/2273839/5fec783bE449f1dc3/f7ae17f018f0cc32.png)




### 小程序场景
我们是京东内部首个小程序可视化搭建平台，借助「Taro」的跨端能力，我们平台天然具备了发布跨端小程序页面的能力，结合京东「开普勒平台」的黄金流程，快速产生一套完整的电商小程序代码。支持发布微信、百度等多个小程序平台，完成「九阳」、「戴森」等多个商家小程序上线。

![小程序场景](https://img20.360buyimg.com/ling/s750x1000_jfs/t1/158307/13/789/1514777/5fec7828E8dd47c30/6d0b4357ae51e416.png)

![小程序场景](https://img13.360buyimg.com/ling/s750x1000_jfs/t1/168374/11/68/2513244/5fec7840E6155dd93/da410c83ae3723f6.png)





### 店铺场景

**店铺场景下，我们实现了三个重要的应用场景：**

1. 店铺首页，为商家提供店铺首页搭建的能力，并实现了把设计结果与「京东智铺」的素材打通，满足商家店铺首页装修诉求。

![店铺首页](https://img12.360buyimg.com/ling/s750x1000_jfs/t1/166043/39/81/1376885/5fec7824Eb14b74ef/34860ae1d9827ab9.png)


2. 店铺推广，一个基于元素编辑器扩展的场景，提供滑屏类页面活动搭建的能力，提供了极具个性化宣传页能力。

![店铺推广](https://img14.360buyimg.com/ling/s750x1000_jfs/t1/170202/22/74/2361557/5fec783fE708b67ef/d1fdd46ade9f1307.png)

3. 店铺购物小程序，以中心化小程序的形式为商家提供私域流量工具，提供丰富的营销工具，如抽奖、关注有礼、全景馆等多种玩法。

![店铺购物小程序](https://img12.360buyimg.com/ling/s750x1000_jfs/t1/157837/23/780/4932981/5fec784eEc67b52a8/df9f96319cabe196.png)


## 编辑器积木化

### 为何要做编辑器积木化？

1. 随着场景越来越多，编辑器的代码逻辑也变得非常复杂，不同场景都有一些特殊的功能逻辑，每个场景又分为模板搭建端和用户使用端，在编辑器中的表现形式不同，而且编辑器与平台的业务逻辑强耦合。
2. 公司内部很多平台，都有可视化搭建的诉求，如果重新开发一个可视化编辑器，少则至少需要半年时间。如果直接复用我们的编辑器积木，将会大大提升效率。也减少公司内部重复造车的情况。
3. 我们编辑器的研发团队人力有限，不能及时满足各场景的需求，扩展性差。
4. 改动一个小小的功能，整个编辑器都需要发布，如果出问题，所有场景都受影响。
5. 编辑器的功能越来越多，体积也随之上升，时间久了，整个编辑器变得非常臃肿。

**为了解决这些问题，我们进行了一次编辑器的架构全面升级**

### 基于配置的插件化架构

**我们将编辑器划分为：主设计器 + 插槽区域，分别用两种颜色表示：**

![主设计器](https://img14.360buyimg.com/ling/s750x1000_jfs/t1/171119/37/73/2148003/5fec7839Ed40d983b/bdbd8c70efe628b9.png)


1. 主设计器：负责编辑器核心逻辑，配置文件解析、插件加载器、组件加载、全局状态管理等；
2. 插槽区域：编辑器会预留几个主插槽位置用来加载插件功能；

**我们大致来了解一下整个编辑器的工作流程：**

1. 编辑器读取配置文件，配置文件是对整个编辑器的描述，包括所有插件的配置。
2. 编辑器中提供几个核心位置以插槽的形式，读取配置文件中的插件。
3. 编辑器的功能抽离成一个个插件文件，通过异步的形式进行加载，这样做的好处是可以按需加载、逻辑解耦、有利于提高系统的扩展性。
4. 每个插件加载可以动态注入到编辑器应用中，同时它能够共享编辑器的状态，完成插件之间通讯以及调用编辑器的数据和方法。
5. 编辑器实际上只做一件事情，就是页面描述的生成，其他业务逻辑交业务侧做，这样的好处是能使编辑器完全解耦独立运行。只需要做一些与编辑器、插件的通信接口，就能快速使用起来。
6. 各使用场景只需要关注自己的编辑器应用配置即可，互相不影响，包括插件个性化升级。




### 对外赋能应用

目前，我们的编辑器积木化解决方案已经应用在京东内部其他平台当中，如京东数科江湖平台、京东ME行业版平台等，作为页面设计引擎助力各平台的商业化快速发展。

![对外赋能应用](https://img20.360buyimg.com/ling/s750x1000_jfs/t1/162059/21/94/2477192/5fec7840Ecab477c6/ae92c6c63e8fad8b.png)





## 结语
目前为止，业界有很多优秀的页面可视化产品，为何一直没有尽头，一直有新的平台出现，但都没有最终极的解决方案，那是因为没有真正的「银弹」，只有适应业务发展的产品，才是最适合的。未来我们将会往智能化页面设计的方向努力，必然会擦出新的火花，敬请期待！







## 参考
- [羚珑组件智能编辑新体验](https://jelly.jd.com/article/5f72fe7baef0130151aec36b)
- [揭秘羚珑页面-多端智能转换](https://jelly.jd.com/article/5fd5e80f5fd2b30146b948eb)
- [智能页面引擎全新亮相 页面设计中台初长成——架构篇](https://jelly.jd.com/article/5f01fc10c44cb5014971ca1b)

