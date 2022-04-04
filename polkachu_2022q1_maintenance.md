# Polkachu 2022 Q1 Maintenance

This treasury proposal is between the Kusama Council and Scenic Hills LLC (d.b.a Polkachu), an LLC registered in the United States with EIN 84-4435092. This is our second quarterly maintenance proposal. The first quarterly proposal can be found [here](/polkachu_2021q4_maintenance.md).


## 2022 Q1 Projects
In 2022 Q1, we released two major projects while maintaining all existing ones. 

First, We have started a [node snapshot service](https://polkachu.com/snapshots) to supplement the only existing snapshot service provided by Polkashots.io. We support both RocksDB and ParityDB for Kusama and Polkadot. For each, we take one snapshot each day while keeping another one around 100K block behind (about 1 week ago). 

|              | RocksDB       | ParityDB    |
| ------------ | --------------| ----------- |
| Polkadot     | Yes           | Yes         |
| Kusama       | Yes           | Yes         |

Second, we have launched [Payout Guard](https://polkachu.com/payout_guard) to help small independent validators to trigger payouts automatically at no cost of their own each era. This product turns out to be quite popular, especially within the Thousand Validator Program community. Currently, we are managing 20 Polkadot validators and 63 Kusama validators. In 2022 Q1, we processed 159 Polkadot payouts and 5921 Kusama payouts in total. These payouts are triggered through our bot acccounts: [Polkadot](https://polkadot.subscan.io/account/14H2TZhfH13ebngvvUtZLGp8mFGw4DyH5uSSqpYVUnfkhRLu) and [Kusama](https://kusama.subscan.io/account/EAm8eWXxTXFTBEzmAVbhF4vu8r9LCpxsJ2u6QAS5N59VPDF). The list of validators and payout transactions are available upon request. The information is all available on-chain in public, but we have it in a more organized fashion stored in a relational database. 

|              | Validators    | Payouts     |
| ------------ | --------------| ----------- |
| Polkadot     | 20            | 159         |
| Kusama       | 63            | 5921        |


## Overall Service description
While it is fun and exciting to release new projects for the community, we also continue to main our existing projects. 
- Polkachu maintains a popular dashboard for the Thousand Validators Program. The team has engaged in the Thousand Validators Program's Element chats of both Kusama and Polkadot, seeking feedback and continuously making improvement. When the Program announced the latest scoring changes, Polkachu's frontend was updated within days, even ahead of the official program site. See: [Kusama Dashboard](https://polkachu.com/kusama/thousand_validators) and [Polkadot Dashboard](https://polkachu.com/polkadot/thousand_validator)
 
- Polkachu maintains a validator/nominator search portal called [Scout](https://polkachu.com/scout). Through the interface, users can quickly look up the historical performance data of a validator/nominator. The data are cached so it is much faster than the official Polkadot JS App. Sample validator profile [here](https://polkachu.com/kusama/validators/CsKvJ4fdesaRALc5swo5iknFDpop7YUwKPJHdmUvBsUcMGb). Sample nominator profile [here](https://polkachu.com/kusama/nominators/HTAeD1dokCVs9MwnC1q9s2a7d2kQ52TAjrxE1y5mj5MFLLA). 

- Polkachu maintains the historical state of the network for Kusama and Polkadot. We track many on-chain metrics each era. Sample pages: [State of Kusama Network](https://polkachu.com/kusama/era_summaries) and [State of Polkadot Network](https://polkachu.com/polkadot/era_summaries). 

- Polkachu also open-sources most of our Kusama/Polkadot related work. For example, 
     - [Polkadot/Kusama Node Deployment Script](https://github.com/polkachu/polkadot-validator)
     - [Other Substrate-Based Node Deployment Script](https://github.com/polkachu/substrate-validator)
     - [Monitoring Server Deployment Script](https://github.com/polkachu/server-monitoring)
     - [Polkadot/Kusama Validator Resource Site on Gitbook](https://github.com/polkachu/validator-resources)
     - [Secure Server Setup for Validator](https://github.com/polkachu/secure-server-setup)


## Builder Philosophy
- **Solve Own Problem**: As a validator on Kusama and Polkadot ourselves, we build tools to solve our own problem initially. For the snapshot service, we used other services so much that we have finally decidecd to offer our own service to provide redundancy for us and for the community. For Payout Guardm, we have been using the payout bot ourselves to work out all the details before we productized it as a community offering. 
- **Optimize on Speed**: We spend lots of time optimizing the page loading speed, which we believe is the main reason why users use our site in stead of the official polkadot app or Thousand Validator Dashboard. 
- **Make Good UI**: Our UI design is simple, clean and functional. We heavily use modern javascript frameworks (vue.js in our case) to make the user interaction delightful. For example, the search on Thousand Validator Dashboard was lightening fast and intuitive.
- **Engage with Community**: Before we release a project, we always try to get the feedback from the community first. The Payout Guard idea came out of an Element chat discussion. After its release, we also got feedback so that we fine-tuned the instruction. 

## Operational expenses
The labor cost is 1600 USD/month with 1 engineer (20 hours per month with 80 USD rate). In addition, we pass along the cloud costs with 20% markup. We use Digital Ocean. Below is the unit cost per month:

| Cost Item          | Cost      | 
| ------------        | --------------| 
| Labor   | $1600/month (20 hours per month with 80 USD rate)  | 
| Website Droplet | $20/month | 
| Database Droplet | $20/month | 
| Digital Ocean Space (spanshots) |  $17.42 in Jan, $322.68 in Feb and 150.55 in Mar   | 

Below is the Q1 2022 budget:
| Cost Item          | Cost      | 
| ------------        | --------------| 
| Labor, total    | $4800 | 
| Website Hosting, total | $60 + $12 markup | 
| Database Hosting, Total| $60 + $12 markup| 
| Digital Ocean Space| $490 + $98 markup| 
| Kusama Payout Cost| Rough estimate: 0.2 KSM -> $36 | 
| Polkadot Payout Cost| Rough estimate: 1.8 DOT -> $36| 
| Total| $5604 | 
| Exchange Rate KSM/USD| ??  | 
| Proposal (KSM)| ?? | 

We put the whole expense in this Kusama proposal and will not submit a separate proposal on Polkadot. But we are happy to seperate them out to two unique proposals. 

## 2022 Q1 Site Traffic Recap
We started our Kusama/Polkadot journey in May 2021. In the last 10 months, our site has attracted more and more users, reaching an all-time high of 3201 unique users in March 2022. 

![Google Analytics Chart](https://i.imgur.com/68iDSxD.png)
