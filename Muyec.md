---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---

# Muyec

1. 自我介绍

   web3新新人。

2. 你认为你会完成本次残酷学习吗？

   能

## Notes

<!-- Content_START -->

### 2024.12.10

1.Arbitrum是什么：Arbitrum 是一个旨在扩展以太坊的技术套件，其核心产品 Arbitrum Rollup 是一种继承以太坊安全性的 Optimistic Rollup 协议，通过降低交易费用和提高交易速度解决了以太坊每秒交易量有限的问题。

2.Arbitrum的技术特点：Arbitrum Rollup 通过将用户交易数据压缩后批量提交至以太坊，并采用“乐观假设”机制，仅在争议情况下触发 L1 验证，从而显著减轻以太坊主网的负担，同时继承以太坊的安全性。

3.多链支持与灵活选择：Arbitrum 支持多条链并行运行，在以太坊主网上，有 2 条 Arbitrum 链：一条 Arbitrum Rollup 链，称为[“Arbitrum One”，](https://portal.arbitrum.one/)一条 AnyTrust 链[，称为“Nova](https://nova.arbitrum.io/)”;用户和开发人员可以选择适合他们的安全/交易成本需求的任何选项。


### 2024.12.11

欺诈证明:欺诈证明是一种逐步细分争议的机制，旨在通过不断缩小争议范围来验证区块和机器状态的正确性。在质询过程中，首先会将全局状态和区块哈希分为两部分，然后逐渐集中到单个区块。在执行阶段，质询被分解为更小的步骤，响应方需要提供数据证明每个步骤的执行状态与预期一致。每一轮质询中，响应方选择相邻的段进行挑战，逐步反驳对方的断言，并细分争议范围。质询的“度数”决定了每次分段的数量，确保挑战不断向前推进。与传统的等分协议不同，本协议采用非对称方式，由挑战者选择要质询的段，响应方提供校样数据。当质询无法得到有效解决时，响应方的状态哈希会被置为 0，从而导致超时失败，最终通过合同升级诊断和修复错误。这种机制不仅确保了挑战过程的透明性，也为错误修复提供了时间窗口。


### 2024.12.12

Nitro 与 Classic:Arbitrum Nitro 是对 Arbitrum Classic 技术栈的升级，代表了 Arbitrum 技术发展的最新一步。两者的目标相似，都是创建一个接近以太坊的执行环境，用以太坊的欺诈证明保证 L2 状态的安全性。但 Nitro 相比 Classic 有显著的改进。在 Classic 中，Arbitrum 使用定制的虚拟机（AVM）执行代码，而在 Nitro 中，采用了 WebAssembly（Wasm），并将 Go 代码编译为 Wasm，这使得 Arbitrum 的 L2 状态机（ArbOS）能够直接包含以太坊的 Geth 实现，从而提高了兼容性。Nitro 的架构选择带来了多方面的优势：更低的费用、更好的以太坊兼容性和系统简化。


### 2024.12.13

Arbitrum Orbit 是一个开发框架，允许用户基于 Arbitrum Rollup 的 L2 创建和启动 L3 网络。Orbit 支持用户定制链功能，包括隐私、权限、费用代币和治理等，同时提供专用吞吐量、流量隔离以及可靠的 Gas 价格，适合特定领域的快速机制设计与迭代，帮助实现更多的价值捕获。
XAI 是基于 Arbitrum Orbit 的首个 L3，定位为专注游戏场景的链，相较于 Nova 通用链，XAI 能够提供更高的性能。它具备专属的计算和存储资源，适合计算密集型场景（如 AI 模型）。同时，XAI 原生集成了 Arbitrum 技术栈，包括 Nitro、BOLD 和 Stylus。
Nitro 是 Arbitrum 的核心技术栈之一，通过直接编译 Geth 核心，显著提升了以太坊的兼容性和性能。这一升级使得 Orbit 链能够以更高效的方式运行，进一步优化用户体验。


### 2024.12.14

交互型 Rollup 确保断言（assertion）正确性的方式分为单轮和多轮交互两种。单轮交互型 Rollup（如 Optimism）中，断言包含调用结果，挑战者可在挑战窗口期内指出具体错误，链上合约模拟执行验证后，如果确有错误，则取消断言并罚没断言者保证金；若无挑战，断言最终确定。多轮交互型 Rollup（如 Arbitrum）通过挑战者与断言者的多轮交互缩小争议范围，最终由链上仲裁合约判定结果并惩罚错误方，设计目的是将链上仲裁的计算量降至最低。


### 2024.12.15

交互式证明:Arbitrum 通过交互式证明机制高效解决争议。以链下处理为主，仅在争议缩小到单步操作时，让 L1 合约参与验证，从而显著降低链上的计算和存储负担。这种机制基于双方的回合制交互，将争议逐步缩小至最小范围，最终解决问题。与重执行交易模式相比，交互式证明更加高效。乐观情况下，它允许一个 Rollup 区块仅包含一个断言，覆盖整条链的状态变化，从而节省 L1 空间开销；在悲观情况下，L1 合约也只需验证操作方向正确，而非重执行整笔交易。此外，交互式证明不受以太坊交易 Gas Limit 和合约大小的限制，这为 Arbitrum 提供了更高的交易吞吐量和合约灵活性。交互式证明是 Arbitrum 设计的核心驱动力，决定了其高效性和灵活性。大多数特性都围绕这一机制展开，显著提升了 Rollup 的性能和实用性，突破了传统 Rollup 设计的限制。


### 2024.12.16

Arbitrum One 是基于 Optimistic Rollup 技术的以太坊扩展链，结合 L1 和 L2 架构，通过 EthBridge 和 Arbitrum 虚拟机（AVM）实现智能合约执行和数据交互。Nitro 是 Arbitrum One 的升级版本，提供更低费用、更高以太坊兼容性，并通过 zk 证明和优化的 Geth 引擎提升性能。Arbitrum Nova 则是专为游戏和社交应用等高频交互的 DApp 设计的链，采用 AnyTrust 技术，提供两种数据发布方式，通过牺牲部分安全性提升性能，适合成本敏感的用例。


### 2024.12.17
Nitro 代表了 Arbitrum 技术发展的重要一步，是 Arbitrum One 主网的技术堆栈的升级版，我们现在称之为“Arbitrum Classic”，它比 2018 年最初的 Arbitrum 白皮书描述的技术更为先进。本文将解释 Nitro 升级的原因，并概述其相对于经典系统的核心优势。
从宏观来看，Classic 和 Nitro 系统的目标相似：都旨在提供一个尽可能接近 EVM（以太坊虚拟机）的执行环境，作为以太坊的第二层（L2）解决方案。即，通过以太坊自身的简洁欺诈证明来确保和执行 L2 虚拟机状态更新的安全性。
在 Arbitrum Classic 中，我们通过定制的虚拟机（AVM）实现这一目标，而 Arbitrum 的 L2 状态机实现（称为“ArbOS”）则是一个编译后上传到 AVM 的程序，具备模拟 EVM 执行能力的功能。
在 Nitro 中，我们采用 WebAssembly (Wasm) 替代 AVM 执行低级指令。由于 Go 代码可以编译为 Wasm，因此我们能够使用 Go 实现 ArbOS，并将 Geth（最广泛使用的以太坊实现）作为子模块嵌入其中。这一架构（直接使用 Geth 的 EVM 实现）是 Nitro 的核心特征，也是 Nitro 升级的关键。


### 2024.12.18
$ARB 代币:$ARB 代币是一种 ERC-20 治理代币，持有者可以通过它参与 Arbitrum DAO 的链上治理，决定 Arbitrum One 和 Arbitrum Nova 链的运行和升级。代币的投票权根据持有数量加权，更多代币意味着更大的投票影响力。$ARB 代币可以委托给他人使用，方便没有时间审查提案的成员参与治理。$ARB 的初始供应量为 100 亿枚，每年最多铸造 2% 的新币，铸币活动由 DAO 通过提案管理。通过 $ARB 代币，持有者可以民主地影响 Arbitrum 生态系统的未来。


### 2024.12.19
治理框架:ArbitrumDAO的修订宪法设定了治理规则和程序，其中部分规则通过链上智能合约执行，其他则通过链下行动。所有规则具有同等约束力，且包括推荐指南，虽然不具约束力，但作为良好治理的建议。该宪法描述了ArbitrumDAO和Arbitrum基金会的治理框架，并明确了可修改的程序。

链所有权:ArbitrumDAO可授权创建额外的Layer-2链，这些链使用Arbitrum技术结算到以太坊。每个新增的链必须通过AIP授权，且根据是否受到$ARB代币管理，分为治理链和非治理链。治理链受到$ARB代币管理，而非治理链则不受代币管理，但都需在以太坊上结算。

DAO提案和投票程序:AIP提案的提交和投票遵循严格的程序。首先，提案会进行体温检查（1周讨论），然后进行正式AIP提交并进行为期3天的投票。投票期后，DAO成员将在14-16天内投票决定提案是否通过。每个提案需标明是否为宪法AIP，宪法AIP修改章程，而非宪法AIP包括资金申请和信息性提案。

提案通过标准:AIP提案的通过需要满足特定的投票条件：宪法AIP要求至少5%的$ARB代币参与投票，非宪法AIP要求至少3%。投票期间，如果达成条件，提案会进入下一阶段。若未通过，则结束流程。通过后，宪法AIP将进入后续阶段执行，非宪法AIP则直接执行。

提案实施阶段:提案通过后的实施分为多个阶段：L2等待期、L1消息和L1等待期。经过这些阶段后，AIP将最终实施。实施可以通过L1上的确认消息来启动，也可以通过治理链间的交易来完成。整个AIP提案和执行流程一般需要27到37天，具体时长取决于提案的类型。


### 2024.12.20
Arbitrum 空投积分系统依据用户在 Arbitrum One 和 Arbitrum Nova 的活动来确定代币分配，积分上限为 15 分。快照日期之前，每完成一项符合条件的操作可获得 1 分；在 Arbitrum Nitro 上线（2022 年 8 月 31 日）之前完成的得分（至少 3 分）可翻倍。符合条件的操作包括桥接资金、完成多次交易、与多个智能合约交互以及交易总额达到指定金额等；Nova 上的积分最多为 4 分，若 One 上得分已达 4 分，还可额外加 1 分。此外，DAO 空投面向 Arbitrum 生态中的协议及以太坊贡献者集体，分配依据协议的活跃度、TVL、用户交互等多项定性与定量指标。空投代币自 2023 年 3 月 23 日起开放领取；投资者和团队代币则按 4 年锁定规则分期释放，首次解锁在代币生成事件一年后（2024 年 3 月 16 日），此后剩余部分按月线性解锁。


### 2024.12.21
Arbitrum 的技术优势与市场地位：
Arbitrum 是以太坊第二层扩容方案的领先者，采用 Optimistic Rollup 技术，兼具扩展性和隐私特性。它支持未修改的 EVM 合约和以太坊交易，同时继承以太坊的安全性。截至 2022 年 6 月，Arbitrum 的锁定价值占第二层市场的 50.88%，在竞争中占据主导地位，相比 Polygon 和 Optimism 等方案表现更为优越。
ARB 代币的市场表现与未来展望：
ARB 代币于 2023 年 3 月 23 日上市，初期价格波动在 0.60 美元至 0.66 美元之间（取决于供应条件）。根据预测，2023 年价格或达到 1.35 美元至 2.32 美元之间，2024 年进一步上涨至 5.41 美元至 7.04 美元。Arbitrum 生态系统的扩大、机构投资者的关注及交易所的支持，预计将成为推动 ARB 代币价值增长的主要驱动因素。


### 2024.12.22
Arbitrum的地位：
Arbitrum 作为当前最领先的二层扩容解决方案之一，在各大扩容协议中占据了显著的市场份额。据 L2BEAT 数据显示，Arbitrum 在所有二层网络中以超 36 亿美元的市值领先，约占二层总锁仓量的 57%。而根据 DefiLlama 的统计数据，Arbitrum 的总锁仓量为 25.5 亿美元，略低于 L2BEAT 的数据。尽管如此，Arbitrum 生态系统依然显示出强大的吸引力，其中锁仓量超过 1 亿美元的项目包括知名的 DeFi 协议如 SushiSwap、GMX、Stargate、Curve、Dopex、Treasure DAO、Synapse 和 dForce 等，这些项目的表现显著推动了平台的成长。在 Arbitrum 上，SushiSwap 是占据主导地位的项目，单项目锁仓量超过 5 亿美元，占总锁仓量的 20%以上，紧随其后的是 GMX，锁仓量达到 4.38 亿美元。此外，在 DefiLlama 统计的 Arbitrum 生态中的 72 个项目中，40 个项目的锁仓量都超过了 100 万美元，且大多数是支持多链的协议，进一步提升了 Arbitrum 网络的去中心化金融生态影响力。从用户参与度来看，Arbitrum 的存款地址数在其主网上线后的去年激增，而最近几个月保持缓慢上升的趋势，目前累计存款地址已接近 25 万个。这些数据显示，Arbitrum 无论是在锁仓量还是生态增长方面，都在不断巩固其在二层扩容领域的领导地位。


### 2024.12.23
出入金与钱包支持：
多个主流中心化交易所已集成 Arbitrum One 主网，支持 ETH 和 USDT 的充提，包括 Bitget、币安、Bybit、Crypto.com、FTX、火币、KuCoin、MEXC、OKX 等交易所。钱包方面，已有 24 个钱包支持 Arbitrum One 主网，如 BitKeep、Coinbase Wallet、MetaMask、DeBank、imToken、MathWallet、Trust Wallet、Zapper、Zerion 等。此外，Banxa 提供 Visa 或 Mastercard 卡直接购买 ETH 和 USDT 的服务；CryptoRefills 支持用户通过比特币等加密货币购买礼品卡或代金券，同时支持包括 Arbitrum 在内的多个网络；Mt Pelerin 和 Transak 等法币网关也支持在 Arbitrum 上购买和出售加密货币。

跨链桥与资产转移：
Arbitrum One Bridge 是官方跨链桥，允许在 L1 和 L2 之间进行多种代币的跨链转移，L1 到 L2 约需 10 分钟，L2 到 L1 约需 8 天。Across Protocol 支持以太坊、Optimism、Arbitrum 和 Boba 的跨链，但目前不支持 L2 间直接转移。Multichain 和 Celer cBridge 是较为热门的跨链工具，分别支持包括 Arbitrum 在内的多个网络；Hop Protocol 专注于以太坊、Polygon、Optimism 和 Arbitrum 等生态内的跨链转移。其他工具如 BoringDAO、Bungee、Connext、deBridge、LI.FI 和 RenBridge 等均支持多个网络的资产跨链转移或兑换，部分项目还发布了原生代币或激励计划。此外，基于 LayerZero 的 Stargate 和 Synapse Protocol 提供高效的跨链解决方案，支持以太坊、Arbitrum、BNB Chain 等主流网络间的互操作。Composable Finance Mosaic、SOCKET、Rubic 等工具也整合了多种桥接方案，为用户提供了更多选择。


### 2024.12.24

Tracer DAO：衍生品元协议与治理发展
Tracer DAO 是一个基于 Balancer 构建的衍生品元协议，其核心应用是 Perpetual Pools，用户可通过杠杆代币形式实现无需清算且长期持有的交易，还能通过质押赚取奖励，同时具有高资本效率和可组合性。Tracer V1 收取 1% 的协议费用，V2 即将推出，将允许无需许可的部署。项目已发布治理代币 TCR，并将 10% 分配用于流动性挖矿奖励计划。此外，Tracer DAO 曾获 Framework Ventures 等知名机构投资，共融资 900 万美元。

### 2024.12.25

Arbitrum 生态：多元化的应用布局
在 Arbitrum 生态上，主要项目覆盖兑换、借贷、流动性管理和 NFT 市场等领域。例如，Swapr、ZipSwap 等支持多链 AMM；Aave V3、Vesta Finance 等提供跨链资产流动性和借贷服务；iZUMi Finance、YIN Finance 等专注流动性挖矿和主动流动性管理；Superfluid 则实现可编程资金流；NFT 市场方面，Stratos 和 TreasureDAO 热度较高，后者通过 MAGIC 代币计价并推出 Bridgeworld 元宇宙游戏，增强了其生态吸引力。

### 2024.12.26
比特币现货ETF获批及以太坊生态的快速发展:1月11日，比特币现货ETF终于获得批准，为传统投资者提供了新的进入加密市场的途径。与此同时，以太坊即将迎来Dencun升级，其中以EIP-4844为核心的技术将大幅降低L2交易费用并提升性能，这使得以太坊在扩展性方面获得了更强的支持，Arbitrum作为以太坊的主要L2解决方案，也因此成为市场关注的焦点。

Arbitrum生态的崛起：Arbitrum生态在不断扩展，Offchain Labs推出的Arbitrum Orbit使得开发者能够无需许可地构建专用链。这一创新使得基于以太坊的多链架构成为可能，且每个Orbit链都具备高度自定义能力，支持定制Gas费用、吞吐量、隐私和治理等功能。特别是Arbitrum Orbit对自定义Gas代币的支持，能够进一步增强链内代币的实用性并推动生态系统的发展。

Arbitrum Orbit生态项目的潜力:目前，已有多个项目计划通过Arbitrum Orbit推出专用链，涵盖游戏、NFT、DeFi等多个领域。例如，Xai专注于为游戏打造去中心化平台，Frame面向创作者和收藏家，而RARI Chain则通过低交易成本和集成多个平台为NFT市场提供支持。这些创新项目展示了Arbitrum Orbit在多元化应用中的巨大潜力，也为以太坊生态的未来增添了新的动力。


### 2024.12.27
Arbitrum Orbit 的技术优势与近期更新:
Arbitrum Orbit 支持 Rollup 和 AnyTrust 两种模式，提供高吞吐量、自定义 Gas 代币、治理、隐私及协议逻辑配置等灵活特性。其最新更新允许 Orbit 链使用特定 ERC-20 代币作为 Gas，从而增强了链的可定制性。此外，Orbit 借助 Stylus 实现 EVM+ 兼容性，支持使用 Solidity、C、C++ 和 Rust 编写智能合约，为开发者提供高性能和跨语言合约的能力。Orbit 生态现已吸引 18 个项目入驻，涵盖游戏、NFT、衍生品和流动性等领域。与 Caldera、AltLayer、Conduit 的合作，则进一步降低了开发者启动自定义 Rollup 的门槛。

### 2024.12.28

Orbit 生态项目亮点及其影响:
Orbit 生态中涌现了多个具有代表性的项目，为去中心化生态的发展注入了活力。例如，专注去中心化游戏生态的 Xai，已上线主网并计划推出链上卡牌游戏《Final Form》，目标是提供抽象的钱包与账户体验；主打低成本交易和无 Gas 铸造的 RARI Chain，支持信用卡支付并集成 LayerZero 等合作伙伴；借助 AltLayer 和 Orbit 部署 Layer3 Rollup 的 Cometh，专注服务卡牌游戏 Cosmik Battle；以及 Superposition，通过去中心化订单簿提供共享深度流动性。这些项目的多样化场景展示了 Orbit 在推动创新和应用落地方面的潜力，同时也证明 Orbit 平台已经成为开发者构建高性能去中心化应用的核心支柱，为 Arbitrum 生态向多功能区块链平台扩展奠定了坚实基础。


### 2024.12.29
Arbitrum 技术栈深度解析：
Stylus 技术框架
Stylus 是 Arbitrum 的新一代智能合约开发框架，支持多种编程语言的智能合约开发，包括 Rust、C++、C 以及其他可编译为 WASM 的语言。Stylus 与以太坊虚拟机（EVM）完全兼容，提供高性能的执行环境，并支持跨语言互操作，确保与以太坊生态系统的良好兼容性。

BOLD (Block Operation Ledger Derivation) 技术
BOLD 技术旨在优化区块操作和账本派生，提升链上数据处理效率，并增强跨链通信能力。其主要优势在于降低链上存储成本、提高交易处理速度，并优化数据可用性证明，从而进一步提升区块链的整体性能和效率。

Nitro 引擎架构
Nitro 引擎架构包含多个关键系统组件，如交易管理器、状态管理器、共识引擎和网络层。其设计旨在提供高吞吐量、低延迟、强一致性和可扩展性，确保 Arbitrum 在处理交易和智能合约时能够保持高效与稳定。


### 2024.12.29
Arbitrum 短期激励计划:
Arbitrum 在分发 ARB 代币后开始去中心化，Arbitrum DAO 负责治理 Arbitrum One 和 Arbitrum Nova，代币持有者可通过投票参与决策。DAO 财库保留了 42.78% 的 ARB 代币，用于激励生态建设。为了推动生态发展，社区多次呼吁启动激励计划。

激励计划启动与提案通过:
2023 年 8 月 15 日，Arbitrum 激励计划工作组首次会议由 Camelot、Gauntlet、GMX 等团队组成，并于 9 月 18 日在 Snapshot 上通过了短期激励计划（STIP）的提案。最终，Arbitrum DAO 在 Tally 上通过了该提案，决定分配 5000 万 ARB 代币（约合 4100 万美元），用于激励项目，资金将于 2024 年 1 月 31 日前分配。

资金分配与投票机制:
此次激励计划的资金分配通过两轮投票程序完成：首先是 Snapshot 上的民意投票，接着在 Tally 上进行链上投票。提案获得 99% 的支持后，5000 万 ARB 代币被分配至一个多签钱包，由 DAO 代表管理，进行项目赠款分配。

赠款申请与条件:
短期激励计划的资金分配依据项目在 Arbitrum 上的表现，主要考虑项目的运行时间、TVL（总价值锁仓）和过去 30 天的交易量。申请的项目必须满足明确的支出计划，承诺提供相关运营数据，并完成 Arbitrum 基金会的 KYC 认证。资金只能用于 Arbitrum 网络上的激励，不能转化为其他资产。

项目支持与生态参与:
此次激励计划显示，原生项目如 GMX 等因其高 TVL 和交易量获得更多支持。此外，项目方不仅要确保项目本身的质量，还需积极参与生态活动，如成为多签钱包的代表、治理代表等，这些都能提升项目在 Arbitrum 网络中的影响力，进而增加获得资助的机会。
<!-- Content_END -->
