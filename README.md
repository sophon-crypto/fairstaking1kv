# fairstaking1kv

项目名称： Non-profit DElegated Staking Tool (NDeST) 
简称： NDeST

## 一，项目背景：

### 1.1 去中心化的问题
长期来看，随着ksm/dot价值的越来越大，机构特别是交易所或者一些专门的节点运营机构可能占据越来越重要重要的位置，他们可能会持有越来越多的节点，而机构持有节点过多会非常影响影响ksm/dot网络的去中心化程度，因此提高个人用户持有节点的比例是保持系统去中心化的关键手段。机构持有过多节点不仅仅会造成去中心化的问题，而且会使得系统总体参与程度下降，比如投票，比如参与提案，比如新版本的更新速度等等，以及因为一些图发情况导致的节点大面积下线，都会对系统发展不利。1kv计划（web3特地发起了1kv计划，即通过web3的支持，部分个人用户只需要提供少量质押，即可以拥有一个节点。）是降低系统中心化程度，保持系统足够分散性和足够参与者的关键项目

### 1.2 1kv中选举成功率较低，需要web3提供更多的质押
目前1kv共约167个valid node（https://kusama.yaohsin.net/api/validators） ，只有84个节点被成功选举成为验证人节点，选举成功率约为50%。虽然1kv计划尝试通过各种方法使得尽可能提高成功率，让更多的参与者能够分享收益，但是如果让167个节点都成为选举人节点，每个节点至少需要5000个抵押，如果所有的节点都来自web3，那么至少需要83万5000ksm。而且随着参与者越来越多，需要web3提供的质押越辣越多，如果仅仅依靠web3 foundation可能不足与提供足够多的staking支持大多数节点选举成功。

### 1.3 个人提名者参与1kv质押是解决问题的根本办法
个人提名者参与1kv质押可以解决一部分质押资金来源的问题，大量的个人提名者参与1kv，也可以极大增加1kv计划的资金实力；个人提名者参与1kv计划，还可以增加1kv计划中节点获取稳定收益的能力，因为个人提名者一般不会频繁质押以及撤销质押，大部分个人用户还是习惯于质押在某一个确定的节点上。

## 二，项目目标
通过polkadot App提供个人提名者对于1kv计划节点的直接质押（一键质押）提升1kv参与者得选举成功率，从而增加1kv计划中质押资金得来源（目前1kv质押资金主要来源于web3），提升系统去中心化程度，增加系统活跃度。

## 三，项目内容
### 3.1 过程
#### 3.1.1 个人提名者质押入口
在polkadot app中，对于个人提名者而言，提供更多1kv操作入口
```
Bond more funds
Unbond funds
Withdraw unbound funds
_______________________
Change Controller account
Change Reward destination
_________________________

Staking in Web3 1KV (新增）

```

#### 3.1.2 选择1kv质押策略
```
<img>stash acount                 xxxxxxxxxxxxxxxxxxxxxxxxxxxx
_______________________________________________________________
<img>controller acount            xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
_______________________________________________________________
1KV staking strategy (selection)
_______________________________________________________________
1kv nodes                     |    nominated accounts
<img>xxxxxx                   |    <img>xxxxxx    
<img>xxxxxx                   |    <img>xxxxxx    
________________________________________________________________
```

#### 3.1.3 输入密码以及确认质押
```
Authorize transaction
Sending transaction staking.nominate(targets)
Declare the desire to nominate targets for the origin controller. 
Fees of 3.0166 milli KSM will be applied to the submission
<img>sending from my account
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
unlock account with password
input password
```
### 3.2 算法
#### 3.2.1 当前收益最高

#### 3.2.2 质押时间最长




## 四，可扩展性（Scalability)
### 4.1 ksm支持

### 4.2 dot支持

## 五，未来的工作（Future Work）

## 六，希望的支持 

### 6.1 功能支持
希望能在polkadot app中提供fairstaking1kv入口。
### 6.2 国库支持
500ksm
