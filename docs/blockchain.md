# Notes on BlockChain

## 哈希函数

要达到密码安全，需要三个附加特性：

* 碰撞阻力
* 隐秘性
* 谜题友好

### 碰撞阻力

定义：无法找到 x 和 y，x != y，而 H(x) = H(y)

* 不表示不存在碰撞
* 使得可以让哈希值作为信息摘要

### 安全哈希算法
Secure Hash Algorithm 256，SHA-256

* MD(Merkle-Damgard) 变换

## 哈希指针

### 区块链

哈希指针构成的链表。每个区块不仅能告诉我们上一个区块的值在哪，还包含了改值的摘要，能验证那个值是否发生了改变

链表头部的哈希指针被称为**创世区块**(genesis block)

## 去中心化

地址：公钥的哈希值

* Fischer-Lynch-Paterson: Impossibility of distributed consensus with one faulty process - 在一个多进程异步系统中，只要有一个进程不可靠，就不存在一个协议，能保证有限时间内所有进程达成一致

## 运行机制

## 交易

比特币交易的过程其实就是不停地创造区块的过程

* 元数据：交易规模、输入数量、输出数量，交易的哈希值，锁定时间(lock\_time)
* 一系列输入
* 一系列输出

每个输出都要和一个特定的公钥（地址）对应

UTXO: Unspent TX(Transaction) Output

## 比特币脚本

交易的输入包括了脚本（而不是签名）

* 输出脚本（scriptPubKey）: 指定公钥
* 输入脚本（scriptSig）: 指定对应公钥的签名

堆栈式脚本: 每个指令只执行一次，线性，无法循环执行. 不是图灵完备的: 不能随意执行强大的函数

256 个指令，每个指令一个字节: 15 个不可用，75 个被保留

### P2SH

支付给脚本的哈希值. P2SH 脚本只是对堆栈最顶层的数据进行哈希运算, 核验运算结果是否与给定的哈希一致。通过后，在执行一步特殊的核验：把堆栈最顶层的数据重新解读为一系列指令，将其作为脚本运行一次

* 让付款方的支付工作简单化
* 效率提升: 矿工的工作是跟踪那些还没有被消费掉的输出脚本。采用 P2SH 的输出脚本会变得很小，只不过是个哈希值。所有的复杂性都被放到输入脚本中了

## 修订协议

### 硬分叉

### 软分叉

## 冷存储

### 分层确定性钱包

冷存储制造无限制的地址数量，通过一个短暂的、一次性的交换，让热存储知晓所有的地址
