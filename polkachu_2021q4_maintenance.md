# Polkachu 2021 Q4 Maintenance

This treasury proposal is between the Kusama Council and Scenic Hills LLC (d.b.a Polkachu), an LLC registered in the United States with EIN 84-4435092.

## Service description
- Polkachu maintains a popular dashboard for the Thousand Validators Program. The team has engaged in the Thousand Validators Program's Element chats of both Kusama and Polkadot, seeking feedback and continuously making improvement. When the Program announced the latest scoring changes, Polkachu's frontend was updated within days, even ahead of the official program site. Sample Pages: [Kusama Dashboard](https://polkachu.com/kusama/thousand_validators) and [Polkadot Dashboard](https://polkachu.com/polkadot/thousand_validator)
 
- Polkachu maintains a validaotr/nominator search portal called [Scout](https://polkachu.com/scout). Through the interface, users can quickly look up the historical performance data of a validator/nominator. The data are cached so it is much faster than the official Polkadot JS App. Sample validator profile [here](https://polkachu.com/kusama/validators/CsKvJ4fdesaRALc5swo5iknFDpop7YUwKPJHdmUvBsUcMGb). Sample nominator profile [here](https://polkachu.com/kusama/nominators/HTAeD1dokCVs9MwnC1q9s2a7d2kQ52TAjrxE1y5mj5MFLLA). 

- Polkachu maintains the historical state of the network for Kusama and Polkadot. We track many on-chain metrics each era. Sample pages: [State of Kusama Network](https://polkachu.com/kusama/era_summaries) and [State of Polkadot Network](https://polkachu.com/polkadot/era_summaries). In fact, we were among the first who reported the underperformance of Kusama parachain validation around Era 2642. The screenshots of our page were shared in community chats when we reported the issue. 

- Polkachu also open-source most of our Kusama/Polkadot related work. For example, 
     - [Polkadot/Kusama Node Deployment Script](https://github.com/polkachu/polkadot-validator)
     - [Other Substrate-Based Node Deployment Script](https://github.com/polkachu/substrate-validator)
     - [Monitoring Server Deployment Script](https://github.com/polkachu/server-monitoring)
     - [Polkadot/Kusama Validator Resource Site on Gitbook](https://github.com/polkachu/validator-resources)
     - [Secure Server Setup for Validator](https://github.com/polkachu/secure-server-setup)


## Builder Philosophy
- **Solve Own Problem**: As a validator on Kusama and Polkadot ourselves, we build tools to solve our own problem initially. Our main struggle was the loading speed and the lack of historical data on the official polkadot app. So we build the site to optimize these two elements. It turns out that the community feels the same pain point like us, 
- **Optimize on Speed**: We spend lots of time optimizing the page loading speed, which we believe is the main reason why users use our site in stead of the official polkadot app or Thousand Validator Dashboard. 
- **Caching Historical Data**: Because storage is expensive on-chain, Kusama/Polakdot purge states every 84 eras. To preserve the historical data, we query on-chain data each era and cache them in a relational databse. As a result, our dashboard has more complete historical data with fast loading speed. 
- **Make Good UI**: Our UI design is simple, clean and functional. We heavily use modern javascript frameworks (vue.js in our case) to make the user interaction delightful. For example, the search on Thousand Validator Dashboard was lightening fast and intuitive. 

## Q1 2022 Roadmap: Snapshot Service
We started our Kusama/Polkadot journey in May 2021. In the last 7 months, our site has attracted more and more users, reaching an all-time high of 722 unique users in Dec 2021. As the site becomes more popular, we plan to build additional features for the community. 

One major initiative underway is a node snapshot service to supplement the current popular snapshot service provided by Polkashots.io. When we reviewed its treasury proposal a month ago, we were struck that we currently do not have an alternative service: "A unique snapshot service that many independent validators relies on constitues a centralization risk. It remains our hope that other ecosystem participants will step in and offer an alternative service." [Source](https://kusama.polkassembly.io/post/1211). We have already finished the script and should be able to deploy it in the next few weeks. The snapshot script is already open-sourced within an Ansible playbook called "snapshot_script.yml" in the [repo](https://github.com/polkachu/polkadot-validator). 

We briefly communicated with the Polkashots team. To build redundancy, 
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title  dsfs     |
| Paragraph   | Text        |

Operational expenses
The labor cost is 660 EUR/month including 2 engineers in 2 geographical locations (Western US and Western Europe).

In addition, we pass along the cloud costs with a 30% markup.

Polkashots is hosted on google cloud. Google cloud has the concept of "projects" which allows for segregation of costs. The cloud cost is determined as follows:

from June 1 to October 10, 2021, polkashots was hosted in a google cloud project shared with other MIDL.dev services named "MIDLUS" for which we estimate about 30% of the costs were incurred by generation and download of Kusama snapshots.
from October 11, 2021 to November 30, 2021, we moved polkashots to a dedicated google cloud project named "MIDLPS", allowing for the most precise cost calculation. We arbitrarily allocate 50% of these costs to Polkadot and 50% to Kusama. A dedicated project for each network would incur overhead costs that we do not feel are necessary.
A majority of these costs are network egress. Google cloud egress costs are in the higher range, similar to Azure and Amazon. Google cloud has two tiers, premium ($0.12/Gb for most regions) and standard ($0.85/Gb for most regions). The premium tier is using google private network across the globe. Polkashots uses the premium tier.

The costs have gone upwards after the introduction of parachains. This is due to the increased storage requirement of the relay chain node in the presence of parachains: as of this writing, a pruned kusama node with 1000 blocks uses 50Gi of storage (7z compressed). In other terms, it costs the treasury $6 each time someone downloads a Kusama snapshot.

The usage of the best cloud platform money can buy is justified by the benefits: a faster download speed and better reliability means that the nodes are more apt to recover quickly in case of accidental loss of storage, making the entire network more resilient.

Screenshots of the billing console are attached for reference.

Usage
From the MIDLPS billing screenshot, we can see 17,262 Gibibytes of download from the period Oct 10-Nov 31 from all regions excluding Asia and Australia. Polkadot snapshot size is 17Gi and Kusama snapshot size is 50Gi, so assuming a medium download file size of 34Gi, there were 500 downloads during the period, or 10 downloads per day. This is a combined figure for Polkadot and Kusama networks.

Note
This proposal is for the Kusama portion of polkashots. We will be submitting a similar proposal to the Polkadot council.

