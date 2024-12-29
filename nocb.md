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

# Hansen

1. 虽然很早就了解过arb，但没有系统的学习和使用过。
2. 你认为你会完成本次残酷学习吗？  应该可以完成 ，抽时间学习 

## Notes

<!-- Content_START -->

### 2024.12.10

#### ARB基础介绍

- ARB is Optimistic rollup protocol ，is a L2  
- L2 是为了Ethereum的扩容
- L1 保证了L2的安全性，
- The only delay that's felt by a user is in "withdrawing" — moving their funds from Arbitrum back to Ethereum;
- 批次，压缩 ，所以L2的费用低和效率高
- 最新技术栈：Stylus ，可以支持 rust 

### 2024.12.11

- ARB have 2 chain ，Arbitrum One   and  Nova. Orbit can create L3
- Arbitrum DAO  

#### Arbitrum suite

The Arbitrum suite includes the protocols, chains, services, and SDKs that power the Arbitrum ecosystem:

Arbitrum Rollup:	A protocol for scaling Ethereum smart contracts.
Arbitrum AnyTrust	A protocol for scaling Ethereum smart contracts even further, with a mild trust assumption.
Arbitrum Nitro	The node software that codifies the Rollup and AnyTrust protocols.
Arbitrum nodes	Machines that run Nitro in order to service and/or interact with an Arbitrum chain.
Arbitrum One	A public Rollup chain.
Arbitrum Nova	A public AnyTrust chain.
Arbitrum bridge	Lets you move ETH and ERC-20 tokens between Ethereum, Arbitrum, and select Orbit chains.
Arbitrum Orbit	Lets you run your own Rollup and AnyTrust chains.
Arbitrum Stylus  write contract with rust  

- 用户通过bridge ，dapp 来使用arb 
- 开发者可以使用  solidity and rust 语言  
- 矿工 运行全节点 nitro 
- 通过orbit 可以创建自己的 L3  

#### chain info  

- 介绍了 RPC 的地址 和特点 
- 介绍了一些共用的 rpc provider  
- 介绍了 几个重要的合约地址 ，及欺诈证明合约 ，bridge ，及水龙头

### 2024.12.12

#### 创建Dapp 
- ui -> provider -> node -> contract
- 就像前后端分离一样，   ui 是前端， 合约是服务， 用solidity 语言写，部署在去中心化网络。

### 2024.12.13
#### run Arbitrum node 
- 节点类型：  full node， archive node，classic node 

一般运行full 节点 就可以了 ， 比归档节点要省资源， 

- Nitro ，full node  
	- hardware： 普通的电脑即可 
	- 可以用docker 
	- snapshot  可以快速同步  
	- 也有rpc 的接口 
	- 需要和 L1 的接口对接 

- 创建一个本地的为开发用的 虚拟链 
- L1 provider  
	- data stored in blob ，on the beacon chain. 

### 2024.12.14

### 2024.12.15
#### L2技术类型
- Zk Rollups是指一种利用零知识证明的密码学算法，在无需知道验证者是谁的情况下，完成外包工作的Layer2方法。
- Optimistic Rollups是指利用一堆验证者，在默认打包是好的情况下，通过奖惩机制，监督发掘是否有Bug的Layer2方法。
	- Optimism和Arbitrum都是Optimisctic Rollups方法为基础开发的项目。
	- starknet  是 zk rollup 

#### ARB的逻辑
- Rollup 上，对合约的调用及其 argument（实际参数）都是作为调用数据（calldata）写在链上的，但是合约的实际计算和存储都是在链下完成的
这个发布上链的断言将所有的调用和结果都 “卷起来”（“rolling up”）成为单笔发送上链的交易。

- AVM 是L1 和L2 直接的网关，avm读取输入，计算，输出
- Nitro 是 One 的技术栈升级，
- Arbitrum Nova 是基于 AnyTrust 技术搭建的新链，专为游戏、社交应用程序和对成本更敏感的用例而设计-
- Arbitrum Orbit 是一个开发框架，
- Stylus 是 Arbitrum 开发的支持多语言构建应用程序的开源 SDK 

### 2024.12.16

#### 深入理解 Arbitrum

- 交互式欺诈证明 是arb 的重要设计原则。   （但自己并没有看太懂）

#### Arbitrum 创新的技术路线图
Your Chain, Your Rules 
- Stylus 
	- 允许使用更高效、好用的语言
	- 加强去中心化的建设
	- Orbit 扩展网络的，
		- 多客户端支持
		- 自适应定价  
	- ZK+乐观混合证明：zk可以立即确认断言，

### 2024.12.17

#### Arbitrum生态

- DEX ：Camelot
- 贷款： Radiant、Aave V3
- 永续合约：GMX
- 期权： Dopex   
- 资格认证 - Odyssey
- 游戏： Treasure

### 2024.12.18

####  上百个生态项目
总体看上去 arb 的生态已经比较全，

#### Orbit 生态
one ：是op rollup L2
nova： 基于anytrust 的游戏链 
orbit：是L3  

### 2024.12.19

#### Constitution of the Arbitrum DAO 章程
一些章程写在了合约里面，
https://www.tuoluo.cn/article/detail-10106172.html   中文的说明

#### DAO 治理工具 
Tally  Snapshot 
 
#### 章程主要内容框架如下： 
- AIP :
- 管理的chains
- DAO 的金库
- Governed Chains：ARB 管理的链
- Non Governed Chains
- 能投票的token 

#### 具体内容 
- chain的归属权  
	- 任何ArbitrumDAO批准的链，都必须与以太坊结算
	- 一个AIP 授权一个链 
- AIP 的流程 
	- 1.Temperature Check ，在snapshot 上发布1周
	- 2.正式AIP 及呼吁vote ，3天

### 2024.12.20

#### AIP 的流程 

- 第 1 阶段——临时检查（1 周）： 在社区论坛上提出建议，并讨论/辩论 1 周。 提案者可以在 Snopshot 上建立一个投票，以衡量社区对提案的兴趣。 
- 第 2 阶段——正式提交 AIP（3 天）： 通过临时检查后，提案者通过 Arbitrum 上的治理合约提交 AIP。 提案者必须拥有一个至少委托 500 万个 $ARB 的地址。 
- 第 3 阶段——DAO 对 AIP 进行投票（14-16 天）： Arbitrum DAO 将能够直接在链上对提交的 AIP 进行投票。 如果满足以下条件，则 AIP 将通过： •“赞成”票为多数（阈值 1）； •对于宪法性 AIP，至- 少 5% 的 $ARB 需要投“赞成”票；对于非宪法性 AIP，至少 3%。 如果 API 通过了，则进入第 4-7 阶段；反之，AIP 将进入第 4 阶段，然后进入第 7 阶段。 
- 第 4 阶段——L2 等待期（3 天）： 第 3 阶段后，有 3 天的等待期，在此期间，未通过的 AIP 可以提取资金； 
- 第 5 阶段——启动并完成 L2→L1 消息（至少 7 天）： 在以太坊上发送 L2-to-L1 消息，表明 AIP 已通过。 
- 第 6 阶段——等待期 （3 天）： 确保投票用户有时间在 AIP 生效前取款。 
- 第 7 阶段——执行和实施 AIP 平均而言，宪法性 AIP 的流程从临时检查到最终执行大约需要 37 天，而非宪法性 AIP 通常需要 27 天

### 2024.12.21

#### AIP 类型
- 宪法性 AIP 包括： 
	- 修改 DAO 规则
	- 软件更新：安装或修改任何链上的软件；
	- 核心：采取任何需要“链所有者”的操作；
	- 新链批准：批准一条新链。（治理链和非治理链）
- 非宪法性 AIP 包括：
	- 资金：提议如何从 DAO 国库支出或分配资金；
	- 信息：向社区提供指导或信息

#### 委托投票

你可以通过将你的投票权委托给其他人来表达你的意见，
- 要委托投票权，你需要一个持有 $ARB 的以太坊钱包
- Tally 上，委托给你信任的人

#### 安全委员会 
9-12 多重签名钱包的 12 名成员，能够执行 Arbitrum DAO 的投票结果以及紧急行动，负责维护 Arbitrum 链。
紧急事件， 非紧急事件

### 2024.12.22
#### 如何提交一个AIP 协议
- 前提： 
	- temperature check using snapshot , 50w token
	- submit proposal by tally ,1M token 
- 类型：宪法型  和 非宪法型 
- 结构
	- 概要
	- 动机 
	- 根本原因
	- 关键条款
	- 规范，详单 
	- 每一步的实现 
	- 时间线
	- 总的费用
	- 如果第二次提交，需要有 上一次的link，拒绝原因，变化，附加信息


### 2024.12.23

#### 治理理念
- Arbitrum DAO 是以太坊区块链上的去中心化自治组织，通过社区驱动治理， 
- ARB的持有者可以对组织及技术变化，提议、投票。
- 他基于智能合约的金库系统，安全理事会来管理，（半年一选），Security Council Members ， 12位，公开了其地址  

#### 治理的论坛 
https://forum.arbitrum.foundation/

#### 案例分析
- amelot 是 Arbitrum 上最大的原生 DEX
- 申请资金最多的是 Arbitrum 上 DeFi 类代表项目 GMX

- 参与者也需要额外满足一系列条件，如：
	- 必须明确支出计划和目标，不得将 ARB 转换为其它资产；
	- 必须承诺提供有关分配、ARB 支出、交易量、TVL、唯一地址、交易费用等指标；
	- 必须完成 Arbitrum 基金会的 KYC；
	- 资金只能用于 Arbitrum 网络上的激励等。

### 2024.12.24


### 2024.12.25


### 2024.12.26
   昨天忘记 提交了  

#### Arbitrum 开发文档
https://docs.arbitrum.io/welcome/get-started

https://github.com/dysquard/Arbitrum_Doc_CN   中文文档

- Arbitrum 门户
https://portal.arbitrum.io/?chains=arbitrum-one

- 测试链 
	- https://rinkeby.arbitrum.io/rpc
	- ChainID: 421611
	- 浏览器 https://rinkeby-explorer.arbitrum.io/#/
	- 水龙头： https://faucet.rinkeby.io/

- 运行 Arbitrum One完整节点
	- Docker镜像: offchainlabs/arb-node:v1.3.0-d994f7d
	- 数据库应挂载到外部磁盘，以便在重启时能永久保存数据
	- Arbitrum 中继： 当运行多个节点时，你希望运行一个 Arbitrum 中继并为所有节点提供回馈

### 2024.12.27

https://github.com/dysquard/Arbitrum_Doc_CN/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3%E5%8D%8F%E8%AE%AE/%E6%B4%9E%E6%82%89Arbitrum.md 
#### 机制的深入理解  
- Arbitrum是一种rollup，这意味着对Arbitrum链的输入也即收件箱中收到的信息，全部都以**calldata**的形式被记录在以太坊上。每个人都能查看收件箱的完整历史，而链状态又完全取决于收件箱历史。因此，仅凭借公开信息就可以决定当前正确的链状态的信息。如有必要，还可重建整个链状态。
- rollup 协议是在L1 上的合约。
- 挑战期（大约为一周）结束后仍没有对rollup区块提出挑战，Arbitrum就会将该rollup区块认定为正确的
- 作恶者的质押资金将被没收，其中一部分将奖励给诚信者
- 如何解决争议？  **交互式证明**：
  	- 分解争议， 直到找到争议行为
  	- L1的仲裁合约，对行为进行判定 

![image](https://github.com/user-attachments/assets/db849ddc-19a2-49ab-bde0-37567b576ea1)

#### L2 的架构
- EVM兼容层,ArbOS,AVM,ethBridge, L1
- evm兼容层的合约， 可以加载到 Arbos内，
- AVM 读取输入，计算，再输出， 是L2 和L1 的分界线
- ethBridge 是L1层的合约， AVM的输出结果，会传入这里的rollup合约，写入到L1 ，或执行仲裁合约。 


### 2024.12.28

#### EthBridge 是为了管理Arb的，在L1层的一组合约，包括
1. 收件箱合约，链的输入
2. 发件箱合约，链的输出
3. Rollup 合约：
	- rollup协议并不决定交易的结果，它只对结果进行确认 
	- L2扩容的核心要义就是以太坊不需要承担交易的所有工作量
	- 参与rollup协议的人，就是eth的验证者， 需要32个质押。
	- 一诚则成： 只要有一个诚实的验证者，那么整个链的正确运行就会有绝对的保证
4. 挑战合约： 仲裁用的

### 2024.12.29

#### rollup 确认逻辑 

![image](https://github.com/user-attachments/assets/cb2d33fe-5041-421f-b115-c4afd724b2af)

- 区块100已被确认。
- 区块101宣称自己是区块100的正确子区块，但101被拒绝了（因为打了叉）。
- 区块102最终被确认为区块100的正确子区块。
- 区块103也确认了，现在是最新确认区块。
- 区块104是103的子区块，105是104的子区块。由于104是错误的，105自然也会被拒绝，因为它的父区块就是错的。
- 区块106待决。它宣称自己是区块103的子区块，但协议尚未决定是确认还是拒绝它。这是首个待决区块。
- 区块107和108延续自区块106，它们也是待决状态。如果106被拒绝，它们也会被拒绝。
- 区块109不认同区块106，因为它们的父区块相同。它们中至少会有一个被拒绝，但协议尚未解决。
- 区块110跟随109。待决状态。如果109被拒绝，110也会。
- 区块111跟随104。111最终肯定会被拒绝因为其父区块已经被拒绝，但目前111还是待决状态，因为协议是按顺序处理区块的，所以要先处理106到110。在110解决后，111会被立即拒绝。

### 2024.12.30


### 2024.12.31






<!-- Content_END -->
