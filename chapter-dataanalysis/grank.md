#### 2.2 Grank 篇

本篇以 GitHub 数据为基础，按照设定方法进行采集、聚类和分析开源生态的状态。本篇作为《中国开源调查报告》的一部分，提供了另外一种从数据的视角来观察中国开源项目发展的方法。

Grank 是本报告制定的一个指数，用于综合评估一个开源项目、开源组织的健康程度。

**Grank 模型介绍**

我们认为，一个健康的开源项目应该体现为以下两个方面：

* 项目的活跃度趋势
* 项目的社区化（去中心化）程度

而这两个方面分别有多个因素组成：

**活跃度和活跃度趋势**

项目的活跃度，我们定义为项目的提交数、 拉取请求数和贡献者数（其它数据，如代码行数、文件数、issue 数、 fork 数、star 数，要么是权重相对低得多，要么是代表意义不够确定，此处忽略不计入模型）。

但是，对于不同的项目，其横向比较其活跃度，或有不同的活跃度形态，或不具备可比性。很难说一个项目比另外一个项目的提交数高，而拉取请求（PR）数低代表的确切含义。因此我们不认为对不同项目的这些数据进行绝对值的比较有太多的科学意义。

所以，我们认为一个项目本身的活跃度变化的趋势和幅度，会更有项目间比较的意义。

如果以三维空间来描述一个项目的活跃度，以提交数、拉取请求数、贡献者数为三维，可以确定在某个时间点某个项目的坐标，那么计算一段时间内，该坐标点的移动轨迹和速率，可以真实的反映该项目的活跃度趋势。

考虑到按周工作的作息时间的普遍影响，我们以一个工作周作为一个时间采样点，然后计算连续的几周内该坐标的移动速率。这反映了该项目的发展速度。

**社区化程度**

开源诞生于社区，繁荣于社区，根植于社区，虽然现在大型组织、商业公司也纷纷投身于开源生态，但是我们认为，开源项目的生命力仍然在于社区。我们并不否认机构、商业公司对开源的巨大贡献和影响力，但是如果一个开源项目变成了一家或几家大企业的私人游戏，其必然失去开源项目的生命力，它或许会在商业上取得成功，但是那个成功不是开源项目的成功模式。

因此，我们认为需要有一个评估开源项目的社区化（去中心化）程度的指标。项目（尤其是软件项目）的一个重要属性是开发人员的社区化身份，因此，我们以实际向项目贡献了代码的人员的社区化离散程度来评估项目的社区化程度。

每个参与项目开发的人员均有其身份属性，这个身份可能是企业雇佣身份，也可能是社区志愿者身份。我们通过对项目的提交中的提交者数据进行收集，然后根据开发人员的身份信息、邮件后缀等依优先级来判断其所属身份。然后对这些信息进行聚类，以一个离散评估模型来评估该数据集的离散程度。

虽然项目越中心化，其发展风险越高，但是，并不是社区化程度越高的项目就越健康，过于离散的项目也容易出现项目分裂、迭代缓慢等问题。这显然是存在一个适当的区域。

通过上述两个指数，我们可以对项目进行象限划分，以“项目活跃度”和“社区化程度”为两个象限轴。

**Grank 项目**

根据如上的方法论，我们（Linux 中国）发起了一个开源项目，用于提供分析工具，该工具由 Linux 中国核心成员 Bestony 创建，并贡献给社区，以期进一步完善。

> 项目地址： [https://github.com/LCTT/Grank](https://github.com/LCTT/Grank)

**数据采集方法**

我们采用 GitHub 提供的 API 进行数据采集，数据采集范围为国内主要互联网公司在 GitHub 上的重要（活跃）项目（以下列表排名不分先后）：

* 阿里巴巴（Ant Design、蚂蚁金服、Angular Developers、淘宝、天猫前端、eggjs）
* 华为（华为 Hadoop）
* 腾讯（AlloyTeam、tarscloud）
* 百度（FEX、EFE、前端）
* 饿了么（前端）
* 网易
* 搜狐
* 奇虎 360（360 企业安全）
* 唯品会
* 豆瓣
* 大众点评
* 小米
* 美团（美团点评）
* 美丽
* 豌豆荚
* 当当
* 有赞
* 深度
* DNSPod
* 新浪微博
* 今日头条
* 滴滴出行
* eBay

以及各个公司捐献给 Apache 基金会的项目：

* Apache carbondata（华为）
* Apache eagle（eBay）
* Apache kylin（eBay）
* Apache hawq（Pivotal）
* Apache rocketmq（阿里巴巴）
* incubator-dubbo（阿里巴巴）
* incubator-weex（阿里巴巴）
* incubator-doris（百度）
* incubator-echarts（百度）
* incubator-griffin（eBay）
* incubator-skywalking（个人）

根据对上述组织的近 500 个项目的数据采集和分析，我们得出了如下结果。

**数据结果点评**

通过对上述项目从 2017/10/1 至 2018/9/30 止的数据进行分析，其活跃度指标数据如下：

![enter image description here](https://images.gitbook.cn/2f0d0090-d3b6-11e8-abac-396c1f0bcec5)


其中前五名的活跃度变化趋势为：

![enter image description here](https://images.gitbook.cn/dfae7990-d417-11e8-80d1-917ffa8847fa)

其中我们可以看到，阿里系项目独占鳌头，而这五个项目中有三个是前端项目。

这五个最活跃项目的社区化趋势为：

![enter image description here](https://images.gitbook.cn/4964da50-d418-11e8-80d1-917ffa8847fa)

可以说，除了阿里巴巴的飞冰（ice）项目外，其它项目的社区参与程度都很高。

其中前五名的项目的各自情况如下：

**1. 蚂蚁金服的 ant-design 前端项目**

> 项目地址： [https://github.com/ant-design/ant-design](https://github.com/ant-design/ant-design)

这是一个“服务于企业级产品的设计体系”，是由蚂蚁金服体验技术部采用 React 封装的一套组件库。

![enter image description here](https://images.gitbook.cn/69bf79e0-d418-11e8-80d1-917ffa8847fa)

从其最近一年的活跃度数据（红）来看，其一年之内就有 2298 个提交，最多的一周有 122 个提交；而在这一年内，新增了 350 位贡献者和 1057 个 PR。可以说是一个活跃度非常高的前端项目了，而且从趋势上，其近期的活跃度趋势还在增加。

不过，从其社区化指数（蓝）上看，其社区参与比例在近期略有下降，但是整体来说，依旧维持较高水平（95% 以上）。

**2. 阿里巴巴的 pouch 容器引擎**

> 项目地址：[https://github.com/alibaba/pouch](https://github.com/alibaba/pouch)

这是阿里巴巴在云计算方面的一个重大项目，其对于阿里巴巴集团内部的容器化进程起到了极大的推动。

![enter image description here](https://images.gitbook.cn/8d24c160-d418-11e8-80d1-917ffa8847fa)

这个项目迄今也只有一年的发展历程，但是其活跃度从一开始就高居不下，甚至在 2018 年 8 月有个显著的活跃高峰。虽然其一年来只有几十位做出提交的贡献者，但是每周的提交数量、PR 数量都很稳定，说明项目的发展很健康。

比较有意思的是，这个项目的社区化程度比较高，也比较稳定，从其官网和 GitHub 主页上的文档和说明全是英文来看，其国际化推广的程度比较高。

**3. 华为捐献给 Apache 基金会的 CarbonData 项目**

> 项目地址：[https://github.com/apache/CarbonData](https://github.com/apache/CarbonData)

Apache CarbonData 项目是一个索引列数据存储方案，可用于大数据平台（如 Apache Hadoop、 Apache Spark）的快速分析。

![enter image description here](https://images.gitbook.cn/b24b67f0-d418-11e8-80d1-917ffa8847fa)

其项目的活跃度相当可观，社区化程度也能稳定在很高的程度上。这个项目是唯一进入前五的 Apache 基金会管理项目，也是华为所有项目中活跃度最高的项目。

**4. 阿里巴巴的飞冰前端项目**

> 项目地址： [https://github.com/alibaba/ice](https://github.com/alibaba/ice)

这又是阿里巴巴的一个项目，同样是前端项目，其“海量可复用物料，配套桌面工具极速构建前端应用”。

![enter image description here](https://images.gitbook.cn/02cf7d60-d41e-11e8-80d1-917ffa8847fa)

这个项目的出现也不久，还不到一年，其活跃度也相当可观，但是同样，随着项目的成熟，其社区参与度也一路走低极低水平。

**5. 饿了么的前端项目 element**

项目地址：[https://github.com/elemefe/element](https://github.com/elemefe/element)

这个项目是饿了么前端部门“为开发者、设计师和产品经理准备的基于 Vue 2.0 的桌面端组件库”。

![enter image description here](https://images.gitbook.cn/11375530-d419-11e8-80d1-917ffa8847fa)

从该项目的活跃度来看，波动比较大，且近期有活跃度减低的趋势。而社区化程度则保持较高的程度。

在前五之外，我们要额外对第 6 名 Apache 孵化项目 skywalking 做一个说明：

**6. 个人主导的 Apache 孵化项目 skywalking**

> 项目地址：

> [https://github.com/apache/incubator-skywalking](https://github.com/apache/incubator-skywalking)

这是国内唯一进入 Apache 基金会的由个人主导的开源项目。它是一个分布式跟踪系统和应用监测系统，主要用于微服务、容器环境的监测。

![enter image description here](https://images.gitbook.cn/36a11f40-d419-11e8-80d1-917ffa8847fa)

作为一个由个人主导的开源项目，而且是活跃于云原生领域的，能取得这样高的项目活跃度十分不易。

**小结**

从上述表格数据可以看到，阿里巴巴/蚂蚁金服在开源方面活跃度很高（前 50 名中，超过了一半）。从下图可以看出来，其整体的活跃度和社区化程度都不错。

![enter image description here](https://images.gitbook.cn/582bda60-d419-11e8-80d1-917ffa8847fa)

![enter image description here](https://images.gitbook.cn/6661da80-d419-11e8-80d1-917ffa8847fa)

另外，除了阿里巴巴、腾讯、百度、华为之外，有赞、饿了么、唯品会也有几个项目的活跃度很高，可见现在注重开源的互联网企业越来越多了。

而在上榜的项目当中，前端项目占据比较多，这可能与这种项目的迭代速度较快有关。