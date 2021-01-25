
# 1KV Enhanced-Decentralized Staking Tool (1KV-EDST)

## 1,Background
### 1.1 The problem of Decentralization
As the increasing exchange value of Kusama/Polkadot, more and more institutes may occupy more and more important positions. They may hold more and more validators in the whole 1000 validators because fewer and fewer free people could afford the cost of maintaining standalone valiator. Thus degree of decentralization of KSM/DOT will decrease and it will have bad effect on the interests of personal node maintainers. Only few organization holding too many nodes will not only cause the problem of decentralization, but also reduce the overall activation of the system, such as voting, participating in proposals, speed of updating to the new version, etc.

Therefore, it is important to increase the proportion of validators held by individual users. The quatity of personal node maintainer (called validator) is the key point of deciding the degree of system decentralization.  1kV plan lauched by Web3 foundation supports provide the nomination support for some individual users with small amount of KSM/DOT by themselve. It is a key project to reduce the degree of system centralization and keep the system decentralization enough.

### 1.2 The node in 1KV plan needs support from not only web3 but others
At present, there are about 170 valid nodes in 1KV（ https://kusama.yaohsin.net/api/validators). Now only 93 nodes were successfully elected as validators, and the election success rate was about 54%. Although the 1kV plan tries to improve the success rate as much as possible through various methods but there are lots of nodes in the waiting set for a long time. Let us have a simple evaluation: if all 170 nodes in the 1KV become validators, each node needs at least 5000 nomintation including at least 50 self-nomination. If all the other nomination is from Web3, it needs at least 170 * (5000 - 50) = 841,5000 KSM. Moreover, with more and more participants, more and more nomination needs to be provided by Web3. If we only rely on Web3 foundation, we may not be able to provide enough nomination to support the successful election as the valid nominator of most nodes.

### 1.3 it is the fundamental way to solve the problem that individual nominators participate in 1kV pledge

Individual nominators participating in 1kV pledge can solve part of the problem of the source of pledge funds, a large number of individual nominators participating in 1kV can also greatly increase the financial strength of 1kV plan; individual nominators participating in 1kV plan can also increase the ability of nodes in 1kV plan to obtain stable income, because individual nominators usually do not frequently pledge and cancel the pledge, most of the individual users are not satisfied Or used to pledge in a certain node.


## 2、 Project objectives

Polkadot app provides direct pledge (one key pledge) of individual nominators for 1kV plan nodes to improve the election success rate of 1kV participants, so as to increase the source of pledge funds in 1kV plan (currently 1kV pledge funds mainly come from Web3), improve the system decentralization process and increase the system activity.

### 2.1 attractiveness to individual nominators

As the authentication node in 1kV is regulated and supervised by the government, it can at least ensure the following features, avoid joining malicious nodes, and greatly reduce the risk of individual nominators.

1. Interest consistency: self-stack is an important index for selecting verification nodes. Only by binding the interests of the node and the nominees, can we ensure that the node will do its best to maintain its operation and avoid being slammed by the system. However, at present, most of the nodes have low self-make (data). If the nominators do not know the details, they may take great risks.

2. Avoid malicious operation: the nominator should pay attention to the proportion of commission at any time, because there may be malicious nodes to increase the proportion of commission, which makes the nominator suffer inexplicable losses without knowing it.

3. Stability: the official monitors the state of the verification node in 1kV at any time to ensure the stable operation of the node and eliminate the unstable nodes.

## 3, Project Desgin
### 3.1 Basic Function
#### 3.1.1 Entry for personal nomination
In Polkadot app, more 1kV operation entrances are provided for individual nominators

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

#### 3.2.1 the current revenue is the highest

The purpose of this algorithm is to help users select the highest node of current pledge according to the 1kV node. The concept of this algorithm is to encourage pledge to invest capital

1. The node with the highest return in active set

2. The total amount of pledge is moderate, 6000 pledge is better than 10000 pledge



But because the pledge strategy of Web3 1kV is round robin, the highest income now is not necessarily the highest forever

#### 3.2.2 node with the highest selection rate / longest online time

The purpose of this algorithm is to help users select the node with the highest current selection rate / the longest online time according to the 1kV node. The concept of this algorithm is to encourage the pledge, which will put money into the network

1. The node with the highest selection rate in active set

2. Maximum online time



But because the pledge strategy of Web3 1kV is round robin, the longest online time is a more reliable indicator



#### 3.2.3 encourage the nodes with low number of pledge



The purpose of this algorithm is to make it easier for small / new verifiers to be nominated. The concept is to encourage the pledgor to invest its capital

1. Less nominees (low selection rate of active set)

2. The total amount of pledge is lower



This kind of verifier is hard to attract the general nominators because it is rarely nominated in Polkadot app, which leads to the low income of verifier from 1kV project. If there is an obvious entrance in the app to attract the nominators to nominate this kind of node, the node with low pledge number will be encouraged to stay in the project



In this algorithm, x high verifiers (easily nominated nodes) are selected

(stake ranking) valid nodes are ranked according to the total number of pledge except Web3 nominators

2. Randomly select m nodes (for example, M = 2) from the top quarter nodes of the stack ranking as high verifiers



And Y low verifiers (nodes that are difficult to be nominated) to nominate the method

1. (active ranking) valid nodes are sorted according to the active set selection rate

2. Randomly select n nodes (e.g. n = 5) as the low verifier from the nodes after 1 / 4 of the stack ranking

3. Randomly select n nodes (e.g. n = 5) as the low verifier from the nodes after the active ranking

The reason for using high and low allocation is that if the nominator invests his capital in the above validators, it is more difficult for him to get income in terms of probability. Therefore, we match one (or more) easily selected nodes to ensure that this algorithm has enough attraction for the pledgor to choose



### 3.3 data analysis

We will provide the corresponding thousand- validators.kusama.network/#/leaderboard The same data analysis interface can help 1kV team to improve the relevant operation effect. I hope 1kV team can also provide corresponding suggestions.



### 3.4 key points

We hope to build a bridge between the 1kV project and the Polkadot app through this project, and then help the community better. The algorithm itself should not mention the particularly important points in the early stage, but focus on the formation of such a mechanism and how to iterate in the future, and how free developers like us participate in the work, which we want to explore and mine.



## 4、 Scalability

Firstly, it supports KSM system and allows KSM nominators to be pledged to 1kV nodes. Later, it can support the pledge of dot nominators to 1kV nodes.



## 5、 Time plan

### stage 1: ksm support(6 months)

Including building test environment, completing code function, submitting code audit

### stage 2：dot support (3 months)

Including building test environment, completing code function, submitting code audit



## 6、 Future work

### 6.1 project operation and maintenance transfer to Web3 1kV team

If the project goes smoothly and the function is stable and complete, it will be transferred to Web3 1kV team after the support of KSM and dot is completed



## 7、 Hope for your support



### 7.1 polkdaot app support

Hope to provide 1kv-edst entrance in Polkadot app.

### 7.3 1kV support

Hope to cooperate with 1kV team to better develop this feature

### 7.2 Treasury support

300ksm

## 8、 Team and advantage

### 8.1 team



##### Project Manager and Developer: sophon (Riot Id)

sophon has a Ph.D. degree of applied mathematics and Master of computer engineering. He has long-term IT-development and IT-management expierence for more than 10 years. He is a serial entrepreneurhas and he has experice of Substrate-based blockchain technology. He is also personal Kusama validator operator.

##### Designer and Developer: yaohsin (Riot Id)：

Yaohsin has a Ph.D. degree in computer science with a focus on information security. He is a big believer in blockchain and is a co-founder of a blockchain-based solar technology company. Currently, he is a personal Kusama validator operator.

##### Designer and Developer: tanis_ 37 (Riot Id)：

tanis_ 37 has a Master degree of computer science. He is a proficient software developer on industrial network management systems. He is also a personal Kusama validator operator.




### 8.2 advantages

#### 8.2.1 be familiar with 1kV plan

We are all involved in the 1kV project and have a deep understanding of the 1kV problem. We hope to help solve some 1kV problems through this project.

#### 8.2.2 some completed works

We have finished the data analysis work of 1kV node, and keep working normally. For details, please refer to https://kusama.yaohsin.net/api/validators
