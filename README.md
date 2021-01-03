# fairstaking1kv

项目名称： Non-Profit Delegated Staking Tool (NDeST) 
简称： NDeST

## 现状：
### 1kv的问题
目前1kv共约158个valid node（ https://kusama.w3f.community/invalid） ，质押比例仅为33%左右（），也就是说，大约有70%的节点实际无法获取到有效的收益去支撑节点的运行。但是我们也有理由猜测，web3应该无法提供足够的staking让所有节点都进入active set，因为目前ksm最小的staking必须到5000以上才能成功入选。5000*158大约总公需要79万，这个数字对于web3来说，有些太庞大了。因为，我们认为需要引入新的机制来解决1kv中大多数节点质押不足的问题。
### 去中心化的问题
长期来看，随着ksm/dot价值的越来越大，机构质押可能占据一个非常非常重要的位置，而机构质押过多会非常影响影响ksm/dot网络的去中心化程度，因此提高freeusers对于散户的直接质押将是增加系统稳定性的核心。

## 目标

### 短期目标

解决目前1kv中大部分节点难以获取web3的直接支持，从而不能进入1KV Active Set的问题。
### 长期目标
发展基于kusama的Non-Profit Defi,增加free users对于free validator的直接质押比例，提高系统的去中心化程度，应该是这个系统的核心目标

## 和Defi的关系
### Non-Profit Defi

我们可以考虑创建一个新名词Non-profit Defi，传统的Defi需要发行自己的代币或者需要直接进行资产的转移然后进行相关的金融活动，Non-Profit Defi也是一种Defi，但是不以进行资产的转移为目标，而是借助某种生态体系（ksm/dot）创建一种金融工具，系统本身不盈利。在本项目中，Non-Profit Defi本质上一种委托质押工具，其中没有利差的存在。当然，不排除，未来，本项目可能会向Defi演进，这可能是另外一个项目。

## 相对Defi的优势

### 解决方案
我们创建Defi，接受来自任何ksm用户的自动委托，通过委托向1kv中的inactive set提供一键质押功能（随机选择任意4个inactive set进行质押），在功能上该质押等同于用户直接选择节点质押，所以在任意时刻用户均可以撤回质押或者再次选择手动质押。

## 意义
通过Defi，解决1kv中流动性不足的问题，通过吸纳自有用户的为1kv增加流动性，提高1kv用户的质押比例。

## 希望的支持 

### 功能支持
希望能在polkadot app中提供fairstaking1kv入口。
### 国库支持
500ksm
