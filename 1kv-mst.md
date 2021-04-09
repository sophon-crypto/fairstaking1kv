# 1KV-program More Stakers Tools (1KV-MST)

## 1. Objective

### 1.1 1KV plan could enahance the ecetralization of kusama/polkadot network

As the value of Kusama/Polkadot increases, only a few people are able to afford the cost of maintaining their own validators without the help of big players. Today, an operator who wants to manage a Polkadot validator needs to own or attract more than 10M USD, which prevents individual operators from joining the community. The high cost of KSM/DOT will not only hurt decentralization but also reduce the overall activation of the system, such as voting, participating in proposals, speed of updating to the new version, etc. 

Therefore, it is essential to increase the proportion of validators held by individual users. The quantity of individual validators is a crucial point to increase  decentralization in the network. The 1kV plan thus was launched by Web3 foundation to help individual players holding validators. It is a pivotal project to disperse the power of validators held by capitals and keep the system decentralized.


### 1.2 1KV could gurantee the high-quality of validators

Bascailly all the Substrated-based blockchain have the staking business and staking is the fundamentail economic model for all the chains.  All the stakers (nominator in kusama/polkadot） needs to choose suitable node (validator in the kusama/polkadot) to finish the operation， otherwise， stakers needs to build node by themselves. However, we think 1KV plan has done a lot of work for the suitable validator because:

1. High self-stake: 1kVP validators commit their 
funds to the system, and they have to pay attention to operations to avoid being slashed.

2. Low malicious operations chance: Web3 Foundation keeps monitoring each validator's status. A malicious validator could soon be kicked out of the Program. Nominators thus take a lower risk of being cheated or slashed.

3. Stability: the official monitors the state of the verification node in 1kVP at any time ensures the stable operation of the node and eliminates the unstable nodes.

### 1.3 high-quality validator could help staking service provider to reduce cost

We already know the staking service is one of the most fundamental for the POS-based blockchain and becasue of unbonding period the unlocking liquidity of staked assets is the popular. But if the service provider tries to do all the things by themselves they need to build their own validator node and probably not all the validators can't be used fully up to 100%. For the staking service provider a decentralized, scalable, free-maintainable validator nodes would be better and they can use some of nodes to bond or unbond freely. 1KV nodes is the best choice for the kusama/polkadot staking servic provider.
 
### 1.4 StaFi project

StaFi is the first DeFi protocol unlocking liquidity of staked assets. Users can stake PoS tokens through StaFi and receive rTokens in return, which are available for trading, while still earning staking rewards. FIS is the native token on StaFi Chain. FIS is required to provide security to the network by staking, pay for transaction fees on the StaFi chain, and mint & redeem rTokens. If trying to understand more, you can : visit www.stafi.io, follow Twitter:@Stafi_Protocol, join Telegram Chat: https://t.me/stafi_protocol.

StaFi will be the first staking-service-provider to work together with 1KV by 1KV-MST project. 

## 2. Project objectives
Staking service is very normal especially in the Substrate-based blockchain system and we would like to develop some common things to connect self-maintained validators sets and nominated-source from outside as show in this following Figure:

Web3 1kv programm could make entry rules of 1kv validators and provide the most of necessary nomination. Additioanlly other staking service provider (SSP) could provide others and all of them could support the election of all the verified vaidators in order to make the whole system more reliable. MST (More Staking Tool) should provide the APIs to help the staking service provider (SSP) to show validator raw information about commission-rate, faults times, slash or not, etc but WITHOUT any algorithms which will be handled by SSP themselves. 




![mst](https://user-images.githubusercontent.com/76861170/113494648-c3b56500-951c-11eb-8958-d2fbc1c254c2.png)

 1KV-MST can provide the dashboard to show the information about validators about norminator-soources types (from WEB3, from SSP or from others) and some other raw information about commision-rate. All the information would be organized from the nominator-side-view.

## 3. Project Design

### 3.1 Interactive API document

We provide RESTful API for users such as Stafi to make monitor validator status simple. We plan to

* Host the API service
* Provide interactive API document in form such as (https://Swagger.io)
* Provide SDK in Javascript and Python

And the API sets will include :
* get 1kvp active sets
GET /api/1kv-active-sets
* get 1kvp inactive sets
GET /api/1kv-inactive-sets
* get commission rate of 1kvp
GET /api/1kvp-commission-rate
* get discoveredAt
GET /api/1kvp-discoveredAt
* get contrller
GET /api/1kvp-controller
* get slash
GET /api/1kvp-slash
* get faults
GET /api/1kvp-faults
* get fault reason
GET /api/1kvp-fault-reason
*  get era points
GET /api/1kvp-average-points
* get all information of 1kvp
GET /api/1kvp-full

### 3.2 1kv-mst dashboard

#### 3.2.1 1kv-mst dashboard can provide the active validators original information
     - commission-rate
     - discoveredAt
     - controller
     - stash
     - rward
     - faults
     - average-era-points
     - recent-era-points
     - ...

#### 3.2.2 active validators could be sorted by many fields:
     - by avarage era point
     - by recent era point （in the last 24 hours)
     - by active/inactive nominated amount
     - ...

### 3.3 other consideration
   Probably sometimes 1kv-mst dashboard is thought to be similar as 1kv-leadership-dashboard. Indeed they are different display model of the same information sets but more importantly these information are organized from different side-view. We think 1kv-leadership-dashboard is mainly for the validator themselves and they could find the enough information to help validator operator to locate the questionf of validator node such as: Don't update to the newest version, node downtime caused by unknow reason, etc.
   1KV-MST dashboard could focus more on the statistical information especially more useful for nominator whatever the Staking Service Provider or individual user. We are sure the 1kv-mst dashboard will be more specic and characteristic when more and more Staking Service Providers join 1KV programme.


## 4. Time & Cost

- Human resources involved: part-time
- Cost of man per day = 1USD 150.00
- cost of man per week = USD 750.00
- we hope to implement the project and make it run as soon as possible AND THEN we could optimize more.

### 4.1 Cloud environment
Cloud environment is used in
- 1KV-MST dashboard development and deployment
- API-Doc depoyment

  1 Server (8vCPU + 16GiB + 500GiB SSD + 10Mbps) * 12 = USD 400 * 12 month  = USD 4800.00
 
### 4.2 API Tools SDK
API SDK includes: 
- online restful model 10 days (1 developer): USD 1500.00
- offline native model (java version) 10 days (1 developer): 1500.00  

Total allocation: USD 3000.00

### 4.3 1kv-mst dashboard

1. 1kv-MST dashboard UI design - 1 week (1 UI Dev & 1 Developer): USD 1500.00
2. 1KV-MST dashboard development for *nominators* to show the status of 1kVP validators - 3 weeks (2 developer): USD 4500.00
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

### 4.4 operation and support for future 1kv-mst: 12 months

We plan to operate our 1kv dashboard site thereafter, the operation man-cost could be calculated as $1000 a year.  

Total allocation: USD 1000
 
#### Budget

KSM Rate: USD 500.00 
Allocation request: USD 15800.00 / (1ksm/USD 300.00) = 49.3 KSM

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
