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
