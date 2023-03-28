# bnbcamp230317
for bnbcamp test
1. 部署ERC-20合约
HYPToken 合约代码：HYPToken.sol

部署transaction hash： 0x2fca360650d793727bb24281facfd0ef825377749872052e29527defab4e5fd5

部署地址：0xAF83310Cf4D57887c29be00D7EEA338d87Ce0643

调用 HYP Token 的 transfer 方法，转账1000个 HYP token：
0x5de6b531eccb1ea74558c7e5c5ae1ad83b2b89dc13856c7e06281bad86ccd242

2. 完成流动性挖矿合约的部署
合约部署
ALP Token，该token作为奖励流动性挖矿奖励token，通过LPStaking合约mint新增的ALP token

合约代码：ALPToken.sol

部署transaction：0x5c395806a80b84e9476a2f3bc5da66ae4db3100134d0c9b89fdb29f5d105582f

部署地址：0xe9dfb1c80f4c8525f9a2264f89568b0aef2b79f3

流动性挖矿合约

合约代码：LPStaking.sol

部署transaction：0x40632b9b465b641a376cff412cd1af2069d03bc45d1223f4f47b14c9b21b1927

部署地址：0x6cb2f692f63312c42554c3f599d0e50435ae5b01

该合约包含了以下功能：
添加池子：每个池子包含一个 LP Token 和分配给该池子的 allocPoint（权重）。

设置池子：更改池子的 allocPoint。

存款：将 LP Token 存入池子，获得对应的代币奖励。存款时将会自动计算之前未领取的奖励并发送给用户。

提款：从池子中提取 LP Token，并领取对应的代币奖励。提款时将会自动计算之前未领取的奖励并发送给用户。

紧急提款：从池子中提取 LP Token，但不会领取奖励。这个功能应该只在必要时使用

相关Transaction
调用 BBB Token 合约的 Add Minter 方法添加 minter 地址 0x6cb2f692f63312c42554c3f599d0e50435ae5b01
0x6f750ef29c6cf5da9272e595dfab30fb0c01504b0be4da565774cf6042cc7470
调用 LPStaking 合约的 Add Pool 方法添加一个流动性挖矿的Pool，Pool 支持的质押 LP token 为 AAA Token (0x819b90dc1309cf956783213324480310794aea44)，并设置 Pool 的权重为 100
0xc9ae892d61effe4986f16858be13f43799c191b601f422cc6c03a11d894bdc49
调用 HYP Token 的 Approve 方法，授权 LPStaking 合约使用 100个 AAA token：
0x832c4c191c12f4a5da959772b737b6aef54c3f64df92c74659dff7c0764f7777
调用 LPStaking 合约的 Deposit 方法，往刚刚添加的 Pool 质押100个 AAA token：
0x28f4a80cbc4bcd237a74a98d457a355af0457c8a106005bac8c25eb25ab0a309
调用 LPStaking 合约的 Deposit 方法，并传入参数质押 0个 AAA token，提取流动性挖矿奖励，获得31个 BBB token：
0xfbb01b4e281b91bfcd4faa92aa3ff46f9903d21399861ad83f43592c52e665fa
