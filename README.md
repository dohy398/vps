# vps推荐 国外：先定机房再看线路，香港/日本/新加坡/洛杉矶四地套餐怎么挑、一年大概花多少

搜"vps推荐 国外"的人，多半已经把方向定了一半：机器放境外，省掉备案，但访问的人主要在国内。真正让人反复刷帖的地方在于"买了之后晚高峰会不会卡成幻灯片"。

先给答案。国外 VPS 的价格跨度很大。2026 年 1 月一份收录 118 个可索引方案的数据集显示，中位价是每月 14.58 美元，P75 是每月 45 美元，中位配置 4 vCPU / 8GB / 160GB。预算放到 30 美元以上，基本就进入了为回国线路付费的档位。

这个档位里，GoMami 的定位很明确：全线走 CN2 / AS9929 / CMIN2 三网优化，机房在香港、日本东京、新加坡和洛杉矶，最低月付 29 美元，全线 KVM 虚拟化、NVMe 存储、免安装费。

> **选购速览**
> 面向大陆用户建站、API、游戏服务器，优先看香港：HKG Pulse Mini（2 核 / 4GB / 60GB NVMe / 1TB 流量，1Gbps）月付 59 美元，是这套体系里比较稳的入门点。
> 单核性能更关键的话，HKG Peak Mini 同样 59 美元，但换成了 Ryzen 9 9950X（最高 5.7GHz），代价是硬盘只有 40GB。往上一档是 HKG Turin Mini，69 美元，EPYC 9575F + 100GB NVMe。
> 预算压在 30 美元以内，日本或新加坡的 Pulse Nano（2 核 / 2GB / 40GB / 500GB 流量）走同一套三网线路。
> 👉 [查看 GoMami 全线套餐与当前价格](https://bit.ly/Gomami)

## 国外 VPS 的选型顺序：机房 → 线路 → 配置 → 价格

这个顺序值得坚持，因为四项对最终体验的影响权重完全不同。机房位置决定了延迟的物理下限，物理距离没法靠软件补回来。线路决定了晚高峰时这个下限能保住多少：同样一条香港到深圳的链路，晚上九点可能从 30ms 抖到 200ms，也可能纹丝不动，差别全在线路类型上。配置决定这台机器能不能撑住你的业务。价格是前三项定完之后才轮到讨论的东西。

所以"vps推荐 国外"这类问题，难点在第二步。市面上标着"CN2"的机器很多，具体做法差别很大：有的只在去程走优化，回程走普通骨干；有的只优化电信一家，联通移动用户照样卡；还有的把普通 163 骨干包装成"CN2 线路"卖。

三家运营商的精品网是三条完全不同的路：

- **CN2**：中国电信的精品骨干，拥塞程度低于普通 163 骨干，电信用户优先走这条。
- **AS9929**：中国联通的精品国际线路，晚高峰拥塞较少，吞吐更稳。
- **CMIN2**：中国移动国际网络的较新线路，持续性表现不错。

GoMami 的"China Mainland Optimized Pro"就是在三张网之间做调度，让电信、联通、移动用户同时拿到可用速度。官方文档的口径是 RTT 小于 50ms，针对三家运营商分别优化，没有承诺"全国每个省都在 50ms 以内"，这点需要分清楚。

## 国外 VPS 现在多少钱：几个能对照的价格锚

便宜的国外 VPS 确实存在，但买到的通常是通用算力，回国线路要另算。OVHcloud 的 VPS-1 是每月 4.54 美元（2 vCore / 4GB / 40GB / 无限流量 / 500Mbps），VPS-2 是 8.50 美元（4 vCore / 8GB / 75GB / 1Gbps）；Hetzner 的 ARM CAX 实例大约每月 4 美元。这类低价方案的常见区域在欧洲机房，具体可用区域和延迟表现以各自官网所选区域为准，从国内访问通常要绕行。

带中国方向优化的大致分两档。搬瓦工的 CN2 GIA 入门方案是 2 vCPU / 1GB / 20GB / 1TB，年付 49.99 美元，折下来每月四美元出头，但内存只有 1GB，在 2026 年跑 WordPress 加数据库会很紧张。DMIT 的入门 CN2 GIA 方案是 1 vCPU / 1GB / 20GB / 2TB，月付 6.9 美元。

GoMami 站在更高一档：全线最低 29 美元/月，香港最低 49 美元/月，对应的是当期 AMD EPYC 和 Ryzen 平台。

有一个价格变化值得单独提：HKG Pulse Mini 在 2025 年 8 月是 39 美元/月，2026 年 5 月还有测评记录显示 15% 折扣后的价格是 33.15 美元（也就是原价仍是 39），到 2026 年 6 月的全线产品表里已经变成 59 美元。一年涨了约 51%。这解释了一个常见困惑：2025 年写的 GoMami 测评，配置数据还能用，价格已经完全对不上。

## GoMami 全线套餐对比

下面是 GoMami 官网当前展示的全部方案，按产品线拆开。所有价格都是月付原价，实际结算以下单页为准。

### 香港 HKG Turin（AMD EPYC 9575F，Zen 5，最高 5.0GHz）

| 套餐 | 配置（vCPU / 内存 / NVMe） | 流量 / 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| Turin.Mini | 2 核 / 4GB / 100GB | 1000GB / 2Gbps | $69 | [ 订购](https://gomami.io/store/hkg-turin?aff=415) |
| Turin.Air | 4 核 / 8GB / 140GB | 2000GB / 2Gbps | $129 | [ 订购](https://gomami.io/store/hkg-turin?aff=415) |
| Turin.Pro | 6 核 / 16GB / 180GB | 5000GB / 5Gbps | $299 | [ 订购](https://gomami.io/store/hkg-turin?aff=415) |
| Turin.Ultra | 12 核 / 32GB / 220GB | 10000GB / 5Gbps | $599 | [ 订购](https://gomami.io/store/hkg-turin?aff=415) |

Turin 全线配 PCIe Gen5 U.2 SSD 和 DDR5 6400MHz 内存，Pro 和 Ultra 标注 Windows-ready。

### 香港 HKG Peak（AMD Ryzen 9 9950X，最高 5.7GHz）

| 套餐 | 配置（vCPU / 内存 / NVMe） | 流量 / 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| Peak.X5.Mini | 2 核 / 4GB / 40GB | 1000GB / 2Gbps | $59 | [ 订购](https://gomami.io/store/hkg-peak?aff=415) |
| Peak.X5.Air | 4 核 / 8GB / 60GB | 2000GB / 2Gbps | $99 | [ 订购](https://gomami.io/store/hkg-peak?aff=415) |
| Peak.X5.Pro | 6 核 / 16GB / 80GB | 5000GB / 5Gbps | $199 | [ 订购](https://gomami.io/store/hkg-peak?aff=415) |

### 香港 HKG Pulse（AMD EPYC 7763，3.5GHz）

| 套餐 | 配置（vCPU / 内存 / NVMe） | 流量 / 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| Pulse.Nano | 2 核 / 2GB / 40GB | 500GB / 1Gbps | $49 | [ 订购](https://gomami.io/store/hkg-pulse?aff=415) |
| Pulse.Mini | 2 核 / 4GB / 60GB | 1000GB / 1Gbps | $59 | [ 订购](https://gomami.io/store/hkg-pulse?aff=415) |
| Pulse.Air | 4 核 / 8GB / 80GB | 2000GB / 1Gbps | $119 | [ 订购](https://gomami.io/store/hkg-pulse?aff=415) |
| Pulse.Pro | 8 核 / 16GB / 100GB | 5000GB / 3Gbps | $269 | [ 订购](https://gomami.io/store/hkg-pulse?aff=415) |
| Pulse.Ultra | 12 核 / 32GB / 300GB | 10000GB / 3Gbps | $499 | [ 订购](https://gomami.io/store/hkg-pulse?aff=415) |

Pulse.Pro 和 Pulse.Ultra 标注 Windows-ready。

### 日本东京 JPN Pulse

| 套餐 | 配置（vCPU / 内存 / NVMe） | 流量 / 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| JPN.Pulse.Nano | 2 核 / 2GB / 40GB | 500GB / 1Gbps | $29 | [ 订购](https://gomami.io/store/jpn-pulse?aff=415) |
| JPN.Pulse.Mini | 2 核 / 4GB / 60GB | 1000GB / 1.5Gbps | $49 | [ 订购](https://gomami.io/store/jpn-pulse?aff=415) |
| JPN.Pulse.Air | 4 核 / 8GB / 80GB | 2000GB / 1Gbps | $89 | [ 订购](https://gomami.io/store/jpn-pulse?aff=415) |
| JPN.Pulse.Pro | 8 核 / 16GB / 100GB | 5000GB / 3Gbps | $169 | [ 订购](https://gomami.io/store/jpn-pulse?aff=415) |
| JPN.Pulse.Ultra | 12 核 / 32GB / 300GB | 10000GB / 3Gbps | $338 | [ 订购](https://gomami.io/store/jpn-pulse?aff=415) |

日本节点在第三方资料里记为 EPYC 7773X / 7K83 平台，官方商店页未标注具体型号，以官网为准。Pro 和 Ultra 标注 Windows-ready。

### 新加坡 SIN Pulse

| 套餐 | 配置（vCPU / 内存 / NVMe） | 流量 / 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| SIN.Pulse.Nano | 2 核 / 2GB / 40GB | 500GB / 1Gbps | $29 | [ 订购](https://gomami.io/store/sin-pulse?aff=415) |
| SIN.Pulse.Mini | 2 核 / 4GB / 60GB | 1000GB / 1Gbps | $49 | [ 订购](https://gomami.io/store/sin-pulse?aff=415) |
| SIN.Pulse.Air | 4 核 / 8GB / 80GB | 2000GB / 1Gbps | $89 | [ 订购](https://gomami.io/store/sin-pulse?aff=415) |
| SIN.Pulse.Pro | 8 核 / 16GB / 100GB | 5000GB / 3Gbps | $169 | [ 订购](https://gomami.io/store/sin-pulse?aff=415) |
| SIN.Pulse.Ultra | 12 核 / 32GB / 300GB | 10000GB / 3Gbps | $338 | [ 订购](https://gomami.io/store/sin-pulse?aff=415) |

### 洛杉矶 LAX Pulse（AMD EPYC 平台）

| 套餐 | 配置（vCPU / 内存 / NVMe） | 流量 / 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| LAX.Pulse.Nano | 2 核 / 2GB / 40GB | 1000GB / 1Gbps | $29 | [ 订购](https://gomami.io/store/lax-pulse?aff=415) |
| LAX.Pulse.Mini | 2 核 / 4GB / 60GB | 2000GB / 1Gbps | $59 | [ 订购](https://gomami.io/store/lax-pulse?aff=415) |
| LAX.Pulse.Air | 4 核 / 8GB / 80GB | 4000GB / 2Gbps | $129 | [ 订购](https://gomami.io/store/lax-pulse?aff=415) |
| LAX.Pulse.Pro | 6 核 / 16GB / 100GB | 8000GB / 3Gbps | $259 | [ 订购](https://gomami.io/store/lax-pulse?aff=415) |
| LAX.Pulse.Ultra | 12 核 / 32GB / 300GB | 15000GB / 5Gbps | $599 | [ 订购](https://gomami.io/store/lax-pulse?aff=415) |
| LAX.Pulse.Titan | 12 核 / 32GB / 600GB | 30000GB / 10Gbps | $999 | [ 订购](https://gomami.io/store/lax-pulse?aff=415) |

洛杉矶是目前唯一做到去程和回程都走三网精品的节点，流量也给得比亚洲节点宽（Nano 就是 1TB，亚洲是 500GB）。官方商店页的 LAX 套餐没有全线标 Windows-ready，这个标注只出现在 Pro 及以上档位的亚洲节点上，别默认 LAX 所有套餐都能装 Windows。

### 香港 HKG Forge 独立服务器

| 套餐 | 配置 | 流量 / 端口 | 价格 | 购买 |
| --- | --- | --- | --- | --- |
| Forge.Mini | EPYC 7663（56 核 112 线程）/ 128GB / 960GB NVMe | 10TB / 2Gbps | 以结算页为准 | [ 订购](https://gomami.io/store/hkg-forge?aff=415) |
| Forge.Air | EPYC 7663（56 核 112 线程）/ 256GB / 4TB NVMe | 20TB / 2Gbps | 以结算页为准 | [ 订购](https://gomami.io/store/hkg-forge?aff=415) |

Forge 用的是 TYAN B8033 平台，付款后即时开通，面板里随时可以重装系统，流量超额按每 GB 0.06 美元计，额外 IP 每个 10 美元、单机最多 4 个。官网不同页面与结算页显示可能不一致，下单以结算页为准。

## 三套硬件平台怎么选：Turin、Peak、Pulse 各自适合什么

GoMami 的定价按硬件平台分层，跟"小中大"那种按核心数切档的逻辑不一样。搞清楚这一点，能省下不少冤枉钱。

**Turin（EPYC 9575F）** 是旗舰。Zen 5 架构，最高 5.0GHz，配 PCIe Gen5 SSD 和 DDR5 6400MHz 内存。这是少数跨过 5GHz 线的 EPYC 型号，单核性能接近桌面级 Ryzen 9。第三方在 2025 年 10 月测过 Turin.Mini，Geekbench 5 单核 1101、多核 2116，相比 EPYC 7763 单核高 123.8%、多核高 130%。Lowendaff Blog 在 2026 年 1 月对香港 Turin 做的独立测试里，到新加坡的持续吞吐是 2.16 Gbps、延迟 40.4ms，到深圳电信是 1.76 Gbps，回程 893 Mbps。

**Peak（Ryzen 9 9950X）** 单核最强，加速频率最高 5.7GHz。适合游戏服务器、实时通信这类"一个线程扛全部"的场景。

**Pulse（EPYC 7763 / 7773X / 7663）** 频率低、核心多、价格便宜。适合容器、多租户、数据库、横向扩展的业务。

关键在于：Turin 和 Pulse 走的是同一条路由。Turin Mini 卖 69 美元，Pulse Mini 卖 59 美元，两者都在香港、都是 CN2/9929/CMIN2 三网优化。多花的 10 美元买到的是 CPU 单核性能、PCIe Gen5 和 DDR5，这笔钱买的是算力，不是线路。如果你的业务不吃单核（普通 WordPress、静态站、小 API），这 10 美元可以省。

还有个容易忽略的细节：Peak Mini 和 Pulse Mini 都卖 59 美元，同价，但 Peak 给的是 40GB 硬盘、2Gbps 端口，Pulse 给的是 60GB 硬盘、1Gbps 端口。硬盘更大还是端口更快，看你实际跑什么。

👉 [对比 HKG Turin 四档配置与当前价格](https://gomami.io/store/hkg-turin?aff=415)

## 亚洲节点和洛杉矶，路由方向不一样

结论先放这里：香港、日本、新加坡三个亚洲节点是回程走三网精品、去程走主线直连；洛杉矶是去程回程都走精品。

回程指服务器到用户这一段。对建站和普通应用来说，回程决定用户感知到的速度，所以亚洲节点被定位成建站的甜点区，香港到深圳、广州这类链路尤其明显。去程走主线直连的好处是不绕路，国内上传、SSH 操作这些体验也更顺。

洛杉矶走的是去程和回程都精品的双向方案，是全线规格最高的自定义路由。代价是跨太平洋的物理延迟躲不掉，适合同时服务中国和北美用户，或者业务本身就需要美国 IP 的场景。

新加坡 Pulse.Mini 有一份 2025 年 12 月的第三方测评，结论是"三网较均衡，电信稍弱，速度和延迟表现优秀，按单位流量成本算偏贵"。这个评价放在 2026 年依然成立，只是当时记录的 39.2 美元月费已经不是现在的价格。

## 套餐表里没写的费用和限制

这部分是决定"一年到底花多少"的关键。除了表里的月费，还有下面这些。

先说标配项：全线 VPS 都含 KVM 虚拟化、NVMe SSD、免安装费，以及每日自动备份到 AWS S3。备份这一项平时不显眼，真出事的时候能省很多事，同价位不少商家是要单独收费的。

| 项目 | 规则 |
| --- | --- |
| 换 IP | 每次 5 美元，即时生效，旧 IP 立即释放且无法找回 |
| 实例转移 | 每次 10 美元，人工处理，24 小时内完成 |
| 流量包 | 100GB $6 / 500GB $30 / 1TB $60 / 2TB $120 / 5TB $300 / 10TB $600 / 20TB $1200，只在本计费周期有效，不结转到下月 |
| 流量超额 | 官方说明是超额后可能限速，具体策略视产品规格而定；另有测评称会被压到极低速度直到下个周期 |
| Forge 流量超额 | 每 GB 0.06 美元 |
| 到期处理 | 到期日立即暂停，没有宽限期；逾期 5 天终止，数据可能无法恢复 |
| 退款 | 新购 24 小时内可全额退，每用户限一次，续费单不退 |
| 退款到账 | 支付宝 1–3 个工作日，信用卡 5–10 个工作日，加密货币 1–3 个工作日 |
| 退款排除 | 超过 24 小时的订单、因违反条款被终止的服务、续费单、已使用的账户余额、因 DDoS 被黑洞的 IP |
| DDoS 防护 | 默认含 Best-effort 防护；最高 600Gbps 的高级清洗需要额外付费开通 |
| 邻居噪音 | 长期高 CPU 占用影响同节点其他用户，会被判定为 noisy neighbor，可能面临 CPU 限速 |
| 支付方式 | 信用卡/借记卡（Stripe）、支付宝、加密货币 |

退款这条要特别注意：申请通过后，实例和数据会立即永久删除，退款前该备份的先备份。而且这个窗口每用户只有一次，退过之后再下单就没有了。

邻居噪音这条在官方 FAQ 里写得很直接。如果你打算在上面跑持续满载的编译任务或者挖矿类负载，被限速是写在规则里的后果，选独服（Forge）会更合适。

其他细节：控制面板基于 VirtFusion，能看到 IP、计费周期、到期日和网络类型；系统模板覆盖 Ubuntu 20.04/22.04/24.04、Debian 11/12/13、CentOS 7 和 Stream 9、AlmaLinux 9/10、Rocky Linux 8/9/10、Fedora 41/42。

👉 [先月付开一台 Pulse Mini 跑自己的测试](https://gomami.io/store/hkg-pulse?aff=415)

## 优惠码与年付折扣

官方文档的表述是年付比月付省 15%–20%，不同产品线折扣不同。除此之外，目前流传两个码。

**`GOMAMI365`**：年付 8 折。有第三方页面标注为"所有产品年付循环 8 折，有效期至 2026 年 12 月 31 日"，另一处则写"仅 HKG Turin 年付 8 折"。两种说法不一致，稳妥的做法是在下单页填进去验证一下适用套餐。

**`Hi,LAX`**：LAX Pulse 全线 8 折，支持月付。按这个折扣，Nano 从 29 美元降到 23.20，Mini 从 59 降到 47.20，Air 从 129 降到 103.20，Pro 从 259 降到 207.20，Ultra 从 599 降到 479.20，Titan 从 999 降到 799.20。

`GOMAMI365` 本身就是年付 8 折码，不存在和年付折扣二次叠加这回事。若它在你的订单上生效，HKG Turin Mini 的年付总额约 662 美元（69 × 12 × 0.8），HKG Pulse Mini 约 566 美元（59 × 12 × 0.8）。如果按官方 15%–20% 的区间算，这两个数字的上沿分别是约 704 美元和约 602 美元。

👉 [用 Hi,LAX 折扣开一台洛杉矶 Pulse](https://gomami.io/store/lax-pulse?aff=415)

## GoMami 适合谁，不适合谁

如果你在找每月三五美元的国外 VPS，GoMami 的价格门槛对不上，它自己也没打算做这个生意。29 美元起步、香港 49 美元起步，注定它不是价格敏感型用户的选择。

它适合这几类人：面向大陆玩家的 CS、Minecraft 之类游戏服务器（单核频率比核心数重要，Peak Mini 或 Turin Mini 比同价位的 8 核 Pulse 更合适）；外贸和跨境电商站（结算流程对延迟敏感，香港比洛杉矶少一段跨洋 RTT）；给中国企业客户做服务的 SaaS 团队；以及被"伪 CN2"在晚高峰坑过一次、现在只想要稳定的人。

个人博客、小 API、开发测试环境用不上 Turin 的 DDR5 和 Gen5 SSD，Pulse Mini 甚至日本/新加坡的 Nano 就够了。

官网首页展示了三条用户评价，分别来自游戏服务器运营者、对晚高峰速度满意的用户，和一个把电商站迁过来的站长。这些是官方页面展示的案例；第三方视角另有独立测评数据，比如前面提到的 Turin 吞吐测试和 Pulse.Mini 的三网均衡评价。

横向对照一下不同定位的产品（只列信息）：OVHcloud VPS-1 每月 4.54 美元，2 vCore / 4GB / 40GB / 无限流量 / 500Mbps；搬瓦工 CN2 GIA 入门款年付 49.99 美元，内存 1GB；DMIT 入门 CN2 GIA 月付 6.9 美元，内存 1GB。这几款的共同点是价格门槛低，代价是配置小或者机房远。GoMami 走的是反方向：价格门槛高，换三网优化线路和当期 AMD 硬件。

## 几个常见问题

**国外 VPS 需要备案吗？**
不需要。国内机房需要 ICP 备案，境外机房不用。但免备案不等于快，国内访问速度完全取决于线路质量，面向国内用户通常优先考虑香港 CN2 类线路。

**买之前能先测线路吗？**
可以。GoMami 提供官方 Looking Glass（lg.gomami.io），支持 Ping、TCPing、MTR、NextTrace、Traceroute，可选香港 Turin、香港 Peak、香港 Pulse、日本、新加坡各节点，从你自己所在运营商那一侧发起测试，看延迟和路由走向。配合 24 小时退款窗口，等于可以买一台、一天之内跑完自己的测试再决定留不留。

**流量超了会直接扣钱吗？**
不会产生超额账单。官方 FAQ 的说法是超额后可能限速，具体策略取决于产品规格，配额在每个计费周期开始时重置。也可以自己买流量包补，但流量包只在当期有效，不结转。

**能装 Windows 吗？**
官网在部分套餐上标了 Windows-ready：香港 Turin 的 Pro / Ultra、Peak 的 Pro、Pulse 的 Pro / Ultra，以及日本和新加坡 Pulse 的 Pro / Ultra。也就是说只有 Pro 及以上档位明确支持。Windows 授权是否包含，官方页面没有说明，需要下单前确认。

**系统模板有哪些？**
Ubuntu 20.04 / 22.04 / 24.04、Debian 11 / 12 / 13、CentOS 7 和 Stream 9、AlmaLinux 9 / 10、Rocky Linux 8 / 9 / 10、Fedora 41 / 42。控制面板基于 VirtFusion。

**年付和月付差多少？**
官方口径是年付省 15%–20%，具体到每条产品线不完全相同。按 8 折码估算的话，HKG Pulse Mini 年付约 566 美元，HKG Turin Mini 约 662 美元；按 15% 折扣算则是约 602 美元和约 704 美元。

## 最后：按你的情况对号入座

只想要一台便宜境外机器跑点小东西，且不在意国内访问速度——去看 OVHcloud、Hetzner 那类按月四五美元的产品，GoMami 这个价位对你没意义。

访问者主要在国内、预算能到 30 美元——日本或新加坡 Pulse Nano 起步，先月付一个月，用 Looking Glass 对照自己运营商的实测数据，再决定要不要往香港迁。

主要面向大陆用户建站，需要稳定回程——HKG Pulse Mini 59 美元是合理起点，60GB 硬盘比 Peak Mini 多 20GB，1Gbps 端口对普通站点够用。

跑游戏服务器或者单核吃紧的应用——HKG Peak Mini 59 美元（Ryzen 9 9950X，5.7GHz）或 HKG Turin Mini 69 美元，别为了核心数去买同价位的 8 核 Pulse。

需要同时服务中美用户，或者业务明确要美国 IP——LAX Pulse 走双向精品路由，叠加 `Hi,LAX` 之后 Nano 是 23.20 美元/月，是这套体系里门槛最低的入场方式。

下单前有两件事值得花五分钟确认：用官方 Looking Glass 从你自己的网络测一遍目标节点；把优惠码在结算页填进去，看是否适用于你选的那档。退款窗口是兜底，但只能用一次，别浪费在没做测试的订单上。

👉 [按预算挑一台合适的 GoMami 套餐开通](https://bit.ly/Gomami)
