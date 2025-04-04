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

# Alfred

之前在Web2从事Java开发工作，接触Web3后在积极参与相关社区活动，不断学习中。希望能够在残酷学习中坚持下来，顺利完成。

## Notes

<!-- Content_START -->

### 2024.12.10

### 1. Arbitrum 的使命

Arbitrum 的使命是通过提供更高效、低成本和用户友好的解决方案，增强以太坊生态系统的可扩展性和可用性。它致力于构建一个去中心化、高性能的 Layer 2 扩展平台，使开发者和用户能够享受更快、更便宜的交易，同时保持以太坊的安全性和去中心化特点。

### 2. Arbitrum 的特点

- 高扩展性
：Arbitrum 是以太坊的 Layer 2 扩展方案，可以显著提高交易处理能力，降低拥堵和交易费用。
- 与以太坊的兼容性
：完全兼容以太坊的 EVM（以太坊虚拟机），开发者可以无缝迁移现有智能合约和 DApp。
- 低成本
：利用 Rollup 技术，大幅降低了链上计算和存储成本，使得小额交易也具有经济性。
- 安全性
：继承以太坊主链的安全性，所有交易在 Layer 1 上的验证确保了去中心化和抗审查性。
- 灵活性
：支持多种开发工具和语言，例如 Solidity，同时为开发者提供良好的文档和社区支持。

### 2024.12.11

### 3. Arbitrum 的原理

Arbitrum 采用了 Optimistic Rollup 技术，通过将大量交易打包（Rollup）并发送到以太坊主链上记录和验证，实现扩展和成本降低。

#### 交易流程

- 用户提交交易：用户的交易首先被发送到 Arbitrum 的 Layer 2 网络。
- 批量打包：多个交易被打包成一个批次，并生成一个状态更新。
- 状态提交：批量交易的摘要（状态根）被提交到以太坊主链。
- 欺诈证明：如果有恶意操作，验证者可以提交欺诈证明，以挑战提交的状态并恢复正确性。

#### 核心技术

- Rollup 技术：将计算和存储移到链下，仅将交易摘要记录到主链。
- 欺诈证明机制：通过挑战者模型确保系统的正确性和抗审查性。
- 以太坊安全性继承：利用 Layer 1 的共识机制，保证 Arbitrum 的交易数据和状态更新的最终性。
### 2024.12.12

### 4. Rollup 概念概述
Rollup 是一种二层扩展解决方案，旨在提高区块链的可扩展性和性能，特别是在以太坊等区块链上。通过将大量交易和计算工作“卷起”并批量处理，这些交易的执行和数据存储仍然依赖于主链（如以太坊），但通过将交易的计算和存储从主链转移到二层，显著提高了交易吞吐量和降低了费用。

原理：
- 成本优化：将⼤部分运算与存储任务移交至L1链下也即L2上。
- 安全保障：L2上的交易内容与交易后的状态，会同步⾄以太坊L1，通过合约来校验 状态转换的有效性。

Rollup 的核心概念是将交易数据打包到主链之外进行处理，但通过机制保证数据的完整性和安全性。这使得它可以提供和主链一样高的安全性，同时大幅提高处理速度和降低成本。常见的 Rollup 类型包括 Optimistic Rollups 和 ZK-Rollups

> 非交互型 rollup（如，ZK-Rollup）、单轮交互型 rollup（如 “optimistic rollup” 提案）和多轮交互型 rollup （如 Arbitrum Rollup ）

防止Rollup排序器作恶的状态校验⽅式，分为欺诈证明（Fraud Proof）和有效性证明（Validity Proof）两类。使⽤欺诈证明的Rollup⽅案称为OP Rollup（Optimistic Rollup，OPR），⽽因为一些历史包袱，使⽤有效性证明的Rollup往往被称为ZK Rollup（Zero-knowledge Proof Rollup，ZKR)，而不是Validity Rollup。

### 5. Fraud Proofs 欺诈证明机制
欺诈证明机制 是在 Optimistic Rollups 中用来确保二层链正确性的机制之一。在这种模型下，交易的执行被假定是有效的，直到有人提出异议（即“挑战”）。这种机制可以通过以下步骤工作：

- 交易提交：用户在二层 Rollup 上发起交易，交易数据和状态变更会被“卷起”并提交到以太坊主链。主链会记录这些批量交易的哈希值。

- 乐观执行：在 Optimistic Rollup 中，假设这些交易是有效的，并且会在链上验证这些交易。理论上，交易会立即被认为是有效的，不需要立即进行复杂的计算。

- 欺诈挑战期：将状态提交到 Rollups 合约后，有一个时间窗口允许其他参与者查看这些交易。如果某个参与者认为 Rollup 上的某个交易是不合法的或恶意的，他们可以提出一个 欺诈证明，即对该交易的合法性进行挑战。

- 欺诈证明的验证：当有人提出欺诈证明时，网络会进行审查，验证该交易是否真正无效。如果证明成功，恶意或无效的交易会被回滚，相关提交的交易也会被撤销。

- 奖励和惩罚：提出有效欺诈证明的挑战者会获得奖励，而那些提交无效交易的节点（比如欺诈者）则会受到惩罚。惩罚通常是扣除抵押金，或者其他形式的经济惩罚。

### 2024.12.13
### 6. Zero-Knowledge Proof 零知识证明机制
零知识证明（简称 ZKP）是一种密码学方法，允许一方（证明者）向另一方（验证者）证明某个声明是真实的，而无需透露任何与该声明相关的具体信息。自20世纪80年代首次提出以来，零知识证明在隐私保护、身份验证、区块链技术等多个领域得到了广泛应用和深入研究。

零知识证明是一种协议，满足以下三个核心属性：
- 完备性（Completeness）：如果声明为真，诚实的验证者将在协议结束时被说服。
- 可靠性（Soundness）：如果声明为假，恶意的证明者无法说服诚实的验证者，除非以极低的概率。
- 零知识性（Zero-Knowledge）：如果声明为真，验证者不会学到任何除了声明为真之外的其他信息。

### 7、Rollup 协议
欺诈证明虽然不能像零知识证明那样具有⾼度的简洁性，但Arbitrum使⽤了⼀种“多轮分割-单步证明”的轮流式交互流程，最终需要证明的仅仅是单⼀的虚拟机操作码，成本相对较⼩。

Rollup协议的核心合约是RollupProxy.sol，在保证数据结构一致的情况下，使用了一个罕见的双重代理结构，一个代理对应两个实现RollupUserLogic.sol和RollupAdminLogic.sol，在Scan等工具中目前还无法很好的解析。

另外还有ChallengeManager.sol合约负责管理挑战，OneStepProver系列合约来判定欺诈证明。
![image](https://github.com/user-attachments/assets/a021e2c0-a0df-4125-912c-0fc22d246028)

ChallengeManager合约负责验证对挑战步骤的细分过程：

1.细分是一个双方轮流互动的过程，一方对某个Rollup Block中包含的历史数据进行分段，另一方指出是哪部分数据片段有问题。类似于二分法（实际是N/K）不断渐进缩小范围的一个过程。

2.之后，可以继续定位至哪条交易及结果有问题，再进一步细分至该交易中有争议的某条机器指令。

3.ChallengeManager合约只检查对原始数据进行细分后，产生的『数据片段』是否有效。

4.当挑战者和被挑战者定位到了将被挑战的那条机器指令后，挑战者调用oneStepProveExecution()，发送单步欺诈证明，证明这条机器指令的执行结果有问题。

### 8、单步证明
单步证明是整个Arbitrum的欺诈证明的核心。WAVM，Wasm Arbitrum Virtual Machine，它是一个由ArbOS模块和Geth（以太坊客户端）核心模块共同编译成的虚拟机。由于L2与L1有许多截然不同的地方，原始的Geth核心必须经过轻量修改，并且配合ArbOS一起工作。所以，L2上的状态转换其实是ArbOS+Geth Core的共同手笔。
![image](https://github.com/user-attachments/assets/095379f9-7565-4401-bf78-0be0a7d38d71)

Arbitrum的节点客户端（排序器、验证者、全节点等），是将上述ArbOS+Geth Core处理的程序，编译为节点主机能直接处理的原生机器代码（for x86/ARM/PC/Mac/etc.）。

如果把编译后得到的目标语言更改为Wasm，就得到了验证者生成欺诈证明时使用的WAVM，而验证单步证明的合约上，模拟的也是WAVM虚拟机的功能。

那为什么在生成欺诈证明时，要编译为Wasm字节码？主要还是因为，验证单步欺诈证明的合约，要用以太坊智能合约模拟出 能处理某套指令集的虚拟机VM，而WASM易于在合约上实现模拟。
![image](https://github.com/user-attachments/assets/149c286b-e139-46e5-b715-9c81820c68a7)

但WASM相比于Native机器代码，运行速度略慢，所以只有在欺诈证明生成及验证的时候，Arbitrum的节点/合约才会用到WAVM。

在之前的多轮互动细分后，单步证明最终证明的是WAVM指令集中的单步指令。

### 2024.12.14

### 9、Retryables 可重试票据
跨链都是异步和非原子性的，它不可能像在一条链上一样做完一笔交易确认后就知道结果，也不能保证另一侧一定会在某个时间点发生某些事。因此跨链有可能因为一些软性问题而失败，但只要使用正确的手段，诸如可重试票据（Retryable Ticket），就不会发生资金卡住等硬性问题。

可重试票据是通过Arbitrum官方桥充值时，用到的基本工具，ETH和ERC20的充值都会使⽤到。其⽣命周期分为三步：

1. 在L1上提交票据。在Delayed Inbox合约中使用createRetryableTicket()方法创建充值票据，并提交。

2. L2上自动兑付。大部分情况下，排序器可以自动帮用户兑付票据，无需后续的手动操作。

3. L2上手动兑付。部分边缘情况，如L2上gas价格突然激增，票据上预付的gas不够，则无法自动兑付。此时需要用户手动操作。

注意，如果自动兑付失败，需要在7日内手动兑付票据，否则要么票据将会被删除（资金会永久损失），要么需要为票据的保存支付一定费用来续租。

另外，对于Arbitrum官方桥的提现流程，虽然和充值行为在流程上有一定对称相似性，但并没有Retryables这个概念，一方面可以从Rollup协议本身理解，另一方面我们可以从一些区别进行理解：

1. 提现的过程中不存在自动兑付，因为EVM没有定时器或自动化，而L2上可以实现自动兑付，是排序器帮忙实现的，所以L1上用户要手动与Outbox合约交互，以Claim取回资产。

2. 提现也不存在票据过期的问题，只要过了挑战期，可以在任意时间领取。

### 10、ERC-20资产跨链 Gateway
![image](https://github.com/user-attachments/assets/b519b20f-4e82-4f6f-8093-0a6aa1eb52d1)
Arbitrum使用了Gateway系统，解决了大部分ERC20跨链的痛点，具有以下特性：

Gateway组件在L1和L2成对出现。

Gateway Router负责维护Token L1Token L2之间的地址映射，以及some tokensome gateway之间的映射。

Gateway本身可分为StandardERC20 gateway，Generic-custom gateway，Custom gateway等等，用以解决不同类型的和功能ERC20的桥接问题。

我们以比较简单的WETH跨链为例，来说明自定义gateway的必要性。

WETH是一种ETH的ERC20等价物。Ether作为主币，很多dApp中的复杂功能是无法实现的，因此需要一个ERC20的等价物。向WETH合约内转入一些ETH，它们会被锁在合约内，并生成出相同数量的WETH。

同理，也可以销毁WETH，取出ETH。显然，流通的WETH和锁仓的ETH数量永远是1：1的。

如果现在把WETH直接跨链到L2上，我们会发现一些奇怪的问题：

无法在L2上把WETH进行Unwrap变成ETH，因为L2上并没有锁仓对应的ETH。

Wrap功能可以使用，但这些新生成的WETH如果跨回到L1，也无法在L1上解封装为ETH，因为L1和L2上的WETH合约不是“对称的”。

显然这违反了WETH的设计原理。那么WETH在跨链时，不论是充值还是提现，都需要先Unwrap成ETH后，再跨到对面，然后Wrap成WETH。这个也就是WETH Gateway的作用。

其他有更复杂逻辑的代币同理，需要更复杂和精心设计的Gateway才能正常在跨链环境下工作。Arbitrum的自定义Gateway继承了普通Gateway的跨链通信逻辑，并允许开发者自定义与代币逻辑相关的跨链行为，可满足大部分需求。

### 11、Delayed Inbox 慢收件箱
与快箱也即 SequencerInbox相对应的是慢箱 Inbox （全称Delayed Inbox）。为什么要有快慢之分呢？因为快箱是专⻔接收排序器发布的L2交易Batch的，所有未经排序器在L2网络内预处理的交易，都不该出现在快箱合约中。

慢箱的第⼀点作⽤是，处理L1到L2的充值⾏为。⽤户通过慢箱进⾏充值，排序器监听到后再反映在L2上，最终这笔充值记录会被排序器包含进L2的交易序列中，并提交⾄快箱合约Sequencer Inbox。

在这个例⼦中，⽤户直接向快箱提交充值交易是不合适的，因为提交到快箱Sequencer Inbox中的交易，会干扰到Layer2正常的交易排序，然后会影响到排序器的工作。

慢箱的第⼆个作⽤，是抗审查。用户直接提交⾄慢箱合约中的交易，排序器⼀般会在10分钟内归集到快箱中。但如果排序器恶意忽略你的请求，慢箱还有⼀个强制归集force inclusion功能：

如果交易被提交至Delayed Inbox中，经过24小时，慢箱中的交易仍未被排序器包含至交易序列中，用户可以在Layer1上手动触发force inclusion函数，把被排序器忽略掉的交易请求，强制归集到快箱Sequencer Inbox中，之后就会被全体Arbitrum One节点监听到，会被强制包含进Layer2交易序列里。

我们刚才提到过，快箱⾥的数据就是L2的历史数据实体。所以在被恶意审查的情况下，通过慢箱可以让交易指令最终包含进L2账本中，这涵盖了强制提款等逃离Layer2的场景。

由此可以看出，对任何⼀个⽅向和层次的交易，排序器最终都⽆法永久审查你。

### 12、Outbox 出站箱
出站箱Outbox只与提现有关，可以理解为提现行为的记录和管理系统：

我们知道，Arbitrum官方桥的提现需要等待约7天的挑战期结束， Rollup Block 最终敲定后，提款行为才可以实施。⽤户在挑战期结束后，向Layer1上的Outbox合约提交相应的Merkle Proof，它再与其他职能的合约通信（如解锁其他合约中锁定的资产），最终完成提现。

OutBox合约会记录哪些L2到L1的跨链消息已经被处理过，以防止有人反复提交执行过的提现请求。它通过mapping(uint256 => bytes32) public spent，记录提现请求的spent Index与信息对应关系，如果mapping[spentIndex] != bytes32(0)则该请求已被提现过。原理类似于防止重放攻击的交易计数器Nonce。

### 2024.12.15

### 充值与提现流程

以ETH为例完整讲解充值与提现的流程。ERC20与之不同的仅仅是⾛了Gateway

### ETH充值
![image](https://github.com/user-attachments/assets/a7fa9e0f-001b-43c8-a12e-d3338d86f4a0)

1. 用户调用慢箱的depositETH()函数。

2. 该函数会继续调用bridge.enqueueDelayedMessage()，在bridge合约中记录该消息，并将ETH发送往bridge合约。所有的ETH充值资金，都保管在bridge合约中，相当于一个充值地址。

3. 排序器监听到慢箱中的充值消息，将充值操作反映⾄L2数据库中，⽤户可以在L2网络看到自己充进来的资产。

4. 排序器将该笔充值记录包含进交易批次batch，提交给L1上的快箱合约。

### ETH提现
![image](https://github.com/user-attachments/assets/3da94536-68f7-429d-bf36-acded86fe2e8)

1. ⽤户在L2上调⽤ ArbSys合约的withdrawEth()函数 ，在L2上销毁相应数量的ETH。

2. 排序器将该提现请求发送⾄快箱。

3. Validator节点根据快箱中的交易序列，创建新的Rollup Block，其中会包含上述提款交易。

4. Rollup Block度过了挑战期并被确认后，⽤户可以在L1上调用Outbox.execute Transaction()函数，证明参数由前面提到的ArbSys合约给出。

5. Outbox 合约确认⽆误后，解锁bridge中相应数额的ETH发送给⽤户。

### 强制提现
force Inclusion()强制归集功能用于对抗定序器的审查，任何L2本地交易、L1到L2交易和L2到L1交易，都可以使用该功能实现。定序器的恶意审查严重影响了交易体验，大部分情况下我们会选择提现离开L2，因此下面以强制提现为例介绍forceInclusion的用法。

回顾在ETH提现步骤中，只有步骤1、2是涉及到定序器审查的，所以只需要更改这两步：

调用L1上慢箱合约中的inbox.sendL2Message()，输入参数就是在L2上调用withdrawEth()时需要输入的参数。该消息会共享给L1上的bridge合约。

等待24小时的强制归集等待期后，调用快箱中的force Inclusion()进行强制归集，快箱合约会检视bridge中是否有对应消息。

最终用户可以在Outbox中提现，其余步骤由同正常的提现相同。

另外，arbitrum-tutorials中也有使用Arb SDK的详细教程去指导用户如何通过forceInclusion()去进行L2本地交易和L2到L1交易。

### 2024.12.16

### Arbitum One 架构
![image](https://github.com/user-attachments/assets/f49fdd66-b14a-4bdc-8b14-6b79af87efc0)
- Arbitrum 的架构有部分在 L1 上，有部分在 L2 上。在 L1 上的组件是 EthBridge，由一组以太坊合约构成。EthBridge 负责对 Arbitrum Rollup 协议进行仲裁，以及维护 Arbitrum rollup 在以太坊链上的收件箱和发件箱。
- 用户、L1 合约和全节点可以通过以太坊链上的收件箱和发件箱将其交易发送至 Arbitrum 链，并观察这些交易的结果。
- Arbitrum 虚拟机（AVM）是 EthBridge 提供的功能，是 L1 和 L2 之间的网关。AVM 能够读取输入，并基于这些输入执行计算，从而产生输出。
- ArbOS 运行在 AVM 上，确保智能合约在 Arbitrum 链上执行。ArbOS 完全存在于 L2 上，并像在以太坊上一样运行 EVM 合约。

### Arbitrum Classic 多轮交互式欺诈证明
Arbitrum 采用多轮欺诈证明。简单来说，就是通过二分查找，找到引起分歧的那个区块的第一个操作码。找到之后，只需在链上执行这个操作码。纠纷解决协议的结果是一个参与者将被发现是错误的。这个参与者的押金会被罚没。押注会从所在的方框上删除。部分押金会给到纠纷的另一方，剩下的被烧掉。

- 当两个质押者押注不同的区块且这两个区块之间没有继承关系时，他们会在某个区块上产生分歧，从而引发挑战。
- 挑战主要发生在 Arbitrum 链上，由 L1 合约裁决。
- 挑战包括一个在 L2 上进行的交互型多轮切分游戏和一个在 L1 上执行的单步证明。
- 如果有质押者对某个区块提出争议，提议该区块的质押者将作为 “被告” 捍卫自己的断言。在切分游戏中，作为 “被告” 的质押者（Alice）为先手，将 N 个指令切分成 K 段，每段的大小是 N/K，且每段都有一个起点和一个终点。
- 作为 “原告” 的质押者（Bob）同样将 N 个指令切分成 K 段（每段的大小是 N/K），并将它们与 Alice 的切分段一一对应，发现其中一个切分段的终点与 Alice 的不同。
  - Bob 实际上是在找出他不认同的切分段。
- 接着，Bob 会执行 Alice 最初的操作，将有争议的切分段（大小为 N/K）再切分成 K 个子段，然后将这个切分段连同子段一起发送给 Alice。Alice 执行 Bob 最初的操作，找到终点不同的那个子段。
- 切分流程继续下去，直到 Alice 和 Bob 找到他们产生分歧的那一个指令为止。这个指令被发送给 L1 合约，并由后者执行它，然后决定这场争议的 “胜诉方”。
- “败诉方” 将失去质押物，一部分质押物将被销毁（防止攻击者对冲押注），其余则奖励给诚实的 “胜诉方”。
- 在整个切分流程中，作为裁决方的 L1 合约不知道任何关于指令的信息，只负责核实双方是否遵循游戏规则。
- 在争议期间，其他所有验证者都能在争议敲定之前自行断定争议的结果，这就意味着会发生软分叉，且验证者可以继续在正确的链上提交 Rollup 区块。
- 挑战期有一个强制的期限，即，每个质押者大约一周时间。
- 每个质押者必须在一周的限期内完成自己的任务，否则就会 “败诉”。
- 多个纠纷可以同时解决，但是每个押注者一次最多只能参与一个纠纷。

### Arbitrum Nitro
2022 年 8 月，Arbitrum One 网络升级为 Arbitrum Nitro。Nitro 使用 WebAssembly（WASM）架构将取代原先的 Arbitrum EVM（AVM）架构，其新的证明器（prover）可以在 WASM 代码上进行 Arbitrum 的交互式欺诈证明。此外，Gethcore 也直接编译到 Arbitrum 中，使其更兼容 EVM。
> 为什么升级：https://docs.arbitrum.io/how-arbitrum-works/why-nitro （更低的费用、更好的以太坊兼容性和简单性）

Nitro 的精髓及其关键创新在于四大理念：

- 排序，然后是确定性执行：Nitro 采用两阶段策略处理交易。首先，将交易组织成一个有序序列，然后 Nitro 按照该序列提交。然后，按照该序列通过确定性状态转换函数处理交易。

- Geth 为核心：Nitro 通过编译流行的 go-ethereum（“Geth”）以太坊节点软件的核心代码来支持以太坊的数据结构、格式和虚拟机。以这种方式使用 Geth 作为库可确保与以太坊的高度兼容性。

- 将执行与证明分开：Nitro 采用相同的源代码并将其编译两次，一次编译为本机代码以便在 Nitro 节点中执行，以优化速度，再次编译为 WASM 用于证明，以优化可移植性和安全性。

- 具有交互式欺诈证明的乐观汇总：Nitro 使用乐观汇总协议将交易结算到第 1 层以太坊链，其中包括 Arbitrum 开创的交互式欺诈证明。

#### 排序，然后确定性执行
![Nitro 中交易的处理方式](https://github.com/user-attachments/assets/dc4fd517-f206-4a9f-b4bb-465dca521e30)
首先，用户创建交易，使用钱包对其进行签名，然后将其发送到 Nitro 链的 Sequencer。顾名思义，排序器的工作是获取到达的事务，将它们放入有序序列中，然后发布该序列。

一旦事务被排序，它们就会按顺序通过状态转换函数一一运行。状态转换函数将链的当前状态（账户余额、合约代码等）以及下一笔交易作为输入。它会更新状态，有时会在 Nitro 链上发出新的第 2 层区块。

因为协议不信任定序器不会将垃圾放入其序列中，所以状态转换函数将检测并丢弃序列中的任何无效（例如，格式不正确）事务。一个表现良好的 Sequencer 会过滤掉无效的交易，这样状态转换函数就永远不会看到它们——这降低了成本，从而使交易费用保持在较低水平——但无论 Sequencer 在其 feed 中放入什么内容，Nitro 仍然可以正常工作。 （提要中的交易由其发送者签名，因此排序器无法创建伪造的交易。）

状态转换函数是确定性的，这意味着它的行为仅取决于当前状态和下一个事务的内容，而不依赖于其他任何东西。由于这种确定性，交易 T 的结果将仅取决于链的创世状态、序列中 T 之前的交易以及 T 本身。

由此可见，任何知道交易序列的人都可以自己计算状态转换函数，并且所有这样做的诚实方都保证得到相同的结果。这是 Nitro 节点操作的正常方式：获取交易序列，并在本地运行状态转换函数。为此不需要共识机制。

### 2024.12.17
#### 以Geth为核心
Nitro 的第二个关键设计思想是“以 geth 为核心”。这里的“geth”指的是go-ethereum，是以太坊最常见的节点软件。顾名思义，go-ethereum 是用 Go 编程语言编写的，几乎所有 Nitro 也是如此。
![image](https://github.com/user-attachments/assets/7709cee6-920a-4a49-af4d-7c8d09032de6)

组成 Nitro 节点的软件可以被认为是由三个主要层构建的，如上所示：

- 基础层是 geth 的核心——Geth 中模拟 EVM 合约执行并维护构成以太坊状态的数据结构的部分。 Nitro 将此代码编译为库，并进行一些小的修改以添加必要的挂钩。
- 中间层，我们称之为 ArbOS，是定制软件，提供与第 2 层功能相关的附加功能，例如解压缩和解析 Sequencer 的数据批次、计算第 1 层的 Gas 成本并收取费用来补偿它们，以及支持跨层链桥功能，例如从 L1 存入以太币和代币以及将其提取回 L1。我们将在下面深入了解 ArbOS 的详细信息。
- 顶层由节点软件组成，大部分来自 geth。它处理来自客户端的连接和传入的 RPC 请求，并提供操作与以太坊兼容的区块链节点所需的其他顶级功能。

因为这个结构的顶层和底层都大量使用了 geth 的代码，所以这种结构被称作“ geth 三明治”。在这个比喻中，geth 相当于“面包”，而 ArbOS 则是“夹心”，不过整个结构是以面包（即 geth ）来命名的。

前文提到的状态转换函数（ State Transition Function ）是由 Geth 的底层和 ArbOS 的一部分组合而成的
Arbitrum 的旧方案方案是通过定制的 Arbitrum 虚拟机（ AVM ）来模拟 EVM，它的一些内部逻辑在 EVM 不一致（例如 Gas 的计算）。 而 Geth 则基本完全支持以太坊的数据结构、格式和虚拟机，所以可以实现以太坊高度兼容

#### 将执行与证明分开
![image](https://github.com/user-attachments/assets/50e007f2-bffa-4157-9c1e-0d70cd4e6bc5)

设计实用的 Rollup 系统的挑战之一是希望系统在普通执行中表现良好与能够可靠地证明执行结果之间的紧张关系。 Nitro 通过使用相同的源代码来执行和证明，但针对两种情况将其编译为不同的目标，从而解决了这种紧张关系。

在编译执行Nitro节点软件时，使用普通的Go编译器，生成目标架构的本机代码，当然对于不同的节点部署，它会有所不同。 （节点软件以源代码形式分发，并作为包含已编译二进制文件的 Docker 映像进行分发。）

另外，为了证明，状态转换函数的代码部分由 Go 编译器编译为 WebAssembly (wasm)，这是一种类型化、可移植的机器代码格式。然后，wasm 代码会经过简单的转换，转换为我们称为 WAVM 的格式，详细信息如下。如果对STF计算的正确结果存在争议，则参考WAVM代码解决。

##### WAVM
wasm 格式具有许多功能，使其成为欺诈证明的良好工具——它是可移植的、结构化的、明确的，并且具有相当好的工具和支持——但它需要一些修改才能完全完成工作。 Nitro 使用 wasm 的稍微修改版本，我们称之为 WAVM。一个简单的转换阶段将 Go 编译器生成的 wasm 代码转换为适合证明的 WAVM 代码。

WAVM 与 wasm 主要在三个方面有所不同。首先，WAVM 删除了 wasm 的一些不是由 Go 编译器生成的功能；转换阶段验证这些功能是否不存在。

其次，WAVM 限制了 wasm 的一些功能。例如，WAVM 不包含浮点指令，因此转换器通过调用 Berkeley SoftFloat 库来替换浮点指令。 （我们使用软件浮点来降低架构之间浮点不兼容的风险。核心 Nitro 函数从不使用浮点，但 Go 运行时确实使用一些浮点运算。）WAVM 不包含嵌套控制流，因此，变压器将控制流结构扁平化，将控制流指令转变为跳转。一些 wasm 指令的执行时间是可变的，我们在 WAVM 中通过使用固定成本指令将它们转换为结构来避免这种情况。这些转换简化了证明。

第三，WAVM 添加了一些操作码以实现与区块链环境的交互。例如，新指令允许 WAVM 代码读取和写入链的全局状态，从链的收件箱获取下一条消息，或者发出执行状态转换函数成功结束的信号。

#### 乐观Rollup

##### Rollup

Arbitrum 是一个汇总，这意味着链的输入（放入收件箱的消息）都作为 calldata 记录在以太坊链上。正因为如此，每个人都拥有确定链当前正确状态所需的信息——他们拥有收件箱的完整历史记录，并且结果由收件箱历史记录唯一确定，因此他们可以重建收件箱的状态如果需要，仅基于公共信息的链。

这也允许任何人成为 Arbitrum 协议的完整参与者，运行 Arbitrum 节点或作为验证者参与。这条链的历史或状态都不是秘密。

##### Optimistic

Arbitrum 是乐观的，这意味着 Arbitrum 通过让任何一方（“验证者”）在第 1 层上发布该方声称正确的汇总区块来推进其链的状态，然后让其他人有机会质疑该主张。如果挑战期（6.4 天）过去并且没有人挑战所声明的汇总区块，则 Arbitrum 确认汇总区块是正确的。如果有人在质疑期间质疑该主张，那么 Arbitrum 将使用有效的争议解决协议（详细信息如下）来识别哪一方在撒谎。说谎者将被没收押金，而说真话的人将获得部分押金作为他们努力的奖励（部分押金将被烧毁，保证即使存在某些勾结，说谎者也会受到惩罚）。

因为试图作弊的一方将损失押金，所以尝试作弊应该非常罕见，正常情况是一方发布正确的汇总区块，而没有人挑战它。

#### 为什么交互式证明更好
- **在乐观情况下更高效**：由于交互式证明可以解决大于一笔交易的争议，因此它可以允许汇总块在该块涵盖的所有执行之后仅包含有关链的最终状态的单个声明。相比之下，重新执行需要为汇总块中的每个事务发布状态声明。每个汇总块有数百或数千个交易，这在 L1 占用空间中存在很大差异 - 并且 L1 占用空间是成本的主要组成部分。

- **在悲观情况下更有效**：在发生争议时，交互式证明只需要 L1 裁判合约来检查 Alice 和 Bob 的行为是否“具有正确的形状”，例如，Alice 将她的 N 步声明分成了两个声明一半大。 （裁判不需要评估 Alice 声明的正确性——Bob 会在链外进行评估。）只需重新执行一条指令。相比之下，重新执行需要 L1 裁判模拟整个交易的执行。

- **更高的每笔交易 Gas 限制**：交互式证明可以摆脱以太坊严格的每笔交易 Gas 限制。出于显而易见的原因，气体限制不是无限的，但它可能比以太坊更大。就以太坊而言，耗费大量 Gas 的 Arbitrum 交易的唯一缺点是，它可能需要步骤稍微多一点的交互式欺诈证明（而且只有在确实是欺诈性的情况下）。相比之下，重新执行必须施加比以太坊更低的Gas 限制，因为必须能够在单个以太坊交易中模拟交易的执行（这比直接执行它更昂贵）。

- **更大的实施灵活性**：交互式证明允许更大的实施灵活性。所需要的只是能够在以太坊上验证一步证明。相比之下，重新执行方法受到 EVM 的限制。

### 2024.12.18

### Sequencer 排序器
排序器是一个特别指定的全节点，赋予它有限的权力来控制交易的排序。这使得排序器能够即时保证用户交易的结果，无需等待以太坊上的任何事件发生。因此，用户不需要等待大约五分钟的区块确认，也不需要等 15 秒来等待以太坊生成一个新区块。

客户端与排序器的交互方式与与任何全节点的交互完全相同，例如，客户端只需将其钱包软件的网络 URL 指向排序器。

目前，在 Arbitrum One 和 Arbitrum Nova 链上，排序器由 Offchain Labs 运行。

#### 即时确认
如果没有排序器，节点可以预测客户端交易的结果，但无法确定，因为它无法知道或控制提交的交易在收件箱中与其他节点提交的交易之间的排序。

排序器拥有更多的排序控制权，因此它可以将客户端交易安排在收件箱队列中的位置，从而确保它能立即确定客户端交易的结果。虽然排序器的重新排序能力是有限制的（下面会详细说明），但它确实比其他任何实体都有更大的权力来影响交易的排序。

#### 收件箱，快速与慢速
引入排序器后，收件箱的操作发生了变化。

排序器的角色：只有排序器可以直接将新消息放入收件箱。排序器会给它提交的消息标记以以太坊的区块号和时间戳。（ArbOS 确保这些值是递增的，如果有必要，会适当调整，避免时间戳出现递减。）

非排序器节点：其他任何人都可以提交消息，但由非排序器节点提交的消息将被放入“延迟收件箱”（delayed inbox）队列，该队列由一个 L1 以太坊智能合约管理。延迟收件箱中的消息会在那里等待，直到排序器选择“释放”它们，进入主收件箱并被添加到队列的末尾。一个表现良好的排序器通常会在约 10 分钟后释放这些延迟消息，原因将在下面解释。

延迟消息的释放机制：如果一条消息在延迟收件箱中等待的时间超过了最大延迟间隔（目前在 Arbitrum One 上是 24 小时），任何人都可以强制将该消息提升到主收件箱中。（这确保了排序器只能延迟消息，但不能审查或阻止消息的传播。）

#### 排序器的权力与限制
排序器虽然拥有更多的交易排序控制权，但它的能力是有边界的。例如，排序器不能随意改变其他节点提交的交易的顺序，尤其是当这些交易已经被提交到收件箱时。排序器的权力在保证交易的公平性和透明性方面受到严格限制，目的是避免排序器滥用其权力，确保去中心化的最终目标。

#### 如果排序器表现良好

一个表现良好的排序器会接受所有请求者的交易，并公平地对待它们，尽可能快速地给每个交易提供承诺的结果。

它还会通过及时释放延迟的消息，最小化对非排序器交易的延迟，这与提供强有力的交易结果承诺的目标一致。具体来说，如果排序器认为在以太坊上需要 40 个确认区块才能对交易的最终性有足够的信心，那么它将在 40 个区块后释放延迟的消息。这足以确保排序器准确知道哪些交易会在其当前交易之前，因为这些前置交易已经有了最终性。对于一个良性排序器来说，不需要延迟非排序器的消息超过这个时间，因此它不会这样做。

这意味着，通过延迟收件箱（delayed inbox）处理的交易，最终性将需要更长的时间。它们的最终性时间大约会翻倍，因为它们必须先等待一个最终性周期来进行提升，然后再等待另一个最终性周期，让提升它们的以太坊交易实现最终性。

这是使用排序器的基本权衡：如果你的消息使用了排序器，最终性会提前 C 个区块；但如果你的消息没有使用排序器，最终性会延迟 C 个区块。通常，这是一个好的权衡，因为大多数交易都会使用排序器；而且，瞬时最终性与 10 分钟最终性之间的实际差异，比 10 分钟与 20 分钟最终性之间的差异要大得多。

因此，如果排序器表现良好，通常来说，使用排序器是有利的。

#### 如果排序器是恶意的

恶意的排序器可能会带来一些麻烦。如果它拒绝处理你的交易，你就不得不通过延迟收件箱进行处理，导致更长的延迟。而且，恶意排序器有能力在所有人的交易之前进行抢先操作，因此它可能会通过牺牲用户的利益来获得巨大的利润。

在 Arbitrum One 上，Offchain Labs 目前运行的是一个表现良好的排序器——我们承诺！ 这种方式虽然有用，但它并非去中心化。随着时间的推移，我们将转向去中心化、公平的排序机制，正如下面所描述的那样。

由于排序器最初由一个可信的第三方运营，之后才会去中心化，因此我们没有构建直接惩罚恶意排序器的机制。我们要求用户最初信任中心化排序器，直到我们转向去中心化公平排序。

去中心化公平排序
从 30,000 英尺的高度来看，去中心化公平排序并不复杂。它的工作原理是：排序器不再是单个中心化的服务器，而是由一组服务器组成的委员会。只要该委员会中有足够大的超级多数成员诚实无私，排序器就能在交易之间建立公平的排序。

但要实现这一点要复杂得多。康奈尔大学技术学院（Cornell Tech）的一支研究团队，包括 Offchain Labs 的首席执行官兼联合创始人 Steven Goldfeder，开发了首个去中心化公平排序算法。通过一些正在开发中的改进，这些概念将成为我们长期解决方案——去中心化公平排序器的基础。

### Bridging 跨链桥
在 Arbitrum 的生态系统中，跨链交互指的是 L1（以太坊）与 L2（Arbitrum 等）链之间的合约调用。我们已经讨论过用户如何与 L2 合约交互——通过将消息提交到链的收件箱，或者通过完整节点（如排序器或聚合器）代为提交。但现在我们要探讨的是，L1 合约如何调用 L2 合约，以及反之如何实现。

由于 L1 和 L2 链是异步运行的，无法在同一个交易中完成跨链调用并立刻得到结果。换句话说，跨链合约间的调用必须是异步的，这意味着调用方提交调用请求的时刻与调用执行的时刻之间存在时间差。因此，跨链的合约对合约调用永远无法立即返回调用结果（除了确认调用成功提交以待后续执行外）。

#### L1 合约如何提交 L2 交易
L1 合约可以像用户一样，通过调用以太坊上的 Nitro 链的收件箱合约来提交 L2 交易。这个 L2 交易会在之后执行，产生的结果不会对 L1 调用方可见。换句话说，L1 调用方无法看到 L2 交易的任何执行结果。

**优点与缺点**
- 优点：这种方式简单且延迟较低。
- 缺点：与其他稍后描述的方法相比，如果 L1 调用方没有正确设置 L2 的 gas 价格和最大 gas 限制，L2 交易可能会失败。由于 L1 调用方无法看到 L2 交易的结果，它无法完全确保 L2 交易会成功。
这对于某些 L1 到 L2 的交互来说，可能会引入严重的问题。例如，考虑一个交易场景，其中涉及将一个代币从 L1 存入，并希望在 L2 的某个地址可用。如果 L1 侧成功，但 L2 侧回滚，那么你可能会把代币发送到 L1 收件箱合约中，而这些代币在 L2 或 L1 都无法找回，这显然是不理想的。

#### L1 到 L2 基于票据的交易
幸运的是，我们有一种更强健的方法来处理 L1 到 L2 的调用，它能更好地应对因 gas 相关失败而产生的问题，即使用基于票据的系统。其基本思路是：L1 合约可以提交一个“可重试”的交易。Nitro 链会尝试执行该交易。如果成功执行，则不需要做其他操作；如果失败，Nitro 会创建一个标识失败交易的“ticketID”。稍后，任何人都可以调用 L2 上的特殊预编译合约，并提供该 ticketID，来尝试赎回该票据并重新执行交易。

**工作流程：**
- 保存交易信息：在保存交易进行重试时，Nitro 会记录发送方的地址、目标地址、调用值和调用数据等信息。所有这些信息都会被保存，并且调用值会从发送方账户中扣除，并与保存的交易逻辑上相关联。
- 交易赎回：如果赎回成功，交易执行完成并会发出回执，同时 ticketID 会被取消，不能再次使用。如果赎回失败（例如，打包的交易失败），赎回会报告失败，ticketID 将保持可用状态，允许其他人再次尝试赎回。
**特点：**
- 提交成本：提交交易时需要支付一定的 ETH，费用依据交易的 calldata 大小而有所不同。提交后，票据有效期为大约一周。如果在此期间票据未被赎回，它将被删除。
- 赎回执行：当票据被赎回时，原始提交者的发送方和来源地址会被保留，目标地址、调用值和调用数据将保持为提交时的内容。
这种方法相比普通的 L1 到 L2 交易稍显复杂，但它有一个优点：提交成本是可预测的，并且如果提交成本已支付，票据始终可以赎回。只要有愿意赎回票据的用户，L2 交易最终可以执行并且不会被悄然丢弃。

#### L2 到 L1 基于票据的调用
L2 到 L1 的调用也使用类似的票据系统。L2 合约可以调用预编译的 ArbSys 合约中的方法，将交易发送到 L1。当 L2 中包含提交的交易执行被确认到 L1（几天后）时，L1 的出站合约会创建一个票据。任何人都可以通过调用特定的 L1 出站方法并提交 ticketID 来触发这个票据。票据仅在 L1 交易未回滚时才会被标记为已赎回。

**特点：**
- 无限期有效：这些 L2 到 L1 的票据具有无限的有效期，直到它们成功赎回为止。
- 无需租金：不需要支付租金，因为票据（实际上是票据的 Merkle 哈希）记录在以太坊存储中，而以太坊存储不需要租金（但票据 Merkle 根的存储费用由 L2 交易费用覆盖）。

### Gas 和费用（Fees）
在 Arbitrum 的 Nitro 链上，NitroGas 被用来跟踪链上执行的费用。为了避免与以太坊（L1）的 gas 混淆，称其为 NitroGas。它的运作方式与以太坊的 gas 相似：每个 EVM 指令的消耗与在以太坊上的 gas 成本相同。

### 速度限制（Speed Limit）
Nitro 链的安全性依赖于一个假设：当一个验证者创建一个 RBlock（Rollup Block）时，其他验证者会检查该 RBlock，并在它出错时作出响应，提供正确的 RBlock 和挑战。这要求其他验证者有足够的时间和资源快速检查每个 RBlock，以便及时发起挑战。Arbitrum 协议基于这一点为 RBlock 设置了提交的最后期限。

这就设定了 Nitro 链执行的有效速度限制：从长远来看，链的进度不能超过验证者模拟其执行的速度。如果 RBlock 的发布速度超过了这个速度限制，它们的最后期限将越来越长。由于协议合约对最后期限的限制，最终会导致新的 RBlock 执行速度减缓，从而强制执行有效的速度限制。

为了准确设定速度限制，需要能够大致估计验证 RBlock 所需的时间。如果验证时间估算不准确，就不得不设置较低的速度限制，以确保安全性。因此，Arbitrum 尝试确保验证时间的估算尽可能准确，以避免过度保守地降低速度限制。 

### 费用（Fees）
用户交易需要支付费用，以覆盖链的运营成本。这些费用由 ArbOS 在 L2 进行评估和收取，并以 ETH 计价。

费用按交易使用的两种资源进行收取：

- L2 gas：执行 Nitro 链上的交易所需的 Ethereum 等效 gas。
- L1 calldata：与交易相关的 L1 calldata 费用，仅当交易通过排序器（Sequencer）提交时才会收取，用于覆盖排序器的费用。

### 2024.12.19
### Arbitrum Nova
Arbitrum Nova 是 Arbitrum 生态系统中另一种 Layer 2 解决方案，Arbitrum Nova 与 Arbitrum One 服务于不同的需求和场景。

![image](https://github.com/user-attachments/assets/8888f62b-701e-454a-a97f-7f46ef41b147)

Arbitrum One 和 Arbitrum Nova 底层都使用 nitro 技术，但 Arbitrum One 使用普通模式，Arbitrum Nova 使用 anytrust 模式。与 Arbitrum One 采用 Rollup 技术不同的是，Arbitrum Nova 利用 AnyTrust 技术（下一节会详细讲解），这个技术的核心在于创建了一个被信任的小组，叫做数据可用性委员会（下一节会详细讲解），因为有这个小组帮助我们记录交易数据，我们牺牲了一定程度的去中心化，但换取了性能的提升，非常适合游戏、社交媒体和轻量级金融应用等对速度和成本敏感的场景。

### 内部AnyTrust
AnyTrust 是一种 Arbitrum Nitro 技术的变种，它通过接受一定程度的信任假设来降低成本。

Arbitrum 协议要求所有 Arbitrum 节点，包括验证者（即验证链正确性并准备对正确结果进行担保的节点），都必须访问 Arbitrum 链的所有 L2 交易数据，并将其发布到以太坊 L1 作为 calldata。用于支付以太坊 gas 的费用是 Arbitrum 的最大成本组成部分。

而 AnyTrust 则依赖于外部的 **数据可用性委员会**（以下简称“委员会”）来存储数据并按需提供。这意味着 AnyTrust 假设委员会中的至少两个成员是诚实的。也就是说，如果委员会中的 N - 1 名成员承诺提供某些数据，则至少有一名诚实的成员会提供数据来确保链能正常运行。

#### 密钥集 (Keysets)
一个密钥集指定了委员会成员的公钥，以及有效的数据可用性证书需要的签名数量。密钥集使得委员会成员的更换成为可能，并允许他们更改公钥。

一个密钥集包含：

- 委员会成员数量
- 每个委员会成员的 BLS 公钥
- 需要多少个委员会成员的签名才有效
- 密钥集通过其哈希值进行标识。

L1 KeysetManager 合约维护着当前有效的密钥集列表。L2 链的拥有者可以添加或删除这些密钥集。当一个密钥集变得有效时，KeysetManager 合约会发出一个包含密钥集哈希及其完整内容的以太坊事件，这样任何人都可以根据密钥集哈希值恢复密钥集内容。

尽管 API 并未限制可以同时有效的密钥集数量，但通常情况下只有一个密钥集会被设为有效。

#### 数据可用性证书 (DACert)
![image](https://github.com/user-attachments/assets/3738e2d0-5e74-40c3-bb65-e7eccf9001cf)

AnyTrust 的核心概念是 **数据可用性证书**（DACert）。一个 DACert 包含：

- 一个数据块的哈希
- 一个过期时间
- 证明有 N-1 个委员会成员签署了（哈希，过期时间）对的证据，包括：
  - 用于签名的密钥集哈希
  - 一个位图，显示哪些委员会成员签署了
  - 一个 BLS 聚合签名（基于 BLS12-381 曲线），证明这些签名成员进行了签名
由于采用了 2-对-N 的信任假设，DACert 证明至少有一个诚实的委员会成员在过期时间之前会提供数据。

在普通的（非 AnyTrust）Nitro 中，Arbitrum 的 Sequencer 会将数据块作为 calldata 发布到 L1 链上。数据块的哈希会被 L1 Inbox 合约提交，确保 L2 代码能够可靠地读取这些数据。

而 AnyTrust 给了 Sequencer 两种发布数据块到 L1 的方式：它可以像普通 Nitro 一样发布完整数据，也可以发布证明数据可用性的 DACert。L1 Inbox 合约会拒绝任何使用无效密钥集的 DACert；DACert 的其他有效性检查由 L2 代码进行。

L2 代码读取 Inbox 中的数据时，如果看到的是完整数据块，就像普通 Nitro 一样进行读取；如果看到的是 DACert，它会检查 DACert 的有效性，参考其中的密钥集（该密钥集会被 L1 Inbox 验证过）。L2 代码会验证：

- 签署者的数量是否至少满足密钥集要求的数量
- 聚合签名是否对已声明的签署者有效
- 过期时间是否至少比当前 L2 时间戳晚两周
如果 DACert 无效，L2 代码会丢弃该 DACert 并跳过；如果 DACert 有效，L2 代码将读取数据块，并确保数据是可用的。

#### 数据可用性服务器 (DAS)
![image](https://github.com/user-attachments/assets/9065e0b3-572a-4928-a1fc-b6064fdfbcb6)
委员会成员运行数据可用性服务器（DAS）软件。DAS 提供两个 API：

- **Sequencer API**：该 API 仅供 Arbitrum 链的 Sequencer 使用，它是一个 JSON-RPC 接口，允许 Sequencer 将数据块提交到 DAS 存储。通常部署会限制其他调用者访问该 API。

- **REST API**：这是一个面向全体用户的 RESTful HTTP(S) 协议，允许根据哈希获取数据块。此 API 是完全可缓存的，部署可以使用缓存代理或 CDN 来增加扩展性，并防止 DoS 攻击。

只有委员会成员有理由支持 Sequencer API。我们希望其他人能运行 REST API，这会有很大的帮助。

DAS 软件根据配置选项可以将数据存储在本地文件中、Badger 数据库中、Amazon S3 上，或者在多个后端存储中冗余存储。该软件还支持可选的内存缓存（使用 Bigcache）或 Redis 实例。

#### Sequencer 与委员会的交互
![image](https://github.com/user-attachments/assets/b3a48664-7b87-4383-98b2-d8afa48c7185)
当 Arbitrum Sequencer 生成一个数据批次，并希望使用委员会发布时，它会将数据和过期时间（通常是三周后）通过 RPC 同时发送给所有委员会成员。每个委员会成员将数据存储在其后端存储中，并通过 BLS 密钥对（哈希，过期时间）对进行签名，然后将签名与成功指示一起返回给 Sequencer。

一旦 Sequencer 收集到足够的签名，它就可以聚合这些签名并生成有效的 DACert。然后，Sequencer 将该 DACert 发布到 L1 Inbox 合约，使其可供 AnyTrust 链的 L2 软件使用。

如果 Sequencer 未能在几分钟内收集到足够的签名，它将放弃使用委员会，并通过“回退到 Rollup”方式，直接将完整数据发布到 L1 链上，这就像在非 AnyTrust 链中一样。L2 软件能够理解两种数据发布格式（DACert 或完整数据），并会正确处理每一种格式。

### One/Nitro跟Nova的核心区别

One 将完整的数据以 Calldata 的形式发布到以太坊主网，由于 Calldata 占用了一定的主网区块空间，此操作支付的 gas 费是 One 成本最大的组成部分。

Nova 提供了 2 种数据发布方式，一种是像 One 一样以 Calldata 的形式发布完整数据，另一种是发布 DACert 证明数据的可用性。 Nova 的排序器将完整的数据同时发送给所有 DAC（数据可用性委员会）成员，委员会签名后把带有签名的证明返回给排序器，排序器收集到足够多的证明就能将它们聚合并创建有效的数据可用性证明（ DACert ），然后把 DACert 发布到主网。 如果排序器没有收集到足够多的证明，Nova 会回退到 One 模式（以 Calldata 形式发布完整数据到主网）。

### 2024.12.20
### Arbitrum Orbit
Arbitrum Orbit 是 Arbitrum 在2023年3月推出的新产品，用户可以利用 Arbitrum Orbit 构建自己的 Layer3（建立在 Layer1 以太主网和 Layer2 之上的链，所以被称为 Layer3 ），可以将它们视为定制链——精确定制以适应你的具体使用场景和业务需求的链。它让用户在构建自己的 Orbit 链时可以灵活选择使用 Rollup（如 Arbitrum One ）或 AnyTrust 技术（如 Arbitrum Nova ），用户自定义 Arbitrum Orbit 链的隐私、权限、费用代币、治理等。 用下图理解 Layer1，Layer2 和 Layer3 之间的关系：

### Why Orbit?
Arbitrum One 和 Arbitrum Nova 这两个公共链已经满足了大多数项目的需要——它们已经支持了数千个应用和数百万用户。但并不是所有人都适合共享的公共链，比如 Arbitrum One 和 Arbitrum Nova 由 Arbitrum DAO 拥有和管理，有了 Orbit 链，你可以决定你的链如何被治理。

**Orbit 优势**
- **专用吞吐量**：如果你的去中心化应用（ dApp ）需要高性能或持续的资源可用性，你可能需要专用吞吐量。在自己的 Orbit 链上运行你的 dApp 显著增加资源可用性，因此你不需要为计算和存储资源竞争。
- **EVM+ 兼容性**：当 Stylus 准备就绪时，Orbit 链将享受 Stylus 引入的相同 EVM+ 兼容性（将在下一章中介绍）。这意味着你将能够使用 Solidity、C、C++ 和 Rust 部署 EVM 兼容的智能合约——无需迁移你已在使用的语言。
- **独立产品路线图**：如果你想将你的应用链的路线图与以太坊或 Arbitrum 的路线图分离，Orbit 使这成为可能。这让你能够提前实施前沿功能，如账户抽象化，超前于遵循以太坊公共路线图的项目。
- **增加 gas 价格可靠性**：许多类型的 dApp 依赖于可预测的交易成本。因为 Orbit 链与 Arbitrum L2 和以太坊 L1 流量隔离，使用 Orbit 链意味着你不会受到其他应用链上活动的显著影响，允许你的 dApp 用户享受更可靠的 gas 价格。
- **自定义 gas 代币**：Orbit 链可以在网络上使用替代 ERC-20 代币作为原生 gas 代币支付 gas 费，便于与你的应用生态系统无缝集成。这目前支持 AnyTrust 链。
> ERC20 是一种遵循特定规则的智能合约标准，专为以太坊区块链上的代币设计。简单来说，它是一个模板，定义了代币的一些基本功能，比如转账、获取账户余额、代币总供应量等。
- **灵活的技术选项**：Orbit 允许你在 Rollup、AnyTrust 或自定义技术栈之间选择。这使得以太坊和 Arbitrum 技术更加适应性，允许你仅纳入你需要的技术元素。

### 2024.12.21
### Arbitrum Stylus
2023年8月31日，Arbitrum 开发团队 Offchain Labs推出了下一代编程环境 Arbitrum Stylus 的代码和公共测试网。 Stylus 是对 Arbitrum Nitro 技术栈的升级，该技术栈支持 Arbitrum One、Arbitrum Nova 和 Arbitrum Orbit 链。此次升级在 EVM 中增加了第二个虚拟机，EVM 合约的行为完全如同它们在以太坊中的行为一样。我们称这种范式为 EVM+。

> 以太坊虚拟机（ Ethereum Virtual Machine，简称 EVM ）是以太坊区块链的核心组件之一，负责执行以太坊网络上的所有智能合约代码。EVM 是一个完全隔离的虚拟环境，可以在全球任何一个节点上以相同的方式执行代码，确保了以太坊网络的去中心化和安全性。

这第二个虚拟机执行的是 WebAssembly（ WASM ）而不是 EVM 字节码。有了 WASM 虚拟机，任何能够编译成 WASM 的编程语言都在 Stylus 的覆盖范围内。这就意味着传统互联网领域的程序员们如果熟练掌握 Rust、C、C++ 等可以编译为 WASM 的编程语言，那么他们无需额外学习 Solidity 等原生智能合约开发语言，也可以参与到区块链合约开发中。

> WebAssembly（ WASM ）是一种为网络浏览器设计的低级字节码格式，开发者可以使用 C、C++、Rust 等多种语言编写代码，然后编译成 WASM。这为不同背景的开发者提供了更多的选择，使得他们可以使用自己熟悉的语言来开发 Web 应用程序。引入 WASM 到区块链技术，意味着开发者可以使用多种编程语言来编写智能合约，而不仅仅是 Solidity。

### Stylus 是如何工作的
Stylus 是一个允许开发人员使用不同编程语言创建智能合约的区块链平台，将智能合约的开发和部署分解为四个主要步骤：编码、编译、执行和验证。

1.编码：开发人员可以选择任何能够被编译成 WASM（ WebAssembly ）的语言来写智能合约。Stylus 最初将支持 Rust、C 和 C++ 语言，其中 Rust 将提供丰富的开发工具包。 

2.编译：智能合约代码首先从高级语言（比如 Rust、C 或 C++ ）编译成 WASM 格式。然后通过一个叫做 ArbWasm 的工具将 WASM 编译成适合特定硬件平台上的本机代码。 

3.执行：编译好的程序在 Wasmer runtime 中执行，这是一个专门为 WASM 设计的高性能 runtime，设计用于在非浏览器环境中运行 WASM 文件。

4.验证：在大多数情况下，智能合约的执行会直接编译成本机代码并顺利运行。如果出现验证者之间的争议，Stylus 使用前文讲解的 Nitro 技术，将执行历史转换回 WASM 格式，以便在以太坊上进行验证和解决争议。

### Why Stylus?
**使用流行的编程语言进行原生以太坊开发**：
利用流行的 WASM 兼容语言如 Rust、C 和 C++ 在 Arbitrum 的大型生态系统上构建应用，将流行的互联网编程语言与区块链智能合约原生语言结合起来。

**完全可组合性**：
Solidity 合约和 Stylus 合约是完全互操作的。如果在 Solidity 中工作，开发者可以调用 Rust 程序。如果在 Rust 中工作，所有 Solidity 功能都可以直接使用。

**更快的计算，更低的成本**：
由于 WASM 程序的高效率，Stylus 合约的速度快了十倍以上，且具有显著较低的 gas 费用。使用 Stylus 时，内存的成本降低了100-500倍。

**启用新的使用案例**：
Stylus 对成熟的 WASM 生态系统的访问打开了之前不能实现的新 EVM 使用案例。比如将用 C++ 编写的现有游戏上链，以及计算密集型 AI 模型都变得更加容易访问。

### 2024.12.22
### Arbitrum 创新的技术路线图
Arbitrum 致力于通过“你的链，你的规则”理念，推动区块链技术的发展，提升可用性、互操作性和实用性。以下是其主要技术路线图：

#### 1.开发者体验与采用

- **Stylus**：支持如 Rust、C 和 C++ 等 WebAssembly（WASM）编程语言，提升开发效率和智能合约的性能与安全性，同时节省 gas 费用。Stylus 将在 Arbitrum Day 上在 Arbitrum One 和 Nova 主网上线，标志着生态系统的重大升级。

#### 2.去中心化

- **BoLD（2024 下半年）**：增强安全性，实现去中心化验证，迈向 L2 Rollup 的最终阶段。
- **Censorship Timeout（2024 下半年）**：限制重复审查或序列器下线对链的负面影响，提升审查抵抗能力和用户资金访问。
- **去中心化序列器（预计 2025 年）**：分散交易排序责任，减少审查攻击风险，提升可靠性。

#### 3.互操作性与横向扩展

- **快速提款（2024 第三季度）**：允许 AnyTrust 链在几分钟内结算到主链，促进链间快速通信和横向扩展。
- **链集群（预计 2025 年）**：通过多个 Orbit 链的紧密协作，减少跨链通信时间，实现近即时的横向扩展。

#### 4.性能与效率

- **多客户端支持（2025 上半年）**：支持多种执行层客户端（如 Reth 1.0、Erigon 3.0 和 Nethermind），优化区块生产速度，降低节点运营成本，提升系统吞吐量。
- **自适应定价（2025 上半年）**：根据实际资源使用情况动态调整 gas 限制，提高网络性能和资源利用率，增强对极端流量模式的韧性。

#### 5.零知识证明

- **ZK+Optimistic 混合证明**：结合零知识证明和乐观验证，提供快速确认路径，提升链间原生互操作性。

### 2024.12.23

### Arbitrum生态系统
Arbitrum 的生态系统已经涵盖了多个领域，尤其是在 DeFi 和消费者应用方面展现出强大的发展潜力。

#### DeFi
去中心化交易所 (DEX)
Arbitrum 的 DEX 活动在2023年超过了 Polygon，使其成为以太坊外最大的 DEX 网络。最初，Uniswap、SushiSwap、Curve 和 Balancer 占据了 Arbitrum DEX 的主导地位。然而，随着生态系统的发展，新兴的协议，如 Camelot，开始挑战这些主流 DEX。Camelot 提供了动态和定向的交易费用结构，允许池中的每项资产根据市场条件进行调整，从而吸引了更多的用户和流动性。

借贷平台
Radiant 是 Arbitrum 上最受欢迎的借贷协议，采用了跨链借贷的模式，并提供了激励措施来鼓励用户存款和借贷。此外，Aave V3 也在 Arbitrum 上获得了较大的市场份额，后者没有通过代币激励用户，而是凭借其强大的借贷产品逐渐发展。

永续合约
在 Arbitrum 的 DeFi 生态系统中，GMX 是最领先的永续合约协议，占据了大部分市场份额。它采用了 AMM 订单簿混合模式，解决了传统 DeFi 永续合约的高手续费和复杂性问题。随着 Vela Exchange 和 Gains Network 等新竞争者的崛起，GMX 的市场份额略有下降，但它仍然在 TVL 和交易量方面保持领先地位。

期权协议
Lyra 和 Dopex 是 Arbitrum 上领先的期权协议。Lyra 在 2023 年实现了显著增长，并吸引了更多用户和流动性。期权协议在 Arbitrum 上的逐步发展表明，随着市场的成熟，Arbitrum 可能成为去中心化期权市场的核心平台之一。

#### 消费者应用
Arbitrum Odyssey
作为 Arbitrum 的新用户获取活动，Arbitrum Odyssey 在 2022 年大获成功，尽管由于网络拥堵，活动进展有所延误。该活动通过提供 NFT 奖励吸引用户参与，并在一定程度上促进了 Arbitrum 网络的早期增长。

游戏应用
Arbitrum 的 Treasure 协议 是 Web3 游戏的核心生态系统，旨在成为“Web3 的任天堂”。在 Treasure 平台上发布的游戏可以互相操作，同时享受其原生 DEX（MagicSwap）和 NFT 市场（Trove）提供的网络效应。Treasure 的成功与其强大的社区以及游戏之间的互操作性密切相关。

### 2024.12.24
忘记打卡了

### 2024.12.25
### $ARB代币：概念概述

$ARB代币是一种ERC-20治理代币，允许持有者参与Arbitrum DAO的链上治理协议。$ARB代币由部署在Arbitrum One上的智能合约铸造，Arbitrum One是一个Layer 2 Arbitrum Rollup链。

Arbitrum DAO负责管理《宪法》中定义的治理协议，以及DAO所治理的技术。这包括Arbitrum One和Arbitrum Nova链，以及它们的底层协议。

如果您持有$ARB代币，您可以对影响Arbitrum One和Arbitrum Nova链运行和发展的治理提案进行投票。这包括链的升级提案，以及如何使用DAO国库资金的提案。

当您对链上提案进行投票时，您实际上是在使用您的$ARB代币表示支持或反对。您持有的$ARB代币越多，您的投票影响力就越大。这是因为Arbitrum DAO的智能合约是基于代币加权的投票机制，也就是说，投票的权力是根据投票者钱包中代币的数量来确定的。

请注意，$ARB代币可以委托给其他钱包。这意味着，您不仅可以使用自己钱包中的$ARB代币进行投票，还可以使用其他人的$ARB代币，只要这些代币的拥有者将投票权委托给了您。委托对于那些没有时间定期审查和讨论DAO提案的DAO成员来说非常有用。

$ARB的初始供应量为100亿个。新的$ARB代币最多每年可以按供应量的2%的速度铸造，其中第一次铸造将于2024年3月15日开始有资格进行。$ARB的铸造事件由DAO通过宪法提案执行。

总之，$ARB代币是一种特殊用途的数字资产，赋予持有者对影响Arbitrum DAO及其所治理技术的链上提案进行投票的能力。持有$ARB代币允许您与其他具有相同价值观和激励机制的代币持有者一起，民主地塑造Arbitrum生态系统的未来。

### 2024.12.26

### Airdrop Eligibility & Distribution (空投资格与分发)
- 空投目的：为了奖励并激励Arbitrum网络上的早期用户和支持者，空投将分发ARB代币。
- 资格标准：为了符合空投资格，用户需要满足一定的条件，包括：
  - 在Arbitrum网络上进行过交易。
  - 参与过Arbitrum的任何测试网或活动。
  - 使用过Arbitrum的协议和DApp。
- 分发方式：空投将按照每个用户在网络中的活跃程度进行分配，确保奖励给那些真正支持Arbitrum的用户。具体分配规则包括根据交易数量、参与度等进行分配。

### Token Supply (代币供应)
- 总供应量：ARB代币的总供应量为1,275,000,000个，其中大部分会分配给社区和生态系统的参与者。

- 分配方案：
  - 社区奖励：约42.8%（约546,000,000个ARB）将分配给社区，包括空投、激励和生态系统奖励。
  - 团队与基金会：约26.2%（约334,000,000个ARB）将用于奖励团队成员、顾问以及基金会的运营。
  - 投资者与合作伙伴：约19.8%（约252,000,000个ARB）将分配给早期投资者和合作伙伴。
  - 流动性和生态系统发展：约11.2%（约143,000,000个ARB）将用于网络流动性和生态系统发展。
- 解锁计划：这些代币将逐步解锁，并有一定的时间表，以确保代币的长期稳定性和社区的参与。
<!-- Content_END -->
