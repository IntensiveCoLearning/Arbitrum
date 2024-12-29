---
timezone: Asia/Shanghai
---

# Kylin

1. 自我介绍<br>
web3开发新手；从hackquest了解到Ethereum，Solana，Arbitrum的开发；对Layer2更感兴趣。
2. 你认为你会完成本次残酷学习吗？<br>
  Y
## Notes

<!-- Content_START -->

### 2024.12.10
**What:**<br>
Arbitrum 是一套旨在扩展以太坊的技术方案，允许用户以更低的费用和更快的速度执行在以太坊上的操作，如使用 Web3 应用和部署智能合约。<br>
Arbitrum 的旗舰产品是 Arbitrum Rollup，一个继承了以太坊安全性的 Optimistic Rollup 协议。<br>

**Why:**<br>
以太坊本身的交易处理能力有限，每秒只能处理大约 20-40 笔交易（TPS），导致用户在交易量高峰时需要竞争交易被打包的机会，从而推高了交易费用。<br>

**How:**<br>
 Arbitrum Rollup 链作为以太坊的一个子模块运行，不要求以太坊节点处理每笔 Arbitrum 交易，而是采用“乐观假设”机制，即默认 Arbitrum 上的活动遵循规则，除非有人提出异议。在争议中，两个验证者通过一个交互式的游戏来缩小争议到一个单一的计算步骤，该步骤在 L1 上执行，以证明诚实方说的是真话。<br>
Arbitrum Rollup 链的数据直接发布在以太坊上，确保了安全性和透明度。交易数据以压缩形式发布在 L1 上，进一步减少了交易的 L1 占用空间。<br>
Arbitrum 强调与以太坊的兼容性，用户可以使用他们喜欢的以太坊钱包，开发者可以使用他们喜欢的以太坊库和工具来构建和部署合约。Arbitrum 使用 Geth 的分叉（Nitro）来实现这一点，使得 Arbitrum 中运行的大部分代码与以太坊相同。<br>
Arbitrum 的最新技术堆栈 Stylus 保持了 Nitro 的以太坊兼容性，并增加了新功能，如使用 Rust、C++ 等编程语言编写高性能智能合约的能力。<br>
对于不需要完全去中心化的应用程序，Arbitrum 提供了 AnyTrust 链，这种链在正常情况下将数据保存在链下，只有在争议发生时才会回到“rollup模式”，这样可以显著降低用户的费用。<br>
 Arbitrum 技术支持多条链并行运行，目前以太坊主网上有两条 Arbitrum 链：Arbitrum One（Rollup 链）和 Nova（AnyTrust 链），用户和开发者可以根据他们的安全和交易成本需求选择。<br>

### 2024.12.11
Arbitrum 提供了多种 Layer 2 解决方案，以提高以太坊的可扩展性和降低交易成本：<br>

**Arbitrum One:**<br>
- Optimistic Rollup：通过在链下执行交易并仅将交易数据发布到以太坊主链上，实现高吞吐量。<br>
- Nitro 升级：引入 WASM 和 Geth，优化交易批处理和压缩，提升性能和降低成本。<br>

**Arbitrum Nova：**<br>
  AnyTrust 技术：依赖数据可用性委员会管理链下数据，减少信任需求，提高用户体验，省去了长时间的提币等待期。
  
**Arbitrum Stylus：**<br>
新编程环境：支持使用 Rust、C++ 等语言开发智能合约，增强性能。<br>

**Arbitrum Orbit：**<br>
自定义专用链：允许创建具有自定义隐私、权限和费用代币的专用链。<br>

### 2024.12.12
#### Rollup
Rollup是一种技术，用于提高以太坊网络的交易处理能力（TPS）和降低交易成本。它通过将多笔交易在链下（Layer 2）进行批量处理，然后将结果（压缩数据）发布回以太坊主链（Layer 1）。这样可以减少主链的负担，提高效率。<br>

#### ZK Rollups
ZK Rollups（Zero Knowledge Rollups）是一种使用零知识证明技术的Rollup方案。它允许在Layer 2上进行交易验证，而无需将所有交易数据发布到主链。<br>
零知识证明允许验证者在不透露交易细节的情况下验证交易的有效性。
ZK Rollups的特点包括：
- Zero Knowledge：验证者无需看到交易所有数据。
- Succinct：数据简洁。
- Non-Interactive：无需知道验证者是谁。
- Argument of Knowledge：证明交易的真实性与正确性。

ZK Rollups适合需要快速结算的业务，如支付和交易所，但算法复杂，对应用开发有一定门槛。

#### Optimistic Rollups
Optimistic Rollups是一种Rollup方案，它默认所有交易都是有效的，除非有人提出异议。如果有人发现欺诈行为，可以通过挑战机制来解决。<br>
Optimistic Rollups的特点包括：
- 乐观假设：默认所有交易都是有效的。
- 挑战机制：如果发现问题，可以通过挑战来解决。

Optimistic Rollups适合开发Dapp和DeFi应用，但提币回Layer 1的速度较慢。

#### Arbitrum
Arbitrum是一种基于Optimistic Rollups的Layer 2协议，它通过多轮欺诈证明来增强安全性，并拥有自己的虚拟机，更加兼容以太坊网络。<br>
Arbitrum与Optimism的主要区别在于它进行多轮欺诈证明，并且交易计算不依赖Layer 1。

### 2024.12.13
围绕 optimistic rollups，最主要的设计抉择是，如何解决争议。假设 Alice 断言 Rollup 会的运行会产生某个结果，而 Bob 不同意，那协议该如何定夺，选择谁提交的结果呢？
处理的方法基本可分两类：交互式证明，或者重执行交易。
#### 交互式证明
交互式证明的思路是让 Alice 和 Bob 参与一个由 L1 合约引导的回合制协议，使用任何 L1 合约所需的最小开销来解决他们之间的分歧。<br>
Arbitrum 的方法基于对争议的剖析。如果 Alice 的断言涉及了 N 个执行步骤，那就让她曝光出两个各涉及 N/2 个步骤的断言，然后让 Bob 选择一个来挑战。这样一来，争议的规模就缩小了一半。<br>
这个过程持续进行，每一回合都将争议的规模缩小一半，直到争议的范围变成一个执行步骤。注意，直到此时为止，L1 引导合约都不必考虑实际上执行了什么。仅当争议被缩小到单个执行步骤时，L1 引导合约才需要理解这一步要执行什么指令，以及 Alice 对该步的断言是否为真，以此解决争议。<br>
交互式证明背后的关键原理是，如果 Alice 和 Bob 有所争议，Alice 和 Bob 应尽可能做链下的工作来解决争议，而不是让 L1 合约承担负担。 <br>
**重执行交易**
让一个 Rollup 区块在区块内每一笔交易后附带一个状态哈希值断言。然后，在争议情形中，L1 引导合约将模拟一整笔交易的执行，看结果是否与 Alice 的断言一致。
#### 优势
- 效率更高
乐观情况下，一个区块只需要包含一个断言，空间占用小，节省成本。
悲观情况下，引导合约只需要执行一个步骤即可验证争议，速度快
- 更高的交易级 gas limit
交互式证明的 gas limit 相较于 Ethereum 要大得多，重执行证明受限于 Ethereum 的 gas limit，可能没办法在一笔交易内模拟执行完
- L2 上的合约大小没有限制
交互式证明不需要为 L2 合约在 Ethereum 上创建对应合约，所以不受限制；重执行模式的 gas limit 必须小于 Ethereum 合约的 gas limit（因为模拟执行的 gas limit 消耗更大）
- 灵活性
举个例子，EVM 中新增指令，必要的功能无非是能在以太坊上验证一个单步执行的证据。而重执行模式就严格受限于 EVM

### 2024.12.14
ChallengeManager 在 Fraud Proofs 系统中扮演着仲裁挑战游戏的角色，其主要功能和流程如下：

1. **区块挑战（Block challenge）**：
   - 挑战开始时，系统会对全局状态（包括区块哈希）进行二分查找（bisecting）。在对实际机器执行产生争议之前，争议会被缩小到单个区块。
   - 一旦挑战被缩小到单个区块，当前响应者可以调用 `challengeExecution`。这个过程类似于二分查找，响应者必须提供一个竞争性的全局状态和机器状态，但这些信息用于过渡到执行挑战阶段。

2. **执行挑战（Execution challenge）**：
   - 一旦挑战被缩小到单个区块，实际的机器执行可以被二分查找。一旦执行被缩小到单个步骤，当前响应者可以调用 `oneStepProveExecution`。
   - 响应者必须提供执行机器步骤的证明数据。如果执行该步骤的结果与之前断言的不同，当前响应者赢得挑战。

3. **通用二分协议（General bisection protocol）**：
   - `ChallengeLib` 辅助库包含一个 `hashChallengeState` 方法，该方法对一系列段哈希、起始位置和总段长度进行哈希处理，生成 `ChallengeLib.Challenge` 的 `challengeStateHash`。这些信息足以推断出每个段哈希的位置。
   - 挑战的“度”（degree）指的是段哈希的数量减一。一个段与下一个段之间的距离（以步骤计）是 `floor(segmentsLength / degree)`，对于最后一对段，`segmentsLength % degree` 被加到正常距离上，以确保总距离是 `segmentsLength`。
   - 挑战开始时只有两个段（度为一），这是断言者的初始断言。然后，二分游戏在挑战者的回合开始。
   - 在游戏的每一轮中，当前响应者必须选择一对相邻的段来挑战。通过这样做，他们对对手的主张提出争议，即从第一个段开始执行指定的距离（步数）将得到第二个段。此时，双方同意第一个段的正确性，但对第二个段的正确性持不同意见。
   - 响应者必须提供一个二分查找，起始段等于第一个段，但结束段与第二个段不同。这样做，他们将挑战分解为更小的距离，并轮到对手。

4. **赢得挑战（Winning the challenge）**：
   - 目前，赢得挑战并不是即时的。相反，它只是使当前响应者成为胜者的对手，并设置状态哈希为0。在那种状态下，该方没有任何有效的移动，因此最终会因超时而输掉。这样做是作为一种预防措施，以便如果挑战被错误地解决，还有时间诊断和修复错误，通过合同升级。

### 2024.12.16
**Arbitrum One**
- 架构：结合 L1 和 L2，L1 组件是 EthBridge，负责仲裁和维护收件箱与发件箱。AVM（Arbitrum 虚拟机）作为 L1 和 L2 之间的网关，ArbOS 在 AVM 上运行，确保智能合约在 L2 上执行。
- 存款与提款：通过 L1 的 EthBridge 合约和 L2 的 Custom Gateway 合约进行代币的存入和提取。
- Rollup 类型：多轮交互型 Rollup，通过争议断言（DA）推进虚拟机状态，押注机制和交互式纠纷解决协议确保正确性。

**Arbitrum Nitro**
- 技术升级：Nitro 是 One 的技术栈升级，包括证明程序、以 Geth 为核心、执行与证明分开、交互式欺诈证明的 Optimistic Rollup。
- 无共识机制：Sequencer 公开操作，任何人都可以计算状态转移函数，降低成本。
- Geth 重写：完全支持以太坊的数据结构、格式和虚拟机，提高兼容性。
- 执行与证明分离：使用不同的代码实现执行和证明，提高效率。
- 交互式欺诈证明：首创的证明系统，通过多轮交互确保安全性和正确性。

**AnyTrust**
- 数据可用性委员会：引入委员会存储 calldata 数据，减少主网上的数据量。
- 最小信任假设：至少需要两名诚实成员保证协议运行。
- Nova：基于 AnyTrust 技术的新链，专为成本敏感的用例设计，提供两种数据发布方式。
**Arbitrum L3 战略**
- Arbitrum Orbit：开发框架，允许创建和启动 L3 网络，定制链特性。
- XAI：基于 Arbitrum Orbit 的首条 L3，专注于游戏和计算密集型 AI 模型。
- BOLD：无需许可验证机制，最小化结算状态延迟。
- Stylus：支持多语言构建应用程序的开源 SDK，降低 gas 成本，实现 EVM+ 兼容性。

### 2024.12.17
#### Arbitrum Nitro
**排序 确定性执行**  
此图总结了 Nitro 中如何处理交易。
![image](https://github.com/user-attachments/assets/7b93d2d1-f773-4f32-ac03-0ba50015878d)

用户事务在Nitro链中的处理流程：
- 创建和签名事务：
用户创建事务，并使用他们的钱包进行签名。
用户将签名后的事务发送给Nitro链的Sequencer。
- Sequencer排序：
Sequencer接收事务，并将其按顺序排列。
Sequencer的职责是将接收到的事务放入有序序列，并发布这个序列。
- 状态转换函数：
排序后的事务逐一通过状态转换函数。
状态转换函数根据链的当前状态和下一个事务来更新状态。
状态转换函数会检测并丢弃任何无效的交易。
- 确定性和结果：
状态转换函数是确定性的，意味着其行为仅取决于当前状态和下一个交易的内容。
任何知道交易序列的人都可以通过状态转换函数计算出相同的结果。
- 节点操作：
Nitro节点通过获取交易序列并在本地运行状态转换函数来操作。
这个过程不需要共识机制。
- Sequencer发布序列：
Sequencer通过两种方式发布序列：实时馈送和在L1以太坊上发布的批次。
实时馈送允许订阅者即时接收每个事务的通知。
这种即时通知提供了交易的“软确定性”，因为它依赖于Sequencer保持其承诺。
- 硬性终局：
Sequencer定期将交易批次压缩并发布到L1以太坊链上。
一旦这些以太坊交易在以太坊上具有最终确定性，记录的Layer 2 Nitro交易也将具有最终确定性。
这种最终确定性是“硬性终局”，因为交易的位置和结果是确定性的，任何一方都可以知道。
- 数据压缩：
Sequencer使用名为“brotli”的通用数据压缩算法在最高压缩设置下压缩其批次。

### 2024.12.18
**核心的Geth**
![image](https://github.com/user-attachments/assets/bf008c7d-2117-4a28-9733-240ab4a00d41) 

Nitro 节点软件的结构可以被理解为由三个主要层组成：

- 基础层（Geth核心）
  这一层是 Geth 的核心部分，负责模拟 EVM 合约的执行和维护以太坊状态的数据结构。Nitro 将这部分代码编译为库，并进行了一些必要的小修改以添加钩子。

- 中间层（ArbOS）：这一层是自定义软件，提供了与 Layer 2 功能相关的额外功能，包括解压和解析 Sequencer 的数据批次、核算 Layer 1 的 gas 成本和收集费用以补偿这些成本，以及支持跨链桥功能，比如从 L1 存入以太币和代币以及将它们提回 L1。

- 顶层：主要由节点软件组成，主要来源于 Geth。这一层处理来自客户端的连接和传入的 RPC 请求，并提供运行与以太坊兼容的区块链节点所需的其他顶级功能。

由于顶层和底层严重依赖于 Geth 的代码，这种结构被称为 "geth sandwich"（Geth 三明治），其中 Geth 扮演面包的角色，而 ArbOS 是馅料。

State Transition Function（STF）由底层的 Geth 层和中间层的 ArbOS 层的一部分组成。STF 是源代码中的一个指定函数，隐式包含了该函数调用的所有代码。  
STF 以收件箱中收到的交易字节作为输入，并可以访问以太坊状态树的可修改副本。  
执行 STF 可能会修改状态，并在最后发出新区块的标头（以以太坊的区块标头格式），该区块将被附加到 Nitro 链中。

### 2024.12.19
**执行与证明分开**
Nitro 通过将执行与证明分开来解决实际 rollup 系统中的挑战：  

1. **执行与证明使用相同源代码**：Nitro 对于执行和证明使用相同的源代码，但将它们编译成不同的目标格式，以适应不同的需求。  

2. **编译执行代码**：在编译 Nitro 节点软件以供执行时，使用普通的 Go 编译器生成目标架构的原生代码，这会因不同的节点部署而异。  

3. **编译证明代码**：对于证明部分，状态转换函数(State Transition Function, STF)的代码由 Go 编译器编译成 WebAssembly (WASM)，这是一种类型化、可移植的机器代码格式。然后，WASM 代码经过转换，形成 Nitro 所使用的 WAVM 格式。  

4. **WAVM 的特点**：  
   - **去除未使用特性**：WAVM 移除了 WASM 中一些 Go 编译器不生成的特性，确保这些特性不会出现在转换阶段。  
   - **限制特定功能**：WAVM 不包含浮点指令，将浮点指令替换为对 Berkeley SoftFloat 库的调用，以减少架构间浮点不兼容性的风险。WAVM 也去除了嵌套控制流，将控制流指令转换为跳转。此外，WAVM 避免了执行时间可变的 WASM 指令，通过转换为使用固定成本指令的结构来实现。  
   - **添加操作码**：WAVM 添加了一些操作码以实现与区块链环境的交互，例如读取和写入链的全局状态，从链的收件箱中获取下一条消息，或发出成功结束执行 STF 的信号。  

5. **ReadPreImage 指令和 Hash Oracle 技巧**：  
   - **ReadPreImage 指令**：这是一个新指令，它接受一个哈希 H 和一个偏移量 I 作为输入，并返回 H 原像中偏移量 I 处的数据字节。这个指令只能在原像公开已知且大小小于固定上限（约 110 KB）的上下文中使用，以确保安全。  
   - **Hash Oracle 技巧**：这种技巧涉及存储数据结构的 Merkle 哈希，并依赖协议参与者存储完整的结构，从而支持通过哈希获取内容，这可以追溯到最初的 Arbitrum 设计。  

**Nova** 
![image](https://github.com/user-attachments/assets/ac66f900-ee96-42a5-8cb7-c3ab4417a379)
Nitro 是 One 的技术栈升级，并不是独立于 One 的网络，Nitro 升级后全称还是 Arbitrum One；而22年8月初上线的 Nova 是独立于 One 的网络。  
One/Nitro 跟 Nova 的区别：最核心的不同点是数据可用性，One 的数据可用性在链上（以太坊主网），Nova 的数据可用性在链下（数据可用性委员会 DAC）。  
Rollup 的本质是执行层的分离，把复杂运算转移到链下执行。
One 将完整的数据集以 Calldata 的形式发布到以太坊主网，由于 Calldata 占用了一定的主网区块空间，此操作支付的 gas 费是 One 成本最大的组成部分。
 Nova 提供了 2 种数据发布方式，一种是像 Nitro 一样以 Calldata 的形式发布完整数据，另一种是发布 DACert 证明数据的可用性。  
 Nova 的定序器将完整的数据集同时发送给所有 DAC 的委员会成员，委员会签名后把带有签名的证明返回给定序器，定序器收集到足够多的证明就能将它们聚合并创建有效的数据可用性证明（DACert），然后把 DACert 发布到主网。  
如果定序器没有收集到足够多的证明，Nova 会回退到 Rollup 模式（以 Calldata 形式发布数据到主网）。  
最简单的理解就是：One 把链下执行数据储存在以太坊主网，Nova 把数据存储在链下的数据可用性委员会。  
 相对于 One 而言，Nova 通过牺牲一定的安全性来提高性能，游戏社交类等需要高频交互的 Dapp 适合部署在 Nova 上。  

### 2024.12.20
**Your Chain, Your Rules**  
核心理念：“Your Chain, Your Rules”：强调用户和开发者对区块链的控制权和自我治理能力。  
技术路线图：
- DevEx, UX, and Adoption 
  - Stylus：允许使用 WASM 语言（如 Rust、C 和 C++）开发，超越了以太坊上构建的限制，支持 EVM 并降低 Gas 费用。
  - Arbitrum 纪念日更新：预计在 Arbitrum 纪念日发布重大更新，包括 Arbitrum Stylus 在 Arbitrum One 和 Nova 主网上的上线。
- 去中心化：
  - BoLD（2024年下半年）：提高安全性和去中心化验证，使 Arbitrum 更接近 Stage 2 rollup。
  - 审查超时（2024年下半年）：限制反复审查或排序器离线对 Arbitrum 链的负面影响。
  - 去中心化排序器（预计2025年）：将交易排序的责任分配给更广泛的去中心化网络参与者。
- 互操作性与可扩展性：
  - Arbitrum Orbit：允许开发者自定义他们的链，以适应特定用例。
  - 快速提现（2024年第三季度）：使 AnyTrust 链能够绕过确认延迟，实现快速结算。
  - 链集群（2025年）：通过允许多个 Orbit 链紧密对齐，减少跨链通信时间。
- 性能与效率：
  - 多客户端支持（2025年上半年）：优化区块生产速度，降低硬件成本，提高吞吐量。
  - 自适应定价（2025年上半年）：动态设置 Gas 限制，提高资源利用效率。
- 零知识证明：
  - ZK+Optimistic 混合证明：探索将 ZK 证明集成到 Arbitrum 链中，提供即时确认声明的可选快速路径。
- 未来展望：Offchain Labs 致力于在问题出现之前创造解决方案，推动区块链技术的边界。

### 2024.12.22
**Arbitrum应用生态**  
![image](https://github.com/user-attachments/assets/65fb4e9a-0d01-45a6-849a-2a6aa99bcc77)  
Arbitrum 的应用程序生态系统可以分为两大类：DeFi 和消费者应用程序。在这些生态系统中构建的项目已经采用 Arbitrum 来获得粘性用户群和从以太坊继承的强大安全保证。  
**Defi**  
![image](https://github.com/user-attachments/assets/224abed4-770a-4b7b-971c-d4bfc777a4f9)
DeFi 生态系统已经存在大量竞争，并以其 DEX、借贷和永续合约为基础。

### 2024.12.23  
项目总数与分类：
Arbitrum 生态门户共列出了 170 多个项目，涉及钱包、交易所、支付网关以及桥和跨链项目约 60 个；DeFi 应用近 40 多个，主要分布在衍生品、AMM 和收益优化方面；NFT 市场 3 个，其中 TreasureDAO 占据主导角色；支持 Arbitrum 的工具、基础设施以及节点提供方约 30 个。  
The Arbitrum Odyssey 生态采用计划：  
56 个项目参与生态采用计划，包括 Yield Protocol、Hashflow、Aboard Exchange、tofuNFT、Uniswap、ApeX、1inch、Yin Finance、DODO、Swapr、TreasureDAO、BattleFly、Ideamarket 和 SushiSwap 等，用户通过体验这些项目收集 NFT 以获得最终设计的 arbi-verse NFT。  
出入金/钱包/交易所：    
支持 Arbitrum One 主网的中心化加密交易所包括 Bitget、币安、Bybit、Crypto.com、FTX、火币、KuCoin、MEXC、OKX 等，支持 ETH 或 USDT 的充提。  
支持 Arbitrum One 主网的钱包包括 BitKeep、Coinbase Wallet、MetaMask、DeBank、imToken、MathWallet、Trust Wallet、Zapper、Zerion 等 24 个。  
桥/跨链项目：    
包括 Arbitrum One Bridge（官方桥）、Across Protocol、BoringDAO、Bungee、Multichain、Celer cBridge、Composable Finance Mosaic、Connext、deBridge、Hop、LI.FI、pNetwork、RenBridge、Router Protocol、Rubic、SOCKET、Stargate、Synapse Protocol 等，支持不同网络间的资产转移和兑换。  
DeFi 应用：  
包括衍生品、AMM 和收益优化项目，如 SushiSwap、1inch、Aave、Curve、dForce、Uniswap、Abracadabra、Balancer、Saddle Finance、Beefy Finance、DODO、MCDEX、Yearn Finance、Hashflow 等。  
NFT 市场：  
主要包括 Stratos、tofuNFT、TreasureDAO，其中 TreasureDAO 旗下元宇宙游戏 Bridgeworld 内的 NFT 系列热度偏高。  
工具/基础设施支持：  
包括 Band Protocol、Biconomy、BlockVision、Chainlink、Covalent、DefiLlama、Etherscan、Nansen、Snapshot、Tenderly、The Graph、Truffle Suite 等二十多个。  
节点提供方：  
包括 Alchemy、Ankr、DataHub、GetBlock、Infura、Moralis 和 QuickNode。  
### 2024.12.25
$ARB代币是一种ERC-20治理代币，持有者可以通过它参与Arbitrum DAO的链上治理协议。这意味着持有者可以对影响Arbitrum One和Arbitrum Nova链的提案进行投票，包括链的升级和DAO金库资金的使用。  
Arbitrum DAO负责管理宪法中定义的治理协议以及DAO所管理的技术，包括Arbitrum One和Arbitrum Nova链及其底层协议。 
持有的$ARB代币越多，投票的影响力就越大，因为Arbitrum DAO的智能合约实现了代币加权投票，即投票的力量由选民钱包中的代币数量决定。  

$ARB代币可以委托给其他钱包，这意味着即使您没有时间定期审查和讨论提案，也可以通过委托您的投票权来参与治理。  

$ARB代币的初始供应量为1000亿枚，新$ARB代币最多可以以每年2%的供应量速度铸造，第一批铸造活动于2024年3月15日成为可能。  
Arbitrum DAO通过宪法提案执行$ARB代币的铸造活动，并且随着$ARB代币的空投，Arbitrum的治理权正式转移到Arbitrum DAO手中，标志着向去中心化治理的转变。  

要参与Arbitrum DAO治理，您需要持有$ARB代币的以太坊钱包，并可以通过连接到Tally的Arbitrum DAO页面进行委托投票。  
### 2024.12.26
Arbitrum 经济模型
$ARB 供应和分配概览
$ARB代币的总供应量初始上限为100亿枚，其中17.53%分配给Offchain Labs投资者，1.13%分配给Arbitrum生态系统中的DAO，11.62%通过空投分配给Arbitrum平台用户，42.78%分配给Arbitrum DAO国库，26.94%分配给Offchain Labs团队、未来团队和顾问。  
治理方式
Arbitrum推出了自执行DAO治理模型，$ARB代币持有者可以对Arbitrum One和Arbitrum Nova网络的治理提案进行投票。  
治理是自执行的，意味着投票结果将直接影响并执行链上决策，无需中介。  
ARB 的价值主张空投认领规则和方法
用户空投资格
DAO 空投标准和分配

### 2024.12.27
**Arbitrum DAO术语表** 
$ARB：Arbitrum的治理代币，是Arbitrum One链上的原生ERC-20代币。持有$ARB代币的人可以参与Arbitrum的链上治理。  
$ARB反向网关：一系列智能合约，负责在Arbitrum One和以太坊之间桥接$ARB代币。  
活跃验证者：一个质押的验证者，它提出可争议的断言以推进Arbitrum链的状态或挑战其他人断言的有效性。  
空投：一种将代币分发到合格钱包地址的机制，通常基于链上活动。  
Arbitrum AnyTrust链：实现Arbitrum AnyTrust协议的Arbitrum链。  
Arbitrum AnyTrust协议：一种Arbitrum协议，通过一个名为数据可用性委员会（DAC）的许可方集合来管理数据可用性。  
Arbitrum链：在Arbitrum协议上运行的区块链，与EVM兼容，使用底层EVM链（例如，以太坊）进行结算和简洁的欺诈证明。  
Arbitrum链所有者：有能力升级Arbitrum核心协议合约和设置各种系统参数的实体。  
Arbitrum DAO：全球$ARB代币持有者和代表组成的社区，负责治理Arbitrum One链、Arbitrum Nova链、Arbitrum DAO宪法和安全委员会。  
Arbitrum DAO国库：存在于Arbitrum One链上的智能合约，包含由Arbitrum DAO集体控制的代币。  
Arbitrum改进提案（AIP）：由Arbitrum DAO宪法定义的治理提案，分为宪法AIP和非宪法AIP。  
Arbitrum Nitro：当前Arbitrum技术栈；运行Geth的分支，并使用WebAssembly作为其底层虚拟机。  
Arbitrum Nova：第一个在以太坊主网上运行的Arbitrum AnyTrust链，引入了更便宜的交易。  
Arbitrum One：第一个在以太坊主网上运行的Arbitrum Rollup链，完全无需信任。  
Arbitrum Rollup链：实现Arbitrum Rollup协议的Arbitrum链。  
Arbitrum Rollup协议：一种无需信任、无需许可的Arbitrum协议，使用其底层基础层进行数据可用性，并继承其安全性。  
子链：一个结算到底层父链的Arbitrum链。例如，Arbitrum One和Arbitrum Nova是 Ethereum的子链。  
可申领空投期：合格$ARB代币接收者能够申领其代币的时间周期。  
宪法AIP：与非宪法AIP相比，要求更严格的提案，需要更长的延迟期才能生效。  
核心治理者：负责创建宪法AIP的治理合约。  
数据可用性委员会（DAC）：一个许可方集合，负责在Arbitrum AnyTrust协议链中执行数据可用性。  
去中心化应用（dApps）：结合基于区块链的智能合约与前端用户界面的应用。  
代表：能够对Arbitrum治理提案进行投票的一方，可以是$ARB代币持有者或被其他$ARB代币持有者委托投票权的人。  
紧急行动：安全理事会在紧急情况下使用的一种特定类型的治理行动，例如修复关键漏洞。  
以太坊共识层（CL）：促进以太坊Layer 1（L1）网络的质押、点对点共识、区块创建和证明。  
以太坊执行层（EL）：促进以太坊Layer 1（L1）网络的智能合约逻辑和执行。  
排除地址：ARB持有者可以将其投票权委托给这个特殊地址，以便在提案的法定人数计算中不被包括。  
基金会归属钱包：存储Arbitrum基金会代币的智能合约钱包；代币在4年的时间里线性归属。  
治理：决策制定的方式，传统web2技术的治理依赖于董事会遵循信任社会契约，而web3技术的治理依赖于使用无需信任智能合约的去中心化自治组织（DAO）。    
治理提案：改变Arbitrum DAO治理协议某些方面的提案。   
治理代币：允许代币持有者对治理提案进行投票的特定类型的代币。  
不可变：在以太坊的背景下，不可变性指的是无法改变区块链中记录的数据。  
Layer 1 (L1)：以太坊网络的基础协议和底层区块链。  
Layer 2 (L2)：建立在以太坊Layer 1（L1）基础协议之上的无需信任的扩展解决方案。  
机制设计：设计协议或机制的过程，以激励特定行为。  
多签名钱包：需要多个私钥签名的钱包。  
节点运营商：在以太坊/Arbitrum生态系统中运行核心协议软件的任何人。  
非宪法AIP：Arbitrum DAO治理提案的两种类型之一。  
链下治理：通过社会共识和链下提案执行的治理。  
链上治理：由智能合约实现的治理，允许DAO成员通过治理提案决定DAO如何分配资源和更新协议。  
乐观汇总协议：设计用于通过使用基础层进行数据可用性并将计算卸载到链下节点来扩展以太坊基础层吞吐量的Layer 2（L2）协议。  
父链：作为一条或多条Arbitrum链（即子链）的结算层的EVM兼容链。  
逐步去中心化：随着时间的推移逐渐增加系统去中心化的过程。  
提案等待期：在治理提案被接受后开始的合同强制延迟期。  
Prysm：为以太坊Layer 1（L1）提供动力的共识层客户端。  
法定人数：治理提案通过所需的最低票数。  
安全理事会：由持有12个成员多重签名钱包私钥的12个实体组成的委员会。  
安全理事会队列：安全理事会的12名成员被分成两个六人队列。  
种子短语：用于恢复以太坊钱包私钥的高敏感性、确定性词汇序列。  
序列器：被赋予在固定时间窗口内重新排序快速收件箱中的交易的实体。   
智能合约：存储和在以太坊区块链上执行的自执行代码。  
Snapshot投票：代表可以链下投票的机制。  
标准代币网关：负责在以太坊和Arbitrum链之间桥接ERC20代币的一系列智能合约。   
Tally：用于与Arbitrum治理合约交互的Web界面。  
Arbitrum基金会：由Arbitrum DAO治理的法律实体。  
Arbitrum国库代币：由Arbitrum DAO国库拥有的$ARB代币。  
Arbitrum DAO宪法：规定Arbitrum DAO运作规则、程序和社区价值观的正式文件。  
时间锁合约：限制在指定未来时间之前采取行动的智能合约。  
代币分配合约：负责持有和分配空投$ARB代币的智能合约。  
代币加权治理：一种治理系统，其中投票权重与治理代币的所有权成正比。  
透明度报告：解释采取了哪些行动以及为什么的报告。  
国库治理者：负责创建非宪法AIP的治理合约。  
无需信任：指系统能够在不依赖中央权威或中介的情况下运作。  
未认领空投代币：未被潜在所有者认领的可申领$ARB代币。  
可投票代币：除了Arbitrum DAO和Arbitrum基金会拥有的代币之外的所有$ARB代币。  
投票期：Arbitrum改进提案（AIP）提交成功后，Arbitrum DAO成员可以投票支持或反对的14-16天期间。  

### 2024.12.28
治理架构：阅读 [安全理事会成员](https://docs.arbitrum.foundation/security-council-members)
Arbitrum DAO是一个建立在以太坊区块链上的去中心化自治组织，它通过社区驱动的治理机制赋予$ARB代币持有者提出和投票决定组织及其技术变化的能力。其治理智能合约部署在Arbitrum One rollup链上，这是一个第2层扩展解决方案，旨在提升以太坊的可扩展性。代币持有者使用$ARB代币对提案进行投票，其投票权重与他们持有的代币数量成正比。Arbitrum DAO还设有一个内置金库系统，用于资助组织的持续开发和维护，代币持有者可以对金库资金的使用提出建议并进行投票。此外，DAO内置了一个安全委员会，负责确保DAO及其链的安全性和完整性，并在安全紧急情况下迅速采取行动，绕过常规投票过程。安全委员会成员由DAO成员通过半年一次的选举产生。

### 2024.12.29
如何提交 DAO 提案  
先决条件：  
提交提案需要拥有一定数量的可投票代币，对于Snapshot轮询的温度检查需要至少500,000个代币，而对于Tally链上提案则需要至少1,000,000个代币。  
提案类型：  
确定你的提案是宪法性（Constitutional）还是非宪法性（non-Constitutional）提案，前者涉及修改宪法或AIP-1的文本、程序，或需要链上所有者权限的行动；后者则包括请求资金/赠款或提供社区指南和信息的提案。  
提案结构：  
包括摘要、动机、理由、关键术语、规格、实施步骤、时间轴和总成本等部分。如果提案未通过，重新提交时还需包括先前提案的链接、未通过的原因以及对提案所做的更改。
提案前开发： 如果提案需要代码更改，应包括通过提案后将执行的代码。   
第1步：进行正式的温度检查：  
在DAO治理论坛上创建新帖子并使用模板提交提案，然后在Snapshot上创建一个为期一周的投票来衡量社区对提案的兴趣。  
第2步：使用Tally提交链上提案：  
如果你的钱包可以代表至少1,000,000个代币，你可以在Tally上创建链上提案，选择目标调控器（Arbitrum Core或Arbitrum Treasury），添加提案名称、描述和行动，预览并提交提案。
提案通过条件：
提案通过需要赞成票多于反对票，并且投赞成票的总票数至少达到可投票代币的一定百分比（宪法AIP为5%，非宪法AIP为3%）。 
重要说明：  
安全理事会有权执行紧急和非紧急行动，无需经过提案过程。提案通过所需的支持门槛可能因提案类型和宪法中规定的法定人数要求而异。你可以将投票权委托给其他地址，即使没有足够的代币提交链上提案。  
<!-- Content_END -->
