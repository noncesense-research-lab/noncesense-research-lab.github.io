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

Special thanks to the many denizens of #monero-reserach-lab and #noncesense-research-lab that have shared their ideas, experience, and perspectives during fascinating discussions


## Selected Projects & Results
### Monero Archival Project 
The [Monero Archival Project](https://github.com/mitchellpkt/monero_archival_project) is a Noncesense endeavor devoted to retaining all blockchain data, including the "lost stories" in orphaned blocks and transactions. This is possible due to our unique data set collected by our [custom archival daemon](https://github.com/neptuneresearch/monerod-archive). Archival nodes run 24/7 on a global network of virtual private servers, capturing a comprehensive realtime view of both obvious and subtle network activity. A live interface ([repo](https://github.com/neptuneresearch/monero-archive-monitor)) interacts with the daemon database to provide real-time visualizations.

###  Miner-reported timestamps are "nonsense!"
A block's miner selects the value included as its timestamp, so the reported value does not always reflect reality. MAP's archival nodes keep track of the time of actual receipt, to study timestamp spoofing, along with network latency and topology. Interestingly, the nodes often receive blocks that are timestamped from the future. Investigation of this phenomenon led to the observation of "Merlin" blocks, where the timestamp in a block precedes the timestamp in the previous block (e.g. block [1607957](https://moneroexplorer.com/search?value=1607957) and block [1607958](https://moneroexplorer.com/search?value=1607958), with respective timestamps 1728h and 1723h). Approximately 2% of Monero blocks exhibit this odd behavior. Consider the implications of the tight distribution around -400 seconds, echoing the typical distribution.

![image.png](/images/merlin_blocks.png)

### Selfish mining detection
Analyses of alternative chains and reorganization events, combined with node receipt timestamp metadata, enables detection of probable [selfish mining](https://arxiv.org/abs/1311.0243) or [stubborn mining](https://eprint.iacr.org/2015/796.pdf).

One such instance is described in MAP wiki article: [Selfish mining at 1636647](https://github.com/Mitchellpkt/monero_archival_project/wiki/Selfish-mining-at-1636647) 

### Custom ring composition spoils Monero fungibility
This [wiki article](https://github.com/Mitchellpkt/monero_archival_project/wiki/Custom-ring-composition-spoils-Monero-fungibility) documents how a series of Monero transactions can be traced by two known analyses (unusual ring size and churn timing). Furthermore, a new heuristic is discovered: identifying sets of transactions with non-standard decoy selection algorithms. These are the types of subtle signals that are ostensibly obfuscated, but statistically quite loud! Distinct failure modes are dissected, and source attribution is validated by experimental transactions.

![image.png](images/MyMonero_TEST_41_ring_member.png)

### Fixed fee options (Bohr fees)
Custom fee options have the potential to damage privacy, and thus fungibility. Many of the [conceptual reasons for fixed ring sizes](https://github.com/monero-project/monero/issues/4229#issuecomment-415139034) transfer to the questions of fixed fee options. IsthmusCrypto proposes that the network enforces discrete specific options for fee levels. For example, the base fee `B` with units of XMR/kB could be calculated by the normal dynamic fee algorithm, and the sender can adjust the priority by preset multiples, e.g. from `{0.002, 0.25*X, 0.5*X, X, 2*X, 4*X, 8*X}`. This saves space in a transaction since the user can represent their selection with only a single alphanumeric character. There is no room for wallet software mistakes or poor design choices to exhibit different and thus detectable behavior.

### Node ecosystem observations 
*(upcoming, collaborators welcome)* Methods are being explored to track enumeration and uptime of Monero nodes, to study the variability and volatility charactistics over multiple timescales. We're also exploring methods for ascertaining adoption rates around software upgrades.

### IP bottlenecks - a subtle centralization 
Performed a small study of nodes doubled up on IP addresses. Checked peer lists and found duplicates. This is a subtle type of centralization - if 20% of our nodes/miners are showing up over a handful of ProtonVPN addresses, then another DoS on the VPN would have the side effect of knocking a disproportional number of machines off the network.	

### Stop by for lots more!
If you want to see what else we're thinking about, check out the [Monero Archival Project issues](https://github.com/Mitchellpkt/monero_archival_project/issues) and join our [IRC channel](https://www.irccloud.com/invite?channel=%23noncesense-research-lab&hostname=chat.freenode.net&port=6697&ssl=1)

## NRL reading corner - some classics, and some fresh
*(links to good papers, not all by us)*
-  [An Empirical Analysis of Traceability in the Monero Blockchain](https://arxiv.org/pdf/1704.04299.pdf) and the [response from the Monero community](https://getmonero.org/2018/03/29/response-to-an-empirical-analysis-of-traceability.html)
-  [New kids on the block: an analysis of modern blockchains](https://allquantor.at/blockchainbib/pdf/anderson2016new.pdf)
-  [Digging into Browser-based Crypto Mining](https://arxiv.org/pdf/1808.00811.pdf)
-  [Majority is not Enough: Bitcoin Mining is Vulnerable](https://arxiv.org/abs/1311.0243)
-  [Stubborn Mining: Generalizing Selfish Mining and Combining with an Eclipse Attack](https://eprint.iacr.org/2015/796.pdf)
-  [Opportunistic investigation of Monero miners during April 2018 network update](https://hackernoon.com/opportunistic-investigation-of-monero-miners-during-march-2018-network-update-cfd6ad8a027f) *(by IsthmusCrypto)*

## Secure contact

[noncesense-research-lab@protonmail.com](mailto:noncesense-research-lab@protonmail.com)

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: OpenPGP.js v3.1.2
Comment: https://openpgpjs.org

xsBNBFusbQkBCADLfpl13DBKyjEzC0XxM5xAxYKH2jSlGT7ewKVa9KIyM76z
pydj5TkZCOrmgs/m26ffOOZ8/RV0FEylQ4B+Cu3QnYS90mI/XXQnPev18Pk2
MsEN2maXjXIMdj0QWB8Am3JBlb63oQKOGsvaXdJW891o7httTXQFfY0vhSiL
ytpIqki64XXqYAcq1mPHXFRgURBCeOokRn19aRVWUsD4PNqbEifWMPIcWnq1
V3EO58QFCO4lZIP9JRVTQGELZnFRFrCEbFa9vVbDb5L+sSuVcxGIP/QFfiB5
U3FHxvEk02sicbGLk+9hEguCcM2c9fYQ7Dp8nwhis3Q6BwJvQyWp3iH1ABEB
AAHNUSJub25jZXNlbnNlLXJlc2VhcmNoLWxhYkBwcm90b25tYWlsLmNvbSIg
PG5vbmNlc2Vuc2UtcmVzZWFyY2gtbGFiQHByb3Rvbm1haWwuY29tPsLAdQQQ
AQgAKQUCW6xtCQYLCQcIAwIJEKWDEBOfci8VBBUICgIDFgIBAhkBAhsDAh4B
AACSvgf/TR2+/FhFyzrDTsI8yI61SPkLPoCm5+QK0NtcP1w815lQHj/YVt6K
9v1wQt1Q669yQxa8cvwlZAMTCoQ1Shykw1mZ7xKrQbpykoWfWyZKoVNak+tR
ZjEj9qruKvpeyOIYDZWIANfgL118JLliq7GgFtTo1CnJcJFgOahQNAAt2veR
+LVlUJybjr/1aVaI1nlgKr9xEXUSTcl72g1v77CO/LYgMo0tJA1Xj5YGPUMR
KJQh0yMAT2LgAtRLqG3uSS5WgC0WKY60vMW/ZTmIs8gFKqa00OjRWJzX/Ldz
oqpYcuZmqHOh8XoPyiy/lUE12xQb/9S+vtX669Hz8cwtsgRRy87ATQRbrG0J
AQgA5+NJijhjy+oXtO1Cmqrui8oY7H7USjnh6SbO+XzgfVN35XbDEINBwwpX
cnTe3cZ7C1nO4JuvNyuSGqaYYOEYzPFYOVgdbV9qqQv0zt04KvRoMEwA7gil
pTkf9SCFjQqe1XtH3sjTWqcCXPSLpGYSM6ROR1G3r2W6aj13MsPrfrJ6MoMn
twl+sd1CdhB/mc2SPQsMpK+8OcqJHx4HB89tkyRMTOWH1Wv2bSeJkPBT45s6
9OxOk3LsBAfFl11TUTu4s48yNt4osCTJJfGQ2n/4lM3eIxCkHZ8WTs/Mpq0U
FGM9A0EkAS4JMSQcduIkcOc1Az+Le21rl+wVCHTXIV22CwARAQABwsBfBBgB
CAATBQJbrG0JCRClgxATn3IvFQIbDAAAu94H+gLJ1G2SADrD+YMCY3BGcTYS
pPZAajNEzYtP73h46dBxm5Kr7hSsHU2J+1gc94mMSM+U3V3PauKl9ow8nMhB
gNeq98i+n1QE3Pdk3faLdSqL1MuaS9tfnSi6BNHdcebWMvIyu62ydOjbmiXR
se8gmwpxV5uuAZPipq4KaEMHw2wFSxtSlDZJmmL2r+yZ65ImykKmNXR1OlbX
VyJOk9KieS8pYOTEW/aoD8Bl/Kqh3kog+nAD9Ozo99naBw3r8S8l0RSFqnJk
l/dYYAD8EqfLf/mczCdWu/ZfxVW9HAyCmqIafvf0hTSEsVGVDSl1/waTx8Um
HEFdx8XmoZVhMkrekxU=
=+Okj
-----END PGP PUBLIC KEY BLOCK-----
```
