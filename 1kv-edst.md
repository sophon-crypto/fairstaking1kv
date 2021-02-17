
# 1KV Enhanced-Decentralized Staking Tool (1KV-EDST)

## 1,Background
### 1.1 The problem of Decentralization
As the value of Kusama/Polkadot increases, only a few people are able to afford the cost of maintaining their own validators without the help of big players. Today, a person who wants to own a Polkadot validator needs to own or attract more than 10M USD, which prevents individual validator maintainers from joining the community. The high cost of KSM/DOT will not only hurt decentralization but also reduce the overall activation of the system, such as voting, participating in proposals, speed of updating to the new version, etc.

Therefore, it is essential to increase the proportion of validators held by individual users. The quantity of personal validators is the crucial point to increase the degree of system decentralization. The 1kV plan thus was launched by Web3 foundation to help individual players to hold validators. It is a pivotal project to disperse the power of validators held by capitals and keep the system decentralized.

### 1.2 The 1kv participants need support from not only web3 but also individual players
Till today, there are about 172 valid nodes in 1KV（ https://kusama.yaohsin.net/api/validators， recorded on 24th, Jan 2021). Only 99 of them were successfully elected as validators, and the elected rate was about 57.5%. Although the 1kV plan is pushing to improve the success elected-rate as much as possible through various methods, many nodes have to wait for a long time before being nominated. However, it is unreasonable to ask Web3 to provide enough stake to keep the 1kv validators nominated all the time. It is also unrealistic to ask web3 to guarantee all the 1KV nodes online all the time.

Let us have a simple evaluation for 1KV in Kusama: if all the 172 nodes in the 1KV are active, each node needs at least 5000 KSM, including at least 50 self-stake. Web3 needs to stake at least 172 * (5000 - 50) = 851,400 KSM, which equals to about 80M USD now. Moreover, as the price goes up, people probably are more willing to join the program. The 1KV participants cannot rely on the nomination from Web3 foundation in the long term.

### 1.3 Why nominators should stake their funds to validators from 1kv

Authenticated 1KV validators are credible because,

1. High self-stake. 1kv validators commit their funds to the system, and they have to pay attention to the operation to avoid being slashed.

2. Low malicious operation chance: Web3 keeps monitoring each validator's status. A malicious validator could soon be kicked out of the program. Nominators thus take a lower risk of being cheated or slashed.

3. Stability: the official monitors the state of the verification node in 1kV at any time to ensure the stable operation of the node and eliminate the unstable nodes.

### 1.4 We need to attract individual stakers from the most intuitive place

Currently, lots of public partipatents/nominators never hear of 1KV plan. There are also no clues on the Polkadot App for nominators to choose 1kv validators. As we need to attract enough Polkadot App users to nominate 1kv participants, making the program visible on the App is crucial. If there are enough nominators from public nominators, 1K validators could reduce the focus on the web3 about why their node is not selected as a normal validator. Web3 can then move these stakes to other uses or even support more validators.


## 2、 Project objectives

We plan to develop a Single-step-nomination function on the Polkadot App to attract individual nominators to put their stakes to the 1kv validators.

## 3, Project Desgin
### 3.1 Basic Function
#### 3.1.1 Entry for personal nomination
In Polkadot app, we would like to add an option to allow nominators to stake on 1kv validators.

```
Bond more funds
Unbond funds
Withdraw unbound funds
_______________________
Change Controller account
Change Reward destination
_________________________

Staking in Web3 1KV (New）

```

#### 3.1.2 nomation strategy 
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

The purpose of this algorithm is to help users select the highest-revenue node in all 1KV nodes. The algorithm is to encourage the individual nominator to invest the capital to:

1. The node with the highest reward in active set.

2. The total-stake of node is moderate. The reward of 6000 stakes is better than 10000 stakes.


Because the strategy of Web3 1kV is round-robin to select the suitable node, the highest reward now is not necessarily the highest forever.

#### 3.2.2 node with the highest selection rate / longest online time

This algorithm aims to help users select the node with the highest current selection rate / the longest online time according to the 1kV node. The concept of this algorithm is to encourage the pledge, which will put money into the network.

1. The node with the highest selection rate in the active set.

2. Maximum online time.


Because the strategy of Web3 1kV is round-robin, the longest online time is a more reliable indicator.


#### 3.2.3 encourage the nodes with low stake

The purpose of this algorithm is to help small/new validators to be nominated. The concept is to encourage the nominators to invest their funds in validator which are

1. Being selected by the 1kv less.

2. Low total stake

This verifier can hardly attract individual nominators because it is rarely seen on the Polkadot App. If there is an obvious entry in the app to attract the nominators to nominate this kind of node, the node with a low pledge number will be encouraged to stay in the project.



In this algorithm, x high validators (validators which are likely being nominated) are selected

(stake ranking) valid nodes are ranked according to the total number of pledge except Web3 nominators

2. Randomly select m nodes (for example, M = 2) from the top quarter nodes of the stack ranking as high verifiers


And Y low validators (validators which are rarely being nominated) to nominate the method

1. (active ranking) valid nodes are sorted according to the active set selection rate

2. Randomly select n nodes (e.g., n = 5) as the low verifier from the nodes after 1 / 4 of the stack ranking

3. Randomly select n nodes (e.g., n = 5) as the low verifier from the nodes after the active ranking

The reason for using high and low allocation is that if the nominator invests his capital in the above validators, it is more difficult for him to get income in terms of probability. Therefore, we match one (or more) easily selected nodes to ensure that this algorithm has enough attraction for the pledgor to choose



### 3.3 data analysis

We will provide the data anlyasis page for 1KV-EDST (this project) as 1KV-leaderboard page (https://thousand-validators.kusama.network/#/leaderboard). This page includes the node with support from the individual nominator and provides the related information to help the individual nominator decide.

### 3.4 key points

We hope to build a bridge between the 1kV project and the Polkadot app through this project and then help the community better. The algorithm itself should not the important points in the early stage but focus on the mechanism and how to implement iteration development in the future.


## 4、 Scalability

Firstly, it supports Kusama 1KV in the first, and Later, it can help the Polkadot 1KV plan.


## 5、 Milestone
### stage 0: design (? months)
### stage 1: ksm support(6 months)

### stage 1.1 (? months)
* add an entry point for 1kv nomination on the polkadot app
* implement selection algorithms
* add a 1kv logo on the app for users to distinguish 1kv validators

### stage 1.2 (? months)

* develop a dashboard to show the status of 1kv validators
* optimize the selection algorithms

### stage 1.3 (? months)

* Enhance the 1kv nomination system

#### Budget
* Environment for development and deploy? such as AWS
* Working hour cost

#### Stage of Treasury Support
Total cost: x USD = ?KSM
* stage 1: Infrastructure setup: x ksm
* stage 2: After verify: y ksm

### stage 2：dot support (3 months)

* Infrastructure setup (?-month)
* Develop the feature described in part 3 for Polkadot (?-month)
* Testing and verifying (?-month)

#### Budget
* Environment for development and deploy? such as AWS
* Working hour cost
* Our roles: Designer, developer

#### Stage of Treasury Support
Total cost: x USD = ?KSM
* stage 1: Infrastructure setup: x ksm
* stage 2: After verify: y ksm

## 6、 Future work

### 6.1 project operation and maintenance transfer to Web3 1kV team

If the project goes well and the function is stable and complete, it will be transferred to Web3 1kV team after the project is finished.


## 7、 Things need Web3 supports


### 7.1 polkdaot app support

Provide 1kv-edst an entry point on the Polkadot app.

### 7.3 1kV support

We would like to cooperate with 1kV team to develop this feature better.

### 7.2 Treasury support

300ksm

## 8、 Team and advantage

### 8.1 team



##### Project Manager and Developer: sophon (Riot Id)

sophon has a Ph.D. degree of applied mathematics and Master of computer engineering. He has long-term IT-development and IT-management experience for more than 10 years. He is a serial entrepreneur, and he has experience with Substrate-based blockchain technology. He is also a personal Kusama validator operator.

##### Designer and Developer: yaohsin (Riot Id)：

Yaohsin has a Ph.D. degree in computer science with a focus on information security. He is a big believer in blockchain and is a co-founder of a blockchain-based solar technology company. Currently, he is a personal Kusama validator operator.

##### Designer and Developer: tanis_ 37 (Riot Id)：

tanis_ 37 has a Master degree of computer science. He is a proficient software developer on industrial network management systems. He is also a personal Kusama validator operator.



### 8.2 advantages

#### 8.2.1 be familiar with 1kV plan

We are all involved in the 1kV project and have a deep understanding of the 1kV problem. We hope to help solve some 1kV problems through this project.

#### 8.2.2 some completed works

We have finished the data analysis work of 1kV node, and it keeps working usually. For details, please refer to https://kusama.yaohsin.net/api/validDetail
