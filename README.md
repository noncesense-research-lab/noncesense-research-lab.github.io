![low_quality_rough_logo_small.png](low_quality_rough_logo_small.png)

## About us
Noncesense Research Lab builds tools and analyses to study blockchain systems from an empirical data science perspective. Distributed consensus systems produce large amounts of canon data (e.g. number of transactions in a given block) along with oceans of ephemeral metadata - connection patterns, broadcast timestamps, data size, orphaned/alternative chains, etc. 

Noncesense seeks the signal in the noise - the anomalies, the edge cases, the subtle temporal and heuristic signatures. We curate a unique dataset, that enables endless new types of analyses. Data, tools, and analyses are disseminated as free and open source software / articles. While Monero is our most common use/test case, the vast majority of the analyses are directly conceptually transferrable to other blockchain projects.

## Contact / Invitation  
Much of our R & D discussions occur in [#noncesense-research-lab](https://www.irccloud.com/invite?channel=%23noncesense-research-lab&hostname=chat.freenode.net&port=6697&ssl=1) on Freenode IRC. Please join us! Feel free to introduce yourself, or lurk and learn.

Sporadic communication occurs asynchronously, since our volunteer contributors are distributed across multiple continents. Many members use IRCcloud to continue receiving messages even when their devices are offline. 

## Code Contributors 
-  [IsthmusCrypto](https://github.com/mitchellpkt)
-  [NeptuneResearch](https://github.com/neptuneresearch)
-  [SerHack](https://github.com/serhack)
-  [NeffMallon](https://github.com/neffmallon)

Special thanks to the many denizens of #monero-reserach-lab and #noncense-research-lab that have shared their ideas, experience, and perspectives during fascinating discussions


## Projects & Results
### Monero Archival Project 
The [Monero Archival Project](https://github.com/mitchellpkt/monero_archival_project) is a Noncesense endeavor devoted to retaining all blockchain data, including the "lost stories" in orphaned blocks and transactions. This is possible due to our unique data set collected by our [custom archival daemon](https://github.com/neptuneresearch/monerod-archive). Archival nodes run 24/7 on a global network of virtual private servers, capturing a comprehensive realtime view of both obvious and subtle network activity. 

###  Miner-reported timestamps are "nonsense!"
A block's miner selects the value included as its timestamp, so the reported value does not always reflect reality. MAP's archival nodes keep track of the time of actual receipt, to study timestamp spoofing, along with network latency and topology. Interestingly, the nodes often receive blocks that are timestamped from the future. Investigation of this phenomenon led to the observation of "Merlin" blocks, where the timestamp in a block precedes the timestamp in the previous block (e.g. block [1607957](https://moneroexplorer.com/search?value=1607957) and block [1607958](https://moneroexplorer.com/search?value=1607958), with respective timestamps 1728h and 1723h). Approximately 2% of Monero blocks exhibit this odd behavior. Consider the implications of the tight distribution around -400 seconds, echoing the typical distribution.

![image.png](/images/merlin_blocks.png)

### Selfish mining detection
Analyses of side chains and reorganization events, combined with node receipt timestamp metadata, enables detection of probable [selfish mining](https://arxiv.org/abs/1311.0243) or [stubborn mining](https://eprint.iacr.org/2015/796.pdf). A

One such instance is described in MAP wiki article: [Selfish mining at 1636647](https://github.com/Mitchellpkt/monero_archival_project/wiki/Selfish-mining-at-1636647) 

### Custom ring composition spoils Monero fungibility
This [wiki article](https://github.com/Mitchellpkt/monero_archival_project/wiki/Custom-ring-composition-spoils-Monero-fungibility) documents how a series of Monero transactions can be traced by two known analyses (unusual ring size and churn timing). Furthermore, a new heuristic is discovered: identifying sets of transactions with non-standard decoy selection algorithms. These are the types of subtle signals that are ostensibly obfuscated, but statistically quite loud! Distinct failure modes are dissected, and source attribution is validated by experimental transactions.

![image.png](images/MyMonero_TEST_41_ring_member.png)

### Node ecosystem observations 
*(upcoming, collaborators welcome)* Methods are being explored to track enumeration and uptime of Monero nodes, to study the variability and volatility charactistics over multiple timescales. We're also exploring methods for ascertaining adoption rates around software upgrades.

### Fixed fee options (Bohr fees)
Custom fee options have the potential to damage privacy, and thus fungibility. Many of the [conceptual reasons for fixed ring sizes](https://github.com/monero-project/monero/issues/4229#issuecomment-415139034) transfer to the questions of fixed fee options. IsthmusCrypto proposes that the network enforces discrete specific options for fee levels. For example, the base fee `B` with units of XMR/kB could be calculated by the normal dynamic fee algorithm, and the sender can adjust the priority by preset multiples, e.g. from `{0.002, 0.25*X, 0.5*X, X, 2*X, 4*X, 8*X}`. This saves space in a transaction since the user can represent their selection with only a single alphanumeric character. There is no room for wallet software mistakes or poor design choices to exhibit different and thus detectable behavior.

### IP bottlenecks - subtle centralization 
Performed a small study of nodes doubled up on IP addresses. Checked peer lists and found duplicates. This is a subtle type of centralization - if 20% of our nodes/miners are showing up over a handful of ProtonVPN addresses, then another DoS on the VPN would have the side effect of knocking a disproportional number of machines off the network.	

### ... and lots more!
If you want to see what else we're thinking about, check out the [Monero Archival Project issues](https://github.com/Mitchellpkt/monero_archival_project/issues) and join our [IRC channel](https://www.irccloud.com/invite?channel=%23noncesense-research-lab&hostname=chat.freenode.net&port=6697&ssl=1)

## NRL reading corner - some classics, and some fresh
*(links to good papers, not by us)*
-  [An Empirical Analysis of Traceability in the Monero Blockchain](https://arxiv.org/pdf/1704.04299.pdf) and the [response from the Monero community](https://getmonero.org/2018/03/29/response-to-an-empirical-analysis-of-traceability.html)
-  [New kids on the block: an analysis of modern blockchains](https://allquantor.at/blockchainbib/pdf/anderson2016new.pdf)
-  [Digging into Browser-based Crypto Mining](https://arxiv.org/pdf/1808.00811.pdf)
-  [Majority is not Enough: Bitcoin Mining is Vulnerable](https://arxiv.org/abs/1311.0243)
-  [Stubborn Mining: Generalizing Selfish Mining and Combining with an Eclipse Attack](https://eprint.iacr.org/2015/796.pdf)

## Secure contact
noncesense-research-lab@protonmail.com
