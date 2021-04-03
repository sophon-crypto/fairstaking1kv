# More Stakers Tools (MST)

## 1. Objective

### 1.1 1KV plan could enahance the ecetralization of kusama/polkadot network

As the value of Kusama/Polkadot increases, only a few people are able to afford the cost of maintaining their own validators without the help of big players. Today, an operator who wants to manage a Polkadot validator needs to own or attract more than 10M USD, which prevents individual operators from joining the community. The high cost of KSM/DOT will not only hurt decentralization but also reduce the overall activation of the system, such as voting, participating in proposals, speed of updating to the new version, etc.

Therefore, it is essential to increase the proportion of validators held by individual users. The quantity of individual validators is a crucial point to increase  decentralization in the network. The 1kV plan thus was launched by Web3 foundation to help individual players holding validators. It is a pivotal project to disperse the power of validators held by capitals and keep the system decentralized.

Until today, there are about 172 valid nodes in 1kVP（ https://kusama.yaohsin.net/api/validators， recorded on 24th, Jan 2021). Only 99 of them were successfully elected as validators and the elected rate was about 57.5%. Although the 1kVP plan is pushing to improve the success elected-rate as much as possible through various methods, many nodes have to wait for a long time before being nominated. However, it is unreasonable to ask Web3 Foundation to provide enough stake to keep the 1kVP validators nominated at all times.

Let us have a simple evaluation for 1kVP on Kusama: if all the 172 nodes in the 1kVP are active, each node needs at least 5000 KSM (including at least 50 KSM self-staked) Web3 Foundation needs to stake at least 172 * (5000 - 50) = 851,400 KSM, which equals to about 80M USD now. Moreover, as the price goes up, people probably are more willing to join the program. The 1kVP participants cannot rely on nominations from Web3 foundation in the long term.

### 1.2 1KV could gurantee the high-quality of validators

Bascailly all the Substrated-based blockchain have the staking business and staking is the fundamentail economic model for all the chains.  All the stakers (nominator in kusama/polkadot） needs to choose suitable node (validator in the kusama/polkadot) to finish the operation， otherwise， stakers needs to build node by themselves. However, we think 1KV plan has done a lot of work for the suitable validator because:

1. High self-stake: 1kVP validators commit their funds to the system, and they have to pay attention to operations to avoid being slashed.

2. Low malicious operations chance: Web3 Foundation keeps monitoring each validator's status. A malicious validator could soon be kicked out of the Program. Nominators thus take a lower risk of being cheated or slashed.

3. Stability: the official monitors the state of the verification node in 1kVP at any time ensures the stable operation of the node and eliminates the unstable nodes.

### 1.3 staking-businsess could help 1kv to support more validators. 



### 1.4 StaFi project
  somethign more about stafi
  
  StaFi will be the first staking-service-provider to work together with 1KV by MST project. 

## 2. Project objectives
Staking service is very normal especially in the Substrate-based blockchain system and we would like to develop some common things to connect self-maintained validators sets and nominated-source from outside as show in this following Figure:

MST (More Staking Tool) should provide the APIs to show all the validator information including all the params such as:offlineAccumulated, Rank, Fault times, Inclusion, etc. All the raw parameters could be dumped and published as API. Then the staking-servcie-provider (SSP) could develop their own stategy to choose more suitable one.

![图片](https://user-images.githubusercontent.com/76861170/112962256-c3ae1180-9178-11eb-9462-b9047a4f237c.png)

 MST (More Staking Tool) also should provide the dashboard to show the nominator-interesting params such as return rate, on-line time and who would like to give normianton for these validators.

## 3. Project Design

### 3.1 1kv nominator API

#### 3.1.1. get 1kvp active sets

GET /api/1kv-active-sets

#### 3.1.2. get 1kvp inactive sets

GET /api/1kv-inactive-sets

#### 3.1.3 get commission rate of 1kvp
GET /api/1kvp-commission-rate

#### 3.1.4 get discoveredAt
GET /api/1kvp-discoveredAt

#### 3.1.5 get contrller
GET /api/1kvp-controller

#### 3.1.6 get slash
GET /api/1kvp-slash

#### 3.1.7 get faults
GET /api/1kvp-faults

#### 3.1.8 get era points
GET /api/1kvp-average-points

#### 3.1.9 get all information of 1kvp
GET /api/1kvp-full

#### 3.1.10 more
to be continued


### 3.3 1kv-edst dashboard


The aim of 1kv-dest is to provide non-web3 nomination for the 1kv VP as much as possible based on the lots of users of polkadot apps, and also we hope 1kv-edst could provide senior invidual nominator more information about 1KV VP. Actually, from our experience as 1KV VP we think the 1KV leaderboard is very good for 1KV VP operators to check the status about the validator node about : the lastest version, Invalidity Reasons, etc. However, 1KV-EDST dashboard is designed just for the individual nominator to check which node is better. So 1KV-EDST can provide the interactive interface for the nominator to show the validator with different rules and all the validators will be sorted by this factor:  
- non-web3 nomination  calculate the taotal of non-web3 nomination for 1KV VP node
this is very important attributes and in some senses the meaning of 1KV Edst is to show all of us nomination from non-web3 is very important. And more nomination from non-web3, web3 could save token to support more 1KV VP.  Additionally, for the nominator we will provide some other attributes but the non-web3 nomination is the basis of this project.



## 4. Time & Cost

- Human resources involved: part-time
- Cost of man per day = 1USD 150.00
- cost of man per week = USD 750.00
- we hope to implement the project and make it run as soon as possible AND THEN we could optimize more.

### stage 1: KSM 1KV EDST (1 months)
 
### stage 1.1 Development and operation environent preparation
- 1KV-EDST dashboard development and deployment for 11 month
  1 Server (8vCPU + 16GiB + 500GiB SSD + 10Mbps) * 12 = USD 400 * 12 month  = USD 4800.00
 
### stage 1.2 1KVP API specification and sdk
 
In this stage, we will provide the following items.

1. 1KVP API （nodejs)  10 days (2 developer): USD 3000.00
2. 1KVP API (python3)  10 days (2 developer): USD 3000.00

Total allocation: USD 6000.00

### stage 1.3  1kv-edst dashboard

1. 1KV-EDST dashboard UI design - 1 week (1 UI Dev & 1 Developer): USD 1500.00
2. 1KV-EDST dashboard development for *nominators* to show the status of 1kVP validators - 3 weeks (2 developer): USD 4500.00
* 1KV-EDST dashboard is not just a validator view but an interactive site for *nominators* to search suitable validator regarding different sorting algorithim including:
        highest reward currently  
        highest/lowest inclusion 
        highest/lowest staking
  
* display totally historical nomination from non-web3 support and web3 support to optimize this project gradually.
* display non-web3 present nominatons now and history nomination trending on each 1KVP node.
* display validator ranking based on proposed algorithms
* display historical trending of validators status of commission, nominator counts and stake size


Deliverable: A validator dashboard

Total allocation: USD 6000.00 

### Stage 1.3 operation and support for future 1kv-edst: 12 months

We plan to operate our 1kv dashboard site thereafter, the operation man-cost could be calculated as $1000 a year.  

Total allocation: USD 1000
 
#### Budget

KSM Rate: USD 500.00 
Allocation request: USD 17800.00 / (1ksm/USD 500.00) = 35.6 KSM

## 8、 Team and advantage

### 8.1 team

##### Project Manager and Developer: sophon (Riot Id)

Sophon has a Ph.D. degree of applied mathematics and Master of computer engineering. He has long-term IT-development and IT-management experience for more than 10 years. He is a serial entrepreneur, and he has experience with Substrate-based blockchain technology. He is also a personal Kusama validator operator.

##### Designer and Developer: yaohsin (Riot Id)：

Yaohsin has a Ph.D. degree in computer science with a focus on information security. He is a big believer in blockchain and is a co-founder of a blockchain-based solar technology company. Currently, he is a personal Kusama validator operator.

##### Designer and Developer: tanis_ 37 (Riot Id)：

tanis_ 37 has a Master degree of computer science. He is a proficient software developer on industrial network management systems. He is also a personal Kusama validator operator.

### 8.2 advantages

#### 8.2.1 be familiar with 1kVP plan

We are all involved in the 1kVP project and have a deep understanding of the 1kV problem. We hope to help solve some 1kV problems through this project.

#### 8.2.2 some completed works

We have finished the data analysis work of 1kV node, and it keeps working usually. For details, please refer to https://kusama.yaohsin.net/api/validDetail

### 9 Future

We propose this project to bridge the Polkadot App and the 1kv project. We hope we can get more insight about how to make the 1kv project more effiecient after our works go online. 

Here are some examples we think we can do in the future,

* keep improving the algorithm and dashabord to fit *nominator* and our needs more
* Support Polkadot 1kv project

We are going to evaluate these ideas after the first stage is done.
