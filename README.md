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
### 2.1 對於個人提名者的吸引力
由於1kv中的驗證節點受到官方的規範與監管，至少可確保下列特性，避免加入惡意節點，大幅降低個人提名者所承受的風險。
1. 利益一致性：self-stake是選擇驗證節點的一個重要指標，只有將節點與提名人的利益綑綁在一起，才能保證節點會盡心盡力維運，避免被系統slash。然而目前大部分節點的self-stake都偏低(給數據)，若提名人不了解細節，則有可能承受極大風險。
2. 避免惡意操作：提名人應隨時注意佣金的比例，因為可能存在節點惡意提高佣金比例，使提名者遭受莫名的損失而不自知。
3. 穩定性：官方隨時監控1kv中驗證節點的狀態，以確保節點穩定運作，並剔除不穩定的節點。
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
此算法的目的是帮助用户根据1kv节点中选择出当前质押会报最高的个节点，其概念为鼓励质押这将资金投入
1. Active set中回报最高的节点
2. 总质押数适中，6000质押好于10000质押

但是因为web3 1kv的质押策略是round robin，所以现在收益最高不一定是永远收益最高
#### 3.2.2 入选率最高/在线时间最长节点
此算法的目的是帮助用户根据1kv节点中选择出当前入选率/在线时间最长最高节点，其概念为鼓励质押这将资金投入
1. Active set中入选率最高节点
2. 最长在线时间

但是因为web3 1kv的质押策略是round robin，所以现在最长在线时间是一个较为稳妥指标

#### 3.2.3 鼓勵質押數量較低的節點

此算法的目的為讓小的/新的驗證人較容易被提名。其概念為鼓勵質押者將其資金投入
1. 較少被提名者 (active set選中率低)
2. 總質押數低者
3. ...?

此類驗證人因很少被提名 難以在polkadot app中獲得關注 自然難以吸引一般提名人的提名 導致驗證人從1kv計畫中獲得的收益低 若能在app中有一個明顯的入口 吸引提名人提名此類節點 將能夠鼓勵質押數低的節點繼續留在計畫中

此算法選擇x個高的驗證人(容易被提名的節點)(算法待補)和y個低的驗證人(難以被提名的節點)(算法待補)提名 
使用高低配的原因是如果提名者將其資金投入上述validators 就機率來說 他較難得到收益 因此我們搭配一個(或多個)容易被選中的節點確保此算法有足夠的吸引力讓質押者選擇 

## 四，可扩展性（Scalability)
### 4.1 初期支持ksm&dot
首先支持ksm系统，能够允许ksm nominators质押给1kv节点。后期，能够支持dot nominators质押给1kv节点。

### 4.1 其他
应该说，任何一个波卡系系统可能都会有类似1kv这样得计划，应该是共性，而非个性。

## 五，时间计划(Time Plan)
### stage 1: 2 months
完成ksm支持
### stage 2：2 months
完成dot支持

## 六，未来的计划（Future Work）
### 6.1 项目运维移交给web3 1kv team
如果这个项目进展顺利，并且功能已经稳定完备，将会移交给web3 1kv team运营


完成fairstaking1kv後 

## 七，希望的支持 

### 7.1 polkdaot app支持
希望能在polkadot app中提供fairstaking1kv入口。
### 7.3 1kv支持
希望能和1kv team合作，更好发会这个特性
### 7.2 国库支持
200ksm

## 八，团队和优势
### 8.1 团队

#####  bodysophon (Riot Id)
         bodysophon has an doctor deggree of applied mathematics and Master of computer engineering ksm. He has long-term IT-development and IT-management expierence for more than 10 years. He has experice of Substrate-based blockchain technology and he is also personal Kusama validator operator.
##### yaohsin (Riot Id)：
         yaohsin has an doctor deggree of applied mathematics and Master of computer engineering ksm. He has long-term IT-development and IT-management expierence for more than 10 years. He has experice of Substrate-based blockchain technology and he is also personal Kusama validator operator.
##### tanis_37 (Riot Id)：
         tanis_37 has an doctor deggree of applied mathematics and Master of computer engineering ksm. He has long-term IT-development and IT-management expierence for more than 10 years. He has experice of Substrate-based blockchain technology and he is also personal Kusama validator operator.


### 8.2 优势
我们参与了1kv计划，对于1kv参与比较深，对于1kv的问题也认识较为深刻，我们希望能通过这个项目解决所有1kv的问题。

