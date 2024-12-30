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

# {Qy}

1. 自我介绍：Qy
2. 你认为你会完成本次残酷学习吗？：yes

## Notes

<!-- Content_START -->

### 2024.12.10

1.我们可以用以太坊来证明Arbitrum上的欺诈行为吗？但如果发生欺诈行为，我们能绝对确定能够证明这一点吗？
      是的，我们确实可以。这就是“rollup”部分的用武之地。输入 Arbitrum Rollup 链的数据（即用户的交易数据）直接发布在以太坊上。因此，只要以太坊本身安全运行，任何感兴趣的人都可以了解 Arbitrum 中正在发生的事情，并且有能力检测和证明欺诈行为。

2.听起来 Arbitrum Rollup 是解决所有扩展问题的理想解决方案？
      Arbitrum Rollup 非常棒而且很酷；它的设计主要是为了避免引入任何中心化或信任假设，因此对于以太坊生态系统来说这是一个明显、严格的净赢。然而，去中心化是有代价的，并不是所有应用程序和用户都一定希望或需要付出这个代价。对于具有不同安全考虑的 dapp 用例，Arbitrum 套件中的不同工具都是合适的；即 Arbitrum AnyTrust 链！

### 2024.12.10

### 2024.12.11

1.Arbitrum是一套以太坊扩展解决方案，可以轻松构建和使用去中心化应用程序。本文档提供了 Arbitrum 套件的高级概述以及针对特定受众量身定制的入门指南。

2.用户可以通过 Arbitrum 桥或使用已部署到 Arbitrum 链的 dApp 与 Arbitrum 进行交互。

3.开发人员通过将智能合约部署到 Arbitrum 链来构建 Arbitrum dApp。

4.链运营商使用 Arbitrum Orbit 来运行专用 Rollup 和 AnyTrust 链。


### 2024.12.11

### 2024.12.12

1.将智能合约部署到 Arbitrum One 主网。现在我们已经验证了我们的智能合约可以在 Arbitrum 的 Sepolia 测试网上运行，我们准备将其部署到 Arbitrum One 主网。这与部署到 Arbitrum 的 Sepolia 测试网的过程相同，只是我们需要以真实的 ETH 美元而不是 ASPL 支付交易费。预计在此步骤中会看到不一致的 $ETH Gas 费 - Gas 和费用部分包含有关如何确定 Arbitrum 交易的 Gas 费的更多信息。

2.以太坊是一个去中心化的节点网络，使用以太坊的客户端软件（如 Offchain 的Prysm ）来维护公共区块链数据结构。以太坊区块链数据结构中的数据一次更改一笔交易。智能合约是根据预定义规则执行交易的小程序。以太坊的节点托管并执行智能合约。您可以使用智能合约构建去中心化应用程序 (dApp)，这些应用程序使用以太坊网络来处理交易和存储数据。DApp 允许用户在应用程序之间携带数据和身份，而无需信任中心化服务提供商。运行以太坊验证器节点3的人可以通过代表用户和 dApp 处理和验证交易来赚取 ETH。当网络负载较重时，这些交易可能会很昂贵。

### 2024.12.12

### 2024.12.13

1.ZK Rollups, ZKSnark 或者叫Zero Knowledge Rollups，顾名思义，通过零知识证明验证来进行Rollups环节。 零知识证明，也是区块链公链项目Algorand的创始人Silvio Micali在密码学的主要贡献之一。
2.Zero Knowledge: 验证者无需看到交易所有数据，Succinct: 言简意赅的，简练的，Non-Interactive: 无需知道验证者是谁，Argument of Knowledge: 证明交易的真实性与正确性。
3.Optimistic的方法如其名字的意思：乐观的，开始认为所有发送的交易都是值得信赖认证过的。Layer 2验证者需要先质押Token作为保证金，如果验证过程中，别人发现了有问题的打包，那么该验证者（Sequencer）将被罚款部分Token，并把其作为奖励给与发现问题的人。每次数据打包后，会有验证期，以供其他验证者检查是否有问题，是否需要重新退回打包。Optimistic Rollups也具有智能合约功能，可以拥有相应的治理Token。
### 2024.12.13

### 2024.12.14

1.Rollup指的是一种整理方法，把一堆交易任务送到Layer2协议去打工，从而提升以太坊的运行效率。
2.Zk Rollups是指一种利用零知识证明的密码学算法，在无需知道验证者是谁的情况下，完成外包工作的Layer2方法。
3.Optimistic Rollups是指利用一堆验证者，在默认打包是好的情况下，通过奖惩机制，监督发掘是否有Bug的Layer2方法。
4.Optimism和Arbitrum都是Optimisctic Rollups方法为基础开发的项目。
5.Zksync, ZKxxxxxxx很多ZK，都是以ZK Rollups方法为基础或噱头，开发的项目。

### 2024.12.14

### 2024.12.15

1.就以太坊而言，大 gas 容量的 Arbitrum 交易的唯一缺点是它可能需要运行更多的交互步骤（这个也仅仅是在有所争议的情况下）。相反，重执行模式下的 rollup 交易，gas limit 必须小于以太坊的区块 Gas Limit，否则就没法在一笔以太坊交易内模拟执行完这笔交易了（而且模拟执行比起在以太坊中直接执行，gas 消耗量还要更大）。

2.合约大小没有限制：交互式证明无需为每一个 L2 合约创建一个以太坊合约，所以也不要求合约符合以太坊合约的限制。对于 Arbitrum 的争议合约来说，在 L2 上部署一个合约的操作也是一系列计算过程的组合，与别的操作没有区别。相反，重执行模式下，L2 合约的大小比以太坊主链上所能容许的还要小，因为要模拟一个合约的执行需要能够仿制（instrument）这个合约，而仿制的代码必须能够放进一个以太坊合约内。

### 2024.12.15

### 2024.12.16



### 2024.12.16

### 2024.12.17

Nitro 代表了 Arbitrum 技术发展的最新一步；它是首次在主网 Arbitrum One 链上发布的技术堆栈的升级版，我们现在将其称为“Arbitrum Classic”（并且比2018 年最初的 Arbitrum 白皮书中描述的要高出几步）。在这里，我们将解释 Nitro 升级背后的理由，并概述 Nitro 相对于经典系统的核心优势。从远处看，Classic 和 Nitro 系统做类似的事情：都试图创建一个尽可能接近 EVM 的执行环境，作为以太坊的第二层运行；也就是说，L2 虚拟机状态更新的安全性可以通过以太坊本身的简洁欺诈证明来保证和执行。在 Arbitrum Classic 中，这是通过定制的虚拟机实现的，我们称之为 Arbitrum 虚拟机 (AVM)。Arbitrum 的 L2 状态机的实现（称为“ArbOS”）实际上是一个编译并上传到 AVM 的程序；ArbOS 包括（除其他功能外）模拟 EVM 执行的能力。在 Nitro 中，我们使用 WebAssembly (Wasm)，而不是使用 AVM 执行低级指令。由于 Go 代码可以编译为 Wasm，因此我们可以用 Go 实现 ArbOS 程序，并在其中（作为子模块）包含Geth 本身，这是最广泛使用的以太坊实现。这种架构（可直接使用 Geth 的 EVM 实现）是 Nitro 的定义性特征，也是我们谈论“Nitro”时主要谈论的内容。Nitro 的大部分优势都是这种设计选择的直接或间接结果。我们可以将这些优势总结如下：费用更低、以太坊兼容性更好、简单易用。

### 2024.12.17

### 2024.12.18

Stylus 是 Arbitrum 开发的支持多语言构建应用程序的开源 SDK 。这是一种实现 EVM+ 兼容性的产品。简言之，开发人员在 Arbitrum 上既能使用传统 Solidity 语言，又能使用 WASM 兼容的语言，如 Rust、C 和 C++ 等来构建应用程序。此外，Stylus 使 Dapps 的执行更加高效，显著地降低了 gas 成本。Stylus 不局限于支持 Rust、C 和 C++, 例如 Move、Sway、Cairo 和 Go 等。试想下，以后 Aptos/ Fuel/ StarkNet 上的 dApps 能一键迁移至 Arbitrum 上。甚至可以通过 Arbitrum Orbit 实现一键 L3 链的链改。更有趣的是，BOLD、Stylus 都是通用的模块化组件；开发者基于 Arbitrum Orbit 启动特定用例的 L3，可以原生集成 BOLD、Stylus；也可以通过去中心化 DAO 治理的形式，在 L3 启动并平稳运行后再投票决定集成上述模块化组件。

### 2024.12.18

### 2024.12.19

1.Arbitrum Nova 是基于 AnyTrust 技术搭建的新链，专为游戏、社交应用程序和对成本更敏感的用例而设计。Nova 提供了 2 种数据发布方式，一种是像 Nitro 一样以 Calldata 的形式发布完整数据，另一种是发布 DACert 证明数据的可用性。
2.Arbitrum Orbit 是一个开发框架，允许用户使用任何基于 Arbitrum Rollup 的 L2 网络作为结算层来创建和启动 L3 网络。借助 Arbitrum Orbit，用户可以在隐私、权限、费用代币、治理等方面定制自己的链。Orbit 链为最终用户提供专用吞吐量、流量隔离和 Gas 价格可靠性，从而允许快速迭代特定领域的机制设计和价值捕获机会。
3.BOLD 是 Arbitrum 团队提出的无需许可验证机制，目的是最小化结算状态的延迟。

### 2024.12.19

### 2024.12.20

 Arbitrum Nitro 是为所有基于 Arbitrum 的链提供支持的节点软件，并基于Geth构建，Geth 是 L1 以太坊执行规范的 Golang 实现。自Arbitrum Nitro 于 2022 年 8 月 31 日首次亮相以来，许多新的执行层 (EL) 客户端实现已经启动或显着改进 - 所有这些都具有不同且独特的价值主张和优化目标。随着这些替代客户端的稳定性和质量的提高，Offchain Labs 一直致力于准备 Arbitrum 堆栈以支持替代客户端。

### 2024.12.20

### 2024.12.21
Paradigm 新发布的 Reth 1.0 、 Erigon 3.0和Nethermind ，目标是在 2025 年提供可投入生产的多客户端实施，并简化在网络中添加其他客户端的流程。路。尽管我们当前的分析表明，一些替代客户端在一些性能基准测试中仍然落后于 Geth，但我们认为，随着这些客户端的进一步优化，为 Arbitrum 采用做好准备是明智的做法。
### 2024.12.21

### 2024.12.22
Arbitrum One 于 2022 年 8 月下旬采用了 Arbitrum 的 Nitro 技术堆栈。Nitro 没有依赖定制的 Arbitrum 虚拟机进行低级代码组装，而是使用 WebAssembly (Wasm)。这一变化允许 rollup 直接使用 Go Ethereum 的 EVM 实现，并对应于更低的费用、更好的以太坊兼容性和更大的简单性。
### 2024.12.22

### 2024.12.23

1.Mosaic 是 Composable Finance 的跨层资产转移系统，使用流动性管理和即时（JIT）流动性机器人来利用现有的桥接基础设施网络，用作连接多个 EVM 兼容扩展解决方案的桥梁，允许用户在以太坊、Polygon、Arbitrum、Avalanche、Moonriver 和 Fantom 之间无缝转移代币。
2.Jones DAO：针对期权的收益、策略和流动性协议，主要机枪池（Primary Jones Vaults）产品允许用户将基础资产存入后获得收益率资产代币 jAssets 来代表其存款，在一定的时间窗口后可以通过销毁 jAssets 来提取原基础资产并获得收益，另一方面，Vaults 将寻求尽量规避风险和获得稳定收益，大部分资金将用于通过持有备兑看涨期权来赚取收益，最高 5% 的资金会用于通过购买看涨期权、看跌期权或永续期权进行对冲。Jones Vaults 可能会通过跨平台期权套利来锁定少量无风险收益。

### 2024.12.23

### 2024.12.24

Arbitrum DAO是一个基于以太坊区块链的去中心化自治组织 (DAO)。Arbitrum DAO 的核心是一种社区驱动的治理机制，允许$ARB代币持有者对该组织及其管理的技术的变更提出建议并进行投票。
Arbitrum DAO 的治理智能合约在Arbitrum One Rollup 链上实现，这是以太坊区块链的第 2 层扩展解决方案。这些智能合约包括 DAO 的治理代币 $ARB。DAO 成员使用 $ARB 代币对 Arbitrum DAO 提案 ( AIP ) 进行投票。任何给定投票者的投票权重与他们持有（或代表）的 $ARB 数量成正比1。
Arbitrum DAO 拥有内置的财务系统（以智能合约的形式实现）；DAO 的财务用于资助组织及其技术的持续开发和维护。代币持有者可以提议并投票决定如何使用财务资金。
Arbitrum DAO 还内置了一个安全机制，称为“安全委员会”。安全委员会是一组实体，负责确保 DAO 及其链的安全性和完整性。如《宪法》所述，理事会可以绕过缓慢的投票过程，并在发生安全紧急情况时迅速采取行动。安全委员会成员由 DAO 通过半年选举产生。
总体而言，Arbitrum DAO 是一个强大的工具，可促进 Arbitrum 生态系统的去中心化治理和社区驱动管理。通过持有 $ARB 代币并参与治理过程，个人可以直接影响 Arbitrum 乃至以太坊的未来。

### 2024.12.24

### 2024.12.25

1.Arbitrum 不是唯一的可用于以太坊区块链的第二层解决方案，但是您可能已经猜到，Arbitrum 是最好的。像 Polygon 和 Optimism 这样的解决方案提供了一些好处，但不如 Optimistic Rollup 以及更重要的是可扩展性提升和隐私特性。
2.在 Arbitrum 基金会的官方网站上，用户可以验证他们已达到的要求和他们被分配到的空投。如果想出售他们的 ARB，用户可以考虑集中式交易所（CEX）以及众多的 DEX。多个 CEX，包括币安，ByBit，OKX，KuCoin 等都已宣布将在介绍日上架 ARB。

### 2024.12.25

### 2024.12.26

为在Arbitrum生态系统中构建应用程序的DAO以及协议协会(以太坊贡献者的集合)分配了单独的分发。在制定这些标准的过程中，我们与Nansen合作，分析了链上数据，以确定每个DAO社区被授予多少令牌。在此过程中，我们考虑了各种定性和定量指标，包括协议何时启动、是本地协议还是多链协议、有多少TVL、活动、交易量、交易价值，以及维护这些指标的一致性。使用多种标准的目的是认识到Arbitrum是具有不同KPI和用户交互的各种项目的所在地。

### 2024.12.26

### 2024.12.27

本章程描述了ArbitrumDAO管理和(或)授权ArbitrumDAO批准的链的决策框架。Dao可以授权创建使用仲裁技术安置到以太坊的附加第2层链，但是每个这样的附加第2层链必须由对应的AIP授权(即，在每个AIP中可以授权不超过一个链)。经如此授权的任何链可受$ARB代币和本章程的管辖，在这种情况下，该链将被视为受管辖链。任何已授权但不受$ARB令牌控制的链都将被视为非受控链。为免生疑问，任何ArbitrumDAO批准的链(无论是受控链还是非受控链)必须在以太坊进行结算。使用ArbitrumDAO批准的链(即，作为“第3层”)的Arbitrum技术的链不需要ArbitrumDAO授权。

### 2024.12.27

### 2024.12.28

紧急行动：
安理会有权立即执行任何软件升级或采取其他必要行动，以应对可能发生的安全紧急情况（此类行动称为“紧急行动”）。执行任何紧急行动均需获得安理会9/12 的批准。除非发生真正的安全紧急情况，例如可能严重损害 ArbitrumDAO 所管理链的完整性、机密性或可用性的严重漏洞，否则安理会不得使用其权力执行紧急行动。
在采取任何紧急行动后，安理会必须发布一份全面透明的报告（在安全紧急情况过去后的适当时间），解释所采取的行动以及采取此类紧急行动的合理性。
ArbitrumDAO 能够通过批准和实施宪法 AIP 来限制或消除安全理事会执行紧急行动的权力。

非紧急行动：
安全理事会还可在非紧急情况下批准和实施常规软件升级、常规维护和其他参数调整（此类行动，简称“非紧急行动”），这些行动需要9/12 的批准才能生效。任何非紧急行动经安全理事会批准后，将绕过 AIP 流程的第 1 至 3 阶段，而直接进入 AIP 流程的第 4 至 7 阶段，以便在部署任何非紧急行动之前提供延迟。安全理事会可选择在部署前指定额外的延迟。
ArbitrumDAO 能够通过批准和实施宪法 AIP 来限制或消除安全理事会执行非紧急行动的权力。

### 2024.12.28

### 2024.12.29

1.一系列智能合约负责在Arbitrum One和以太坊之间桥接$ARB。$ARB 代币是 Arbitrum One 的原生代币，这意味着它是在 Arbitrum One 链上的智能合约中铸造的。“反向”网关将全部 $ARB 供应托管在 Arbitrum One 中，并在存款/取款时铸造或销毁第1 层 (L1)代币表示。反向网关通常与标准代币网关进行比较，后者在第 2 层 (L2)上铸造/销毁。
2.Arbitrum 协议通过一组获得许可的参与方（称为数据可用性委员会 (DAC)）来管理数据可用性。该协议通过引入额外的数据可用性信任假设来代替以太坊的无需信任数据可用性机制，从而降低了交易费用。Arbitrum Nova是 AnyTrust 链的一个示例；Arbitrum One是实现纯粹无需信任（且 L1-gas 密集度更高）的Arbitrum Rollup 协议的替代链。

### 2024.12.29

### 2024.12.30

1.DAO 的成立：Arbitrum DAO（去中心化自治组织）是一个新实体，对 Arbitrum One 和 Arbitrum Nova 链及其底层协议拥有决策权。该 DAO 受Arbitrum DAO 宪法的管辖，该宪法是一套描述 DAO 如何运作的规则。宪法载于 Arbitrum DAO 用于管理自身及其技术的一系列社会契约中。
2.治理代币发布：治理代币的所有权代表 DAO 内的成员资格。代币持有者可以对 DAO 提案进行投票。Arbitrum 的治理代币是$ARB，并将通过即将到来的空投分发到符合条件的钱包地址。
3.代码：DAO 治理通常由一系列开源智能合约来促进，这些合约执行特定的决策协议。这些无需信任的智能合约用于逐步取代传统董事会的可信社会合约。Arbitrum DAO 使用智能合约来编纂《Arbitrum DAO 宪法》中阐明的决策协议。

### 2024.12.30

### 2024.12.31

### 2024.12.31

<!-- Content_END -->
