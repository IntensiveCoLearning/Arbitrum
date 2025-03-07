### Derick
- 参与学习arb，了解代币经济，架构模型
<!-- Content_START -->
### 2024-12-10

- arbitrum是以太坊的L2，基于op rollup搭建的，交易成本低，速度快，目前是L2的领头羊，TVL最高
- Arbitrum Rollup 通过将其作为以太坊的子模块运行来解决这一问题。与常规的 L1 以太坊交易不同，Arbitrum 不要求以太坊节点处理每一笔交易，而是采用“无罪推定”的态度。只有在出现违规时，才会回到 L1 进行争议解决。这种机制使得 Arbitrum 能够高效地处理大量交易，同时保持安全性。
#### 关键特性
- 数据透明性：所有用户的交易数据都会直接发布到以太坊上，确保任何人都能验证 Arbitrum 上的活动。
- 验证者角色：负责推动 Arbitrum 链状态的参与者称为验证者。任何人都可以成为验证者，只需运行开源软件并在必要时质押以太币。
- 欺诈证明：如果发生争议，验证者之间会进行互动游戏，以确定哪个验证者是诚实的，最终通过执行一个简单的计算步骤来证明真相。
### 2024-12-11
- 学习rollup概念 什么是ZK Rollups  
- ZK Rollups, ZKSnark 或者叫Zero Knowledge Rollups，顾名思义，通过零知识证明验证来进行Rollups环节。
- 零知识证明，也是区块链公链项目Algorand的创始人Silvio Micali在密码学的主要贡献之一。
- ZK的四大特点：
1. Zero Knowledge: 验证者无需看到交易所有数据 
2. Succinct: 言简意赅的，简练的
3. Non-Interactive: 无需知道验证者是谁
4. Argument of Knowledge: 证明交易的真实性与正确性

ZK Rollups与Optimistic Rollups是以太坊的两种主要扩展解决方案，它们在技术实现和机制上存在显著差异。

## 基本概念
**ZK Rollups**（零知识卷积）使用零知识证明（如zk-SNARKs）来验证交易的有效性，而不需要透露交易的具体内容。这种方法允许将大量交易压缩成一个单一的证明，提交到主链，从而提高隐私性和效率。

**Optimistic Rollups**（乐观卷积）则假设所有提交的交易都是有效的，只有在有人提出质疑时才会进行验证。这种机制依赖于防欺诈措施，允许在链外处理交易，减少了对链上计算的需求，但可能会引入延迟，因为存在一个质疑期。

## 主要区别

| 特征                     | ZK Rollups                                      | Optimistic Rollups                             |
|------------------------|------------------------------------------------|------------------------------------------------|
| **验证机制**            | 使用零知识证明进行交易验证                     | 假设所有交易有效，依赖质疑机制进行验证          |
| **隐私性**              | 高，交易细节不被公开                           | 较低，交易细节可能被公开                       |
| **交易确认时间**        | 快速，因可立即验证                             | 可能较慢，因为需要等待质疑期                   |
| **复杂性**              | 需要高级密码学知识和资源来生成证明            | 相对简单，更易于集成                           |
| **适用场景**            | 适合需要高安全性和隐私性的应用                 | 适合对延迟不敏感且希望简化集成的应用           |

## 优缺点

### ZK Rollups
- **优点**：
  - 高隐私性和安全性
  - 快速的交易确认
- **缺点**：
  - 实现复杂，需要较高的技术门槛

### Optimistic Rollups
- **优点**：
  - 易于集成，适合现有以太坊应用
  - 降低链上计算需求
- **缺点**：
  - 可能面临延迟
  - 安全性依赖于质疑机制的有效性


### 2024.12.12
### 什么是欺诈证明（Fraud Proof）？

**欺诈证明（Fraud Proof）** 是一种用于检测区块链中欺诈行为的机制。在区块链系统中，当某个参与者（比如一个验证者或节点）提交一个无效的区块或交易时，其他节点需要能够证明这个区块或交易的错误，从而维护区块链的完整性和安全性。简单来说，欺诈证明是一个手段，用于证明某个区块的计算结果（或交易状态）是错误的，进而确保网络中恶意行为者无法轻易地伪造交易或篡改状态。

### Arbitrum中的欺诈证明

Arbitrum 是以太坊的二层扩展解决方案（Layer-2），它采用了**Optimistic Rollups**技术。在这种技术中，大部分交易是通过计算链外（off-chain）执行的，然后将执行结果（即区块）提交到以太坊主链。Arbitrum 假设所有提交的交易状态是正确的，只有在出现争议时才会进行验证。这种“乐观”假设使得系统能够更高效地处理交易和状态更新。

### 如何在 Arbitrum 中使用欺诈证明？

1. **交易执行**：
   Arbitrum 基于OP Rollup模型，首先将交易在L2上执行，生成交易状态的变更（包括数据、账本状态等），并将这些变更提交给以太坊主链。这个提交的过程是乐观的，假设提交的结果是正确的。

2. **欺诈证明的挑战**：
   任何人（称为挑战者）都可以挑战这些提交的交易。具体来说，当某个验证者认为提交的状态不正确（例如，存在计算错误或恶意操作时），他们可以提出一个**欺诈证明挑战**，请求重新验证某个区块或交易。

3. **挑战管理（Challenge Manager）**：
   Arbitrum 使用一个名为 **Challenge Manager** 的系统来管理和执行欺诈证明。这个系统使用了一种叫做 **bisection protocol**（二分法协议）的机制来逐步验证交易的正确性。在这个过程中，挑战者和被挑战者轮流提交每一步的计算结果，从而逐渐缩小问题的范围。

4. **处理与判定**：
   在挑战的过程中，如果欺诈证明成功（即发现了错误），挑战者可以成功推翻错误的区块，并防止错误的状态被纳入以太坊主链。如果挑战失败，则状态提交被认为是有效的，提交者将继续进行操作。

5. **自动化回退机制**：
   Arbitrum 中的欺诈证明并不会立即改变状态，而是通过回退机制（比如超时或者一定数量的验证期）来避免系统迅速做出错误的判断。这种回退机制有助于解决恶意参与者提交的无效状态问题。

### 欺诈证明的作用

1. **增强安全性**：
   欺诈证明提供了一个强大的安全保障机制，确保在OP Rollup模型下，即便有恶意行为者提交无效的状态，系统也能有效地识别并撤销这些错误。通过欺诈证明，Arbitrum 能够保持高效的状态更新，同时保障链上数据的准确性。

2. **降低交易成本**：
   因为 Arbitrum 的OP Rollup假设大多数提交的状态是正确的，系统不会立即进行每个交易的完整验证。只有在出现欺诈行为时才会启动额外的验证过程，这大大降低了交易的计算和验证成本。

3. **提高吞吐量**：
   通过将大部分计算转移到链外执行，并通过欺诈证明机制只对有争议的部分进行验证，Arbitrum 能够有效提升以太坊网络的吞吐量。与传统的区块链系统不同，Arbitrum 允许通过更少的计算资源处理更多的交易。

4. **去中心化与公平**：
   欺诈证明的机制确保了任何人都有机会挑战不正当的区块，这使得系统具有去中心化的特点，并防止单个或少数节点通过提交错误的区块来操纵网络。

5. **减少依赖于信任**：
   由于欺诈证明要求所有提交的区块都可以被后期验证，这减少了对单一中心化实体的信任要求。在 Arbitrum 网络中，虽然执行和计算是由少数验证者处理，但任何人都可以在发现错误时对其进行挑战。
### 2024.12.13
- 请假一天
### 2024.12.14
- 学习arbitrum中one、nitro、nova版本的介绍
### Arbitrum One
Arbitrum One是最初推出的版本，采用了Optimistic Rollup技术。它的主要特点包括：
- **数据可用性**：所有交易数据都以Calldata的形式发布到以太坊主网，这样做虽然确保了安全性，但也导致了较高的交易费用。
- **安全性**：与以太坊主网共享安全性，用户可以放心地控制自己的资产。
- **EVM兼容性**：能够运行未修改的以太坊智能合约。
### Arbitrum Nitro
Arbitrum Nitro是对Arbitrum One的技术栈升级，并不是一个独立的网络。它在2022年8月推出，主要特点包括：
- **性能提升**：通过优化执行过程和数据处理方式，降低了交易费用。
- **更好的兼容性**：Nitro使用WebAssembly（Wasm）作为执行环境，增强了与以太坊的兼容性，使得开发者可以更轻松地迁移合约。
- **交互式欺诈证明**：采用了多轮欺诈证明机制，以提高交易的安全性和效率。
### Arbitrum Nova
Arbitrum Nova是一个独立于Arbitrum One的网络，于2022年8月上线。其主要特点包括：
- **AnyTrust技术**：Nova使用AnyTrust模型，这意味着它将交易数据存储在链下的数据可用性委员会（DAC）中，而不是直接发布到以太坊主网。这种方式显著降低了交易费用。
- **适合高频交互应用**：Nova特别适合游戏、社交应用等需要高频交互的DApp，因为它在性能上进行了优化，但相对牺牲了一定的安全性。
- **两种数据发布方式**：Nova允许以Calldata形式发布完整数据，或通过DACert证明数据的可用性。
### 2024.12.15

#### Nitro的设计理念

Arbitrum Nitro的设计围绕着几个核心理念，旨在提高性能和兼容性，同时保持安全性。以下是Nitro的四个主要设计理念：

1. **排序与确定性执行**：
   - Nitro采用两阶段策略处理交易。首先，将交易组织成一个有序序列，然后通过确定性的状态转换函数逐一处理这些交易。这种方法确保了每个交易的结果是可预测的，任何人都可以根据交易序列计算出结果。

2. **以Geth为核心**：
   - Nitro通过集成流行的以太坊节点软件Geth来支持以太坊的数据结构、格式和虚拟机。这种集成确保了与以太坊的高度兼容性，使得Nitro能够无缝运行未修改的EVM合约。

3. **分离执行与证明**：
   - Nitro将相同的源代码编译两次，一次用于在Nitro节点中执行，优化速度；另一次用于证明，优化可移植性和安全性。这种分离使得Nitro在执行和证明方面都能达到最佳性能。

4. **OP Rollup与交互式欺诈证明**：
   - Nitro使用OP Rollup协议将交易结算到以太坊主链，并引入了交互式欺诈证明机制，以提高交易的安全性和可靠性。

### 2024.12.16
- ARBITRUM的欺诈证明与op的有些不同，具体来说，op是当有挑战者在窗口期发起验证，会统一走一个流程，一直到窗口期结束判定是否是真的欺诈，而arbi是多轮交互，并且机制是挑战者将押金抵押后，由一个合约作为仲裁院，经过断言后可快速验证欺诈证明
- Arbitrum 采用多轮欺诈证明。简单来说，就是通过二分查找，找到引起分歧的那个区块的第一个操作码。找到之后，只需在链上执行这个操作码。

> 纠纷 解决协议的结果是一个参与者将被发现是错误的。这个参与者的押金会被罚没。押注会从所在的方框上删除。部分押金会给到纠纷的另一方，剩下的被烧掉。
当两个质押者押注不同的区块且这两个区块之间没有继承关系时，他们会在某个区块上产生分歧，从而引发挑战。
挑战主要发生在 Arbitrum 链上，由 L1 合约裁决。
挑战包括一个在 L2 上进行的交互型多轮切分游戏和一个在 L1 上执行的单步证明。
如果有质押者对某个区块提出争议，提议该区块的质押者将作为 “被告” 捍卫自己的断言。在切分游戏中，作为 “被告” 的质押者（Alice）为先手，将 N 个指令切分成 K 段，每段的大小是 N/K，且每段都有一个起点和一个终点。
作为 “原告” 的质押者（Bob）同样将 N 个指令切分成 K 段（每段的大小是 N/K），并将它们与 Alice 的切分段一一对应，发现其中一个切分段的终点与 Alice 的不同。
Bob 实际上是在找出他不认同的切分段。
接着，Bob 会执行 Alice 最初的操作，将有争议的切分段（大小为 N/K）再切分成 K 个子段，然后将这个切分段连同子段一起发送给 Alice。
Alice 执行 Bob 最初的操作，找到终点不同的那个子段。
切分流程继续下去，直到 Alice 和 Bob 找到他们产生分歧的那一个指令为止。这个指令被发送给 L1 合约，并由后者执行它，然后决定这场争议的 “胜诉方”。
“败诉方” 将失去质押物，一部分质押物将被销毁（防止攻击者对冲押注），其余则奖励给诚实的 “胜诉方”。
在整个切分流程中，作为裁决方的 L1 合约不知道任何关于指令的信息，只负责核实双方是否遵循游戏规则。
在争议期间，其他所有验证者都能在争议敲定之前自行断定争议的结果，这就意味着会发生软分叉，且验证者可以继续在正确的链上提交 Rollup 区块。
挑战期有一个强制的期限，即，每个质押者大约一周时间。
每个质押者必须在一周的限期内完成自己的任务，否则就会 “败诉”。
多个纠纷可以同时解决，但是每个押注者一次最多只能参与一个纠纷。
### 2024.12.17
- 通过阅读[Your chain,Your rules](https://medium.com/offchainlabs/your-chain-your-rules-offchain-labs-technical-roadmap-to-fuel-arbitrum-innovation-f787f2e85966) 了解他们对于arbi的开发计划，增强开发者体验styuls，增加去中心化排序器，互操作性和可扩展性，零知识证明，增加快速体现功能，允许选定orbit链在更短时间内提现，
- arbitrum nova使用anytrust技术，转为游戏和社交应用设计，可以更快的响应和更好的tps。
### 2024.12.18
- [Arbitrum TVL](https://defillama.com/chain/Arbitrum) 现在是3.257b
- 跨链桥 (Bridges):
1. Arbitrum Bridge: 这是官方的跨链桥，用于在以太坊主网和 Arbitrum 之间转移资产。
2. Hop Protocol: 一个通用的跨链桥协议，支持在多个 Layer-2 网络之间快速转移代币，包括 Arbitrum。
3. Multichain (原 Anyswap): 一个支持多条链的跨链桥，也支持 Arbitrum。
4. Synapse Protocol: 另一个多链桥协议，提供跨链资产转移和交换功能。
5. Celer cBridge: 一个高性能的跨链桥，专注于速度和低成本。
### 2024.12.19
- $ARB 是一种 ERC-20 治理代币，允许其持有者参与 Arbitrum DAO 的链上治理协议。 $ARB 代币由一个位于 Arbitrum One（一个第 2 层 Arbitrum rollup 链）上的智能合约铸造。 Arbitrum DAO 负责管理宪法中定义的治理协议以及 DAO 治理的技术。
- $ARB 的初始供应量为 100 亿。每年最多可以以其供应量的 2% 的速度铸造新的 $ARB，第一次铸造将于 2024 年 3 月 15 日开始。 $ARB 铸造活动由 DAO 通过宪法提案进行。
- $ARB 代币是一种特殊用途的数字资产，赋予其持有者投票权，以影响 Arbitrum DAO 的运营和发展及其治理的技术。持有 $ARB 代币使您能够与其他价值观一致和激励一致的代币持有者一起民主地塑造 Arbitrum 生态系统的未来。
### 2024.12.20
- 请假
### 2024.12.21
- 学习[ARB代币治理](https://docs.arbitrum.foundation/concepts/arb-token)
- $ARB 是一种 ERC-20 治理代币，允许其持有者参与 Arbitrum DAO 的链上治理协议。 $ARB 代币由一个位于 Arbitrum One（一个第 2 层 Arbitrum rollup 链）上的智能合约铸造。 Arbitrum DAO 负责管理宪法中定义的治理协议以及 DAO 治理的技术。$ARB 的初始供应量为 100 亿。
### 2024.12.22
- 代币基本信息
- 代币类型：$ARB是Arbitrum One链上的ERC-20治理代币。
- 初始供应量：100亿个。
- 通货膨胀率：最高2%每年。
- 铸造/销毁机制：通过L2智能合约进行。
- 空投快照区块：在Arbitrum One链的区块58642080（2023年2月6日）。
- 认领开始时间：在以太坊主网的区块16890400（2023年3月23日）。
- 认领结束时间：在以太坊主网的区块18208000（2023年9月24日），此后$ARB不再可认领。
##### 代币分配
根据AIPs 1.1和1.2的通过情况，$ARB的分配如下：
Arbitrum DAO财库：35.28%（35.28亿个）
团队和贡献者 + 顾问：26.94%（26.94亿个）
投资者：17.53%（17.53亿个）
用户（通过空投）：11.62%（11.62亿个）
Arbitrum基金会：7.5%（7.5亿个）
为构建应用程序的DAOs：1.13%（1.13亿个）

### 2024.12.23
- 请假一天
### 2024.12.24
##### 用户空投资格
用户通过一个积分系统来确定可认领的代币数量。主要考虑在Arbitrum One上的活动，同时也包括少量在Arbitrum Nova上的活动。用户在快照日期之前每个合格行为最多获得1点，积分上限为15点。
- 合格行为包括：
在Arbitrum One上：
资金桥接到Arbitrum One
在两个不同月份内进行交易
1. 在六个月内进行交易
2. 在九个月内进行交易
3. 进行超过四次交易或与超过四个不同智能合约互动
4. 进行超过十次交易或与超过十个不同智能合约互动
5. 进行超过25次交易或与超过25个不同智能合约互动
6. 进行超过100次交易或与超过100个不同智能合约互动
7. 交易总额超过$10,000、$50,000或$250,000
- 在Arbitrum Nova上：
1. 资金桥接到Arbitrum Nova
2. 进行三次、五次或十次以上交易
### 2024.12.25
#### Arbitrum Token Supply 概述

Arbitrum 是一个以太坊扩展解决方案，旨在提高去中心化应用程序（dApps）的可扩展性和效率。其原生治理代币为 ARB，用户可以通过持有 ARB 代币参与 Arbitrum DAO 的治理投票，共同决定协议和链的未来。

### 代币供应情况

- **总供应量**: ARB 的最大总供应量为 9,999,998,977 个代币。
- **流通供应量**: 当前流通中的 ARB 代币约为 4,097,359,817 个。
- **市场数据**: ARB 的市场资本化约为 4,169,696,073 美元，24 小时交易量约为 1,081,347,794 美元。

### 代币分配

ARB 代币于 2023 年 3 月 23 日启动，初始分配的 12.75% 总供应量分配给合格的接收者。ARB 持有者可以将其投票权委托给其他代表，以参与治理。

### 2024.12.26
![image](https://github.com/user-attachments/assets/3e37b7d4-1cd8-4ec2-ac0c-36ae019e583e)
1. 如果在 Hop 协议奖励计划期间发现空投接收者的钱包地址是女巫地址，则将其列入不合格名单。
2. 其他反女巫规则如下：
- 如果空投接收者的钱包交易全部发生在前 48 小时内，则将扣除一点。如果空投接收者的钱包余额少于 0.005 ETH 且钱包未与多个智能合约互动，则将扣除一点。
- 在 Arbitrum 基金会的官方网站上，用户可以验证他们已达到的要求和他们被分配到的空投。如果想出售他们的 ARB，用户可以考虑集中式交易所（CEX）以及众多的 DEX。多个 CEX，包括币安，ByBit，OKX，KuCoin 等都已宣布将在介绍日上架 ARB。
### 2024.12.27
- 请假一天
### 2024.12.28
Arbitrum DAO的术语表（Glossary）提供了与Arbitrum生态系统相关的关键术语和定义，帮助用户理解其治理结构和操作机制。
## 主要术语及定义

1. **Arbitrum Chain**:
   - 基于Arbitrum协议运行的区块链，兼容以太坊虚拟机（EVM），用于结算和简洁的欺诈证明。

2. **Arbitrum DAO**:
   - 由$ARB代币持有者和代表组成的全球社区，负责治理Arbitrum One和Arbitrum Nova链。

3. **治理提案（Governance Proposal）**:
   - 用于改变Arbitrum DAO治理协议的提案，包括宪法性提案和非宪法性提案。

4. **宪法性提案（Constitutional AIP）**:
   - 一种更严格的提案类型，需要更长的延迟才能生效，涉及对章程的修改。

5. **非宪法性提案（Non-Constitutional AIP）**:
   - 不符合宪法性提案标准的提案，通常处理常规操作或小幅变更。

6. **多签钱包（Multisignature Wallet）**:
   - 需要多个私钥签署交易的钱包，用于安全委员会触发紧急行动。

7. **委托（Delegate）**:
   - 有权投票参与治理提案的人，可以是$ARB代币持有者或被其他持有者委托投票的人。

8. **数据可用性委员会（Data Availability Committee, DAC）**:
   - 负责在Arbitrum AnyTrust协议链中强制执行数据可用性的特定权限方。

9. **链所有者（Chain Owner）**:
   - 有权升级Arbitrum核心协议合约并设置系统参数的实体，包括Arbitrum DAO和安全委员会。

10. **智能合约（Smart Contract）**:
    - 存储在以太坊区块链上的自执行代码，自动化任务和协议。

11. **节点操作员（Node Operator）**:
    - 运行以太坊/Arbitrum生态系统核心协议软件的人，包括以太坊节点和Arbitrum节点。

12. **快照投票（Snapshot Poll）**:
    - 委托可以进行链外投票的一种机制，用于在治理论坛中进行温度检查。

### 2024.12.29
Arbitrum DAO的提案和投票程序是其治理机制的重要组成部分，以下是详细的介绍：
## 提案流程
1. **临时检查阶段（1周）**:
   - 提案者在社区论坛上提出建议，进行讨论和辩论，持续一周。
   - 在此期间，提案者可以在Snapshot上创建投票，以衡量社区对提案的兴趣。

2. **正式提交AIP（3天）**:
   - 经过临时检查后，提案者需通过Arbitrum的治理合约正式提交AIP（Arbitrum改进提案）。
   - 提案者必须拥有至少500万$ARB的代币。

3. **DAO投票阶段（14-16天）**:
   - Arbitrum DAO成员将在链上对提交的AIP进行投票。
   - 提案通过的条件包括：
     - 赞成票数超过反对票数。
     - 赞成票占投票代币的特定比例：宪法性提案需达到5%，非宪法性提案需达到3%。
## 投票方式
- **直接投票**: 代币持有者可以直接参与投票。
- **委托投票**: 代币持有者可以将自己的投票权委托给代理人。代理人是被选举出来代表其他代币持有者行使投票权的成员。委托后，持有者可随时撤销委托并收回投票权。

## 投票工具
- **Tally平台**: Arbitrum DAO使用Tally作为去中心化治理工具，用户可以通过该平台进行委托和投票操作。

### 2024.12.30
Arbitrum 的安全委员会成员页面提供了有关安全委员会结构、成员及其职责的详细信息。
## Arbitrum 安全委员会概述
### 1. **安全委员会的角色**
- **职责**: 安全委员会负责确保 Arbitrum 网络的安全性和完整性。它能够在紧急情况下快速采取行动，绕过常规的投票流程，以保护网络免受潜在威胁。
- **组成**: 安全委员会由 9 至 12 名成员组成，这些成员通过多重签名钱包进行管理。
### 2. **成员选举**
- **选举机制**: 安全委员会的成员由 Arbitrum DAO 定期选举产生，确保委员会的代表性和去中心化。
- **当前成员**: 页面列出了现任安全委员会成员的地址和相关信息，反映了社区对安全管理的重视。
### 3. **决策流程**
- **紧急决策**: 在发生安全事件时，安全委员会可以迅速做出决策，执行必要的措施以保护网络。
- **投票机制**: 委员会成员需要达到一定数量（如 9 名）才能通过紧急决策，确保决策的有效性和代表性。

### 4. **与 DAO 的关系**
- 安全委员会与 Arbitrum DAO 紧密合作，确保治理过程中的安全考虑得到充分体现。DAO 成员可以对安全委员会的操作进行监督，并提出改进建议。

- Arbitrum 的安全委员会是维护网络安全的重要机构，通过定期选举和多重签名机制确保去中心化与高效决策。其主要职责是在紧急情况下保护网络，并与 Arbitrum DAO 协作以增强治理结构的安全性。

### 2024.12.31
<!-- Content_END -->
