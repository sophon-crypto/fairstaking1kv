# 1KV-program More Stakers Tools (1KV-MST)

## 1. Objective

### 1.1 1KV plan could enahance the decetralization of kusama/polkadot network

As the value of Kusama/Polkadot increases, only a few people are able to afford the cost of maintaining their own validators without the help of big players. Today, an operator who wants to manage a Polkadot validator needs to own or attract more than 10M USD, which prevents individual operators from joining the community. The high cost of KSM/DOT will not only hurt decentralization but also reduce the overall activation of the system, such as voting, participating in proposals, speed of updating to the new version, etc. 

Therefore, it is essential to increase the proportion of validators held by individual users. The quantity of individual validators is a crucial point to increase  decentralization in the network. The 1kV plan thus was launched by Web3 foundation to help individual players holding validators. It is a pivotal project to disperse the power of validators held by capitals and keep the system decentralized.


### 1.2 1KV could gurantee the high-quality of validators

Bascailly all the Substrated-based blockchain have the staking business and staking is the fundamentail economic model for all the chains.  All the stakers (nominator in kusama/polkadot） needs to choose suitable node (validator in the kusama/polkadot) to finish the operation， otherwise， stakers needs to build node by themselves. However, we think 1KV plan has done a lot of work for the suitable validator because:

- High self-stake: 1kVP validators commit their 
funds to the system, and they have to pay attention to operations to avoid being slashed.

- Low malicious operations chance: Web3 Foundation keeps monitoring each validator's status. A malicious validator could soon be kicked out of the Program. Nominators thus take a lower risk of being cheated or slashed.

- Stability: the official monitors the state of the verification node in 1kVP at any time ensures the stable operation of the node and eliminates the unstable nodes.

### 1.3 high-quality validator could help staking service provider to reduce cost

We already know the staking service is one of the most fundamental for the POS-based blockchain and becasue of unbonding period the unlocking liquidity of staked assets is the popular. But if the service provider tries to do all the things by themselves they need to build their own validator node and probably not all the validators can't be used fully up to 100%. For the staking service provider a decentralized, scalable, free-maintainable validator nodes would be better and they can use some of nodes to bond or unbond freely. 1KV nodes is the best choice for the kusama/polkadot staking servic provider.
 
### 1.4 StaFi project

StaFi is the first DeFi protocol unlocking liquidity of staked assets. Users can stake PoS tokens through StaFi and receive rTokens in return(like stake KSM, get rKSM.), which are available for trading, while still earning staking rewards. More info about StaFi, you can : visit www.stafi.io, follow Twitter:@Stafi_Protocol, join Telegram Chat: https://t.me/stafi_protocol.

StaFi will be the first staking-service-provider to work together with 1KV by 1KV-MST project. Users stake KSM/DOT through StaFi Staking Contract, it will be nominated to the validators on this group, in order to make the network more decentralized. Recently Stafi will provide 2 kinds of unlocking liquidity of staked assets ： rKSM and rDOT targeted for Kusama and Polkadot project. 

## 2. Project objectives
Staking service is very normal especially in the Substrate-based blockchain system and we would like to develop some common things to connect self-maintained validators sets and nominated-source from outside as show in this following Figure:

Web3 1kv programm could make entry rules of 1kv validators and provide the most of necessary nomination. Additioanlly other staking service provider (SSP) could provide others and all of them could support the election of all the verified vaidators in order to make the whole system more reliable. MST (More Staking Tool) should provide the APIs to help the staking service provider (SSP) to show validator raw information about commission-rate, faults times, slash or not, etc but WITHOUT any algorithms which will be handled by SSP themselves. 




![mst](https://user-images.githubusercontent.com/76861170/113494648-c3b56500-951c-11eb-8958-d2fbc1c254c2.png)

 1KV-MST can provide the dashboard to show the information about validators about norminator-soources types (from WEB3, from SSP or from others) and some other raw information about commision-rate. All the information would be organized from the nominator-side-view.

  The whole project will be split into 2 stages. In this stage we just implement the 1kv for kusama. After 1KV-MST can be online we will review the design and we should get the real feedback from Stafi project as Staking Service Provider.
  In the second stage We plan to start the 1kv-mst project for Polkadot when the 1kv-mst for kusama is done immediately and submit the 1KV-MST proposal of new design. 
 

## 3. Project Design

### 3.1 Interactive API
#### 3.1.1 function description
We provide RESTful API for users such as Stafi to make monitor validator status simple. We plan to

* Host the API service
* Provide interactive API document in form such as (https://Swagger.io)
* Provide SDK in Javascript and Rust.

JS is regarded as full-stack language and it is easily used for many prototype projects. Rust is the base-language for the substrate-based blockchain. So we choose these 2 languages to implement the SDK firstly.

#### 3.1.2 API description
    - get 1kvp active sets
    - get 1kvp inactive sets
    - get 1kvp commission rate
    - get 1kvp discoveredAt
    - get 1kvp contrller
    - get 1kvp slash
    - get 1kvp faults
    - get 1kvp fault reason
    - get 1kvp era points
    - get 1kvp all information
    - ...

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

### 4.1 Cloud environment preparation
Cloud environment is used in
- 1KV-MST dashboard development and deployment
- API-Doc depoyment
- domain name for 2 years (USD 300.00）

  1 Server (8vCPU + 16GiB + 500GiB SSD + 10Mbps) * 12 = USD 400 * 12 month  = USD 4800.00
  
  Funding allocation: USD 5100
  Time estimation: 1 week
 
 
### 4.2 API component
API component has 2 parts: API, API interactive document, API SDK, etc as following:

- API implementation 10 days (1 developer): USD 1500.00
- Interactive API document 5 days (1 developer): USD 750.00
- SDK of JS version 5 days (1 developer): 750.00  
- SDK of Rust version 5 days (1 developer): 750.00  

Funding allocation: USD 3750.00
Time estimation: 1 months

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

Funding allocation: USD 6000.00 
Time estimation: 1.5 months

### 4.4 operation and support for future 1kv-mst: 12 months

We plan to operate our 1kv dashboard site thereafter, the operation man-cost could be calculated as $300 * 9 month = 2700 USD a year (USD 300 per month).

Total allocation: USD 2700
 
#### 4.5 Time estimation and budget

The project will be done in the 3 months after the proposal is approved by coucil but the API component will be done in the first month because API component will be used by StaFi project. 

According to the KSM Rate: 1KSM = USD 423.00 (13th, 4, 2021) the funding request will be  USD 17550 / (1ksm/USD 423.00) = 41.48 KSM.


### 5 Future work

We propose this project to bridge the 1KV project and the 3rd-party staking servicing provider. We hope we can get more insight about how to make the 1kv project more effiecient after the project is online. 

Here are some examples we think we can do in the future,

* keep optimizing the API interface and API specification around the staking service for 3rd-party
* keep optimizing the 1kv-mst dashabord in side of nominator view
* Go on the project for Pokadot (dot) 

## 6、 Team and advantage

### 6.1 team

##### Project Manager and Developer: sophon (Riot Id)

Sophon has a Ph.D. degree of applied mathematics and Master of computer engineering. He has long-term IT-development and IT-management experience for more than 10 years. He is a serial entrepreneur, and he has experience with Substrate-based blockchain technology. He is also a personal Kusama validator operator.

##### Designer and Developer: yaohsin (Riot Id)：

Yaohsin has a Ph.D. degree in computer science with a focus on information security. He is a big believer in blockchain and is a co-founder of a blockchain-based solar technology company. Currently, he is a personal Kusama validator operator.

##### Designer and Developer: tanis_ 37 (Riot Id)：

tanis_ 37 has a Master degree of computer science. He is a proficient software developer on industrial network management systems. He is also a personal Kusama validator operator.

### 6.2 advantages

#### 6.2.1 be familiar with 1kVP plan

We are all involved in the 1kVP project and have a deep understanding of the 1kV problem. We hope to help solve some 1kV problems through this project.

#### 6.2.2 some completed works

We have finished the data analysis work of 1kV node, and it keeps working usually. For details, please refer to https://kusama.yaohsin.net/api/validDetail

