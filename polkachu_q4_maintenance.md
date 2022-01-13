This treasury proposal is between the Kusama Council and Scenic Hills LLC (d.b.a Polkachu), an LLC registered in the United States with EIN 84-4435092.

## Service description
A functioning infrastructure to provide usable blockchain database snapshots for the Kusama network, to the benefit of node operators and validators,
New snapshots at least once per day. Snapshots are filesystem dumps of the Kusama node storage backend files, of variety RocksDb, of type pruned, with a depth of 1000 blocks, compressed in 7z format, that can be used by validators to quickly spin up or restore their infrastructure,
A website frontend at polkashots.io with relevant metadata and download links, including a permanent link that always redirects to the most recent snapshot,
Best effort incident and problem management,
Redundant implementation setup which allows for continuity, seamless upgrades and basic disaster recovery & contingency management.
Context
Node operators must have a contingency plan for loss of storage. For us at MIDL.dev, it consists of regularly taking snapshots of the node filesystem and backing it up for recovery if needed. We regularly generate these archives for our own benefit as well as the community. All cloud automation code used for generation of snapshots is open-source so node operators can easily replicate the setup in order to be in full control of the generated snapshots.

The website polkashots.io has been operational for a year now and providing Polkadot and Kusama pruned snapshots for validators. It has had excellent uptime. It is very frequently mentioned in the Validator Lounge Matrix channels and there are youtube videos referencing them. It is beneficial to the ecosystem by providing a path for validators to quickly and safely recover from a storage failure or migrate their operations.

Alternatives
The warp sync feature has been implemented in Polkadot 0.9.9, however it still requires several hours for a full sync.

A unique snapshot service that many independent validators relies on constitues a centralization risk. It remains our hope that other ecosystem participants will step in and offer an alternative service.

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

