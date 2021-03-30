
# 1KV Enhanced-Decentralized Staking Tool (1KV-EDST)

## 1. Background
### 1.1 The problem of Decentralization
As the value of Kusama/Polkadot increases, only a few people are able to afford the cost of maintaining their own validators without the help of big players. Today, an operator who wants to manage a Polkadot validator needs to own or attract more than 10M USD, which prevents individual operators from joining the community. The high cost of KSM/DOT will not only hurt decentralization but also reduce the overall activation of the system, such as voting, participating in proposals, speed of updating to the new version, etc.

Therefore, it is essential to increase the proportion of validators held by individual users. The quantity of individual validators is a crucial point to increase  decentralization in the network. The 1kV plan thus was launched by Web3 foundation to help individual players holding validators. It is a pivotal project to disperse the power of validators held by capitals and keep the system decentralized.

### 1.2 The 1kv participants need support from not only web3 but also individual players
Until today, there are about 172 valid nodes in 1kVP（ https://kusama.yaohsin.net/api/validators， recorded on 24th, Jan 2021). Only 99 of them were successfully elected as validators and the elected rate was about 57.5%. Although the 1kVP plan is pushing to improve the success elected-rate as much as possible through various methods, many nodes have to wait for a long time before being nominated. However, it is unreasonable to ask Web3 Foundation to provide enough stake to keep the 1kVP validators nominated at all times.

Let us have a simple evaluation for 1kVP on Kusama: if all the 172 nodes in the 1kVP are active, each node needs at least 5000 KSM (including at least 50 KSM self-staked) Web3 Foundation needs to stake at least 172 * (5000 - 50) = 851,400 KSM, which equals to about 80M USD now. Moreover, as the price goes up, people probably are more willing to join the program. The 1kVP participants cannot rely on nominations from Web3 foundation in the long term.

### 1.3 Why nominators should stake their funds to validators from 1kv

Authenticated 1kVP validators are credible because:

1. High self-stake: 1kVP validators commit their funds to the system, and they have to pay attention to operations to avoid being slashed.

2. Low malicious operations chance: Web3 Foundation keeps monitoring each validator's status. A malicious validator could soon be kicked out of the Program. Nominators thus take a lower risk of being cheated or slashed.

3. Stability: the official monitors the state of the verification node in 1kVP at any time ensures the stable operation of the node and eliminates the unstable nodes.

### 1.4 We need to attract individual stakers to support 1kVP

Currently, lots of public partipants/nominators never heard of 1kVP. There are also no guidelines on the Polkadot JS Apps for nominators to choose 1kVP validators. As we need to attract enough Polkadot JS Apps users to nominate 1kVP participants, making the program visible on Apps is crucial. If there are enough nominators, 1kVP validators could reduce the focus on the Web3 Foundation stake regarding why their node is not selected as validator. Web3 Foundation can then move these stakes to other use or even support more validators.

### 1.5 Current status of 1kv nominating mechanism from our perspective

The 1kVP nominating system nominates its participants in rotation: If a validator is selected, it will be in the active set for 4 eras (one day) on Kusama, then it will be removed from the set and has to be queued for several days (3 to 5 days) until it is being selected again. The mechanism, though ostensibly fair, does not help validators in collecting support from individual nominators. From our observation, the most effective way to attract nominators is to create a validators ranking on the *Targets*, including an option to nominate 1kVP participants. The nomination within one day can reach more than 10000 KSM. However, after the nomination from 1kVP ends, and if the validator is not selected, the nomination from independent nominators is lost. After 3 to 5 days of not being selected, most nominations attracted by the active period of the validator rotate the nominations.

The goal of this proposal is to enhance the 1kVP nominating strategy, helping those validators who already accumulated some nominations to continue being selected in the active set by individual nominators.

## 2. Project objectives

We plan to develop a Single-step-nomination function on Polkadot JS Apps to attract individual nominators to stake in favout of 1kVP validators.

## 3. Project Design
### 3.1 Basic Functions
#### 3.1.1 Entry for personal nomination
In Polkadot JS Apps, we would like to add an option to allow nominators to stake on 1kVP validators.

```
Bond more funds
Unbond funds
Withdraw unbound funds
_______________________
Change Controller account
Change Reward destination
_________________________

Nominate 1kVP validators (New）

```

#### 3.1.2 nomination strategy 
```
<img>stash acount                 xxxxxxxxxxxxxxxxxxxxxxxxxxxx
_______________________________________________________________
<img>controller acount            xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
_______________________________________________________________
Nominate 1kVP validators (selection)
_______________________________________________________________
1kVP nodes                    |    nominated accounts
<img>xxxxxx                   |    <img>xxxxxx    
<img>xxxxxx                   |    <img>xxxxxx    
________________________________________________________________
```

#### 3.1.3 input password to conform nomination
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

### 3.2 algorithm

#### 3.2.1 the current reward is the highest

The purpose of this algorithm is to help users select the highest-revenue node in all 1kVP nodes. The algorithm encourages individual nominators to invest the capital to:

1. The node with the highest reward in active set.

2. The total-stake of node is moderate. The reward of 6000 stakes is better than 10000 stakes.


Because the strategy of 1kVP is round-robin to select the suitable node, the highest reward now is not necessarily the highest forever.

#### 3.2.2 node with the highest selection rate / longest online time

This algorithm aims to help users select the node with the highest current selection rate / the longest online time according to the 1kVP node. The concept of this algorithm is to encourage the pledge, which will put money into the network.

1. The node with the highest selection rate in the active set.

2. Maximum online time.


Because the strategy of 1kVP is round-robin, the longest online time is a more reliable indicator.


#### 3.2.3 encourage the nodes with low stake

The purpose of this algorithm is to help small/new validators to be nominated. The concept is to encourage nominators to backup validators which are:

1. Not frequently selected by 1kVP to validate.

2. Have a low total stake.

This verifier can hardly attract individual nominators because it is rarely seen on the Polkadot JS Apps: If there is an obvious entry in Apps to attract nominators to nominate this kind of nodes, the nodes with a low pledge number will be encouraged to stay in the project.

With this algorithm, x high validators (validators which are likely being nominated) are selected

(stake ranking) valid nodes are ranked according to the total number of pledge except Web3 nominators

2. Randomly select m nodes (for example, M = 2) from the top quarter nodes of the stack ranking as high verifiers


And Y low validators (validators which are rarely being nominated) to nominate the method

1. (active ranking) valid nodes are sorted according to the active set selection rate

2. Randomly select n nodes (e.g., n = 5) as the low verifier from the nodes after 1 / 4 of the stack ranking

3. Randomly select n nodes (e.g., n = 5) as the low verifier from the nodes after the active ranking

The reason for using high and low allocation is that if the nominator invests his capital in the above validators, it is more difficult for him to get income in terms of probability. Therefore, we match one (or more) easily selected nodes to ensure that this algorithm has enough attraction for the pledgor to choose



### 3.3 1kv-edst dashboard


The aim of 1kv-dest is to provide non-web3 nomination for the 1kv VP as much as possible based on the lots of users of polkadot apps, and also we hope 1kv-edst could provide senior invidual nominator more information about 1KV VP. Actually, from our experience as 1KV VP we think the 1KV leaderboard is very good for 1KV VP operators to check the status about the validator node about : the lastest version, Invalidity Reasons, etc. However, 1KV-EDST dashboard is designed just for the individual nominator to check which node is better. So 1KV-EDST can provide the interactive interface for the nominator to show the validator with different rules and all the validators will be sorted by this factor:  
- non-web3 nomination  calculate the taotal of non-web3 nomination for 1KV VP node
this is very important attributes and in some senses the meaning of 1KV Edst is to show all of us nomination from non-web3 is very important. And more nomination from non-web3, web3 could save token to support more 1KV VP.  Additionally, for the nominator we will provide some other attributes but the non-web3 nomination is the basis of this project.


### 3.4 key points

We hope to build a bridge between the 1kVP project and Polkadot JS Apps through this project and help the community when deciding on staking. The algorithm itself should note the important points in the early stage but focus on the mechanism and how to implement iteration development in the future.


## 4. Time & Cost

- Human resources involved: part-time
- Cost of man per day = 1USD 150.00
- cost of man per week = USD 750.00
- we hope to implement the project and make it run as soon as possible AND THEN we could optimize more.

### stage 1: KSM 1KV EDST (1 months)
 
### stage 1.1 Development and operation environent preparation
- development environment including native polkadot app for 1 month 
- 1KV-EDST dashboard development and deployment for 11 month
  1 Server (8vCPU + 16GiB + 500GiB SSD + 10Mbps) * 12 = USD 400 * 12 month  = USD 4800.00
 
### stage 1.2 1kv-edst front-side in the polkadot apps.
 
In this stage, we will provide the following items.

1. add an entry point for 1kVP nomination on Polkadot JS Apps - 3 days (1 developer): USD 450.00
2. add the 1KVP logo and filter function on Apps' staking page, targets page and waiting page -  4 days (1 developer): USD 600.00
3. provide the validator info-on-chain reader js class - 1 week (1 developer): USD 750.00
4. provide the simple abstract function to be compatible with differerent algorithms - 1 week ( 2 developers): USD 1500.00
        highest reward currently  
        highest/lowest inclusion 
        highest/lowest staking
Deliverable: Polkadot JA Apps pull request accepted (as patch)

In the polkadot app the 1kv-edst just gives some information to choose 1KV VP but doesn't have effect on the polkadot apps sorting algorithm.

Total allocation: USD 3300.00

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

KSM Rate: USD 220.00 
Allocation request: USD 15100.00 / (1ksm/USD 220.00) = 68.63 KSM

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
