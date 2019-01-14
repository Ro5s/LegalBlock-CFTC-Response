# LegalBlock CFTC Response

On December 11th, 2018 the CFTC [submitted a public "Request for Input"](https://www.cftc.gov/sites/default/files/2018-12/federalregister121118.pdf) which asks for clarity and answers around Ethereum. The following is a list of all questions asked in the RFI. The following answers were developed on LegalBlock, a decentralized-driven legal community practicing Collective Wisdom.

_**From the CFTC: In providing your responses, please be as specific as possible, and offer concrete examples where appropriate. Please provide any relevant data to support your answers where appropriate. The Commission encourages all relevant comments on related items or issues; commenters need not address every question.**_

DEADLINE: February 9, 2019

## Purpose and Functionality

### 1. What was the impetus for developing Ether and the Ethereum Network, especially relative to Bitcoin?

Answer:

### 2. What are the current functionalities and capabilities of Ether and the Ethereum Network as compared to the functionalities and capabilities of Bitcoin?

Answer:

### 3. How is the developer community currently utilizing the Ethereum Network? More specifically, what are prominent use cases or examples that demonstrate the functionalities and capabilities of the Ethereum Network?

Prominently, the Ethereum development community has used the network to (i) manage digital token fundraisers for kickstarting open-source software projects that, by virtue of not developing proprietary IP, might not otherwise be able to attract funding, and, similarly, to (ii) manage bounty smart contracts that incentivize and coordinate open-source development through platforms such as Gitcoin and Bounties Network. 

### 4. Are there any existing or developing commercial enterprises that are using Ether to power economic transactions? If so, how is Ether recorded for accounting purposes in a comprehensive set of financial statements?

Answer:

### 5. What data sources, analyses, calculations, variables, or other factors could be used to determine Ether’s market size, liquidity, trade volume, types of traders, ownership concentration, and/or principal ways in which the Ethereum Network is currently being used by market participants?

Answer:

### 6. How many confirmations on the Ethereum blockchain are sufficient to wait to ensure that the transaction will not end up on an invalid block?

Answer:

## Technology

### 7. How is the technology underlying Ethereum similar to and different from the technology underlying Bitcoin?

Answer:

### 8. Does the Ethereum Network face scalability challenges? If so, please describe such challenges and any potential solutions. What analyses or data sources could be used to assess concerns regarding the scalability of the underlying Ethereum Network, and in particular, concerns about the network’s ability to support the growth and adoption of additional smart contracts?

Answer:

The Ethereum Network faces what many have called a 'scalability trilemma' for transaction processing in computer science, wherein blockchain systems are largely forced to choose two out of the following three options: (i) Decentralization (number of block producers), (ii) Scalability (transaction throughput), and (iii) Security (cost to attack network). 

In other words, a highly decentralized and secure blockchain system will almost necessarily have to make sacrifices on its transaction processing capabilities - - for example, because of hard-coded limits on computation per block, the Ethereum Network currently supports about 15 transactions per second versus the thousands processed by a centralized provider like Visa.

In the case of Bitcoin, where the cryptocurrency might store large values, or Ethereum, where the network is valued for trustless computation, the permissionless Proof of Work consensus algorithm is chosen for its relatively high offerings in terms of network security and decentralization (proven difficulty to manipulate); however, systems that target different blockchain use cases, such as Steem for micropayments, might use Delegated Proof of Stake (DPoS) as their consensus algorithm to offer more competitive processing speeds, wherein a limited delegation or more 'permissioned' number might mine blocks and have less overhead in reaching consensus, offering higher transaction throughput but losing aspects of decentralization and security in the same process.

For Ethereum, these scalability challenges are mostly present for transactions 'on chain' at the fundamental, protocol layer ('Layer 1') - - more immediately, 'off chain' or 'Layer 2' solutions have been presented for scaling Ethereum's processing capabilities by recording certain sets of transactions off of the blockchain (while maintaining core Ethereum security guarantees). In a recent post (August 2018), Vitalik Buterin, Ethereum inventor and co-founder, argues:

“(A)s blockchains become more and more mature, layer 1 will necessarily stabilize, and layer 2 will take on more and more of the burden of ongoing innovation and change...”

While this brief overview will focus on these Layer 2 solutions as more imminent developments, there is active research on Layer 1 scaling solutions. "Sharding" is one such solution gaining significant traction within the Ethereum research community. Whereas the current network design requires all nodes to process every transaction (presenting sure bottlenecks for sake of decentralization), "sharding" proposes secure methods for separating various consensus functions to different participants, drastically reducing system load on Ethereum nodes and possibly enabling thousands of transactions per second.

Among emerging Layer 2 solutions for scaling the Ethereum Network, "Plasma" has attracted significant attention and collaboration from the research community (while this response focuses on Plasma, there are a number of promising Layer 2 scaling solutions, such as "State Channels" and "Truebit" that are seeing implementations). 

As described above, recording transactions on the root chain (in this case Ethereum), is relatively slow and costly, as each transaction, from micro to massive, is treated with the same level of security. Before Layer 1 scaling solutions such as "sharding" are implemented, many see establishing relatively secure, parallel transaction methods "off chain" as a promising path to more immediate adoption of blockchain applications. 

On August 11, 2017, Vitalik Buterin and Joseph Poon published a whitepaper describing Plasma, a proposed framework for “incentivized and enforced execution of smart contracts” that is scalable to potentially millions of transactions per second and which would service a significant amount of decentralized financial applications.

At its core, Plasma seeks to resolve the tensions of the so-called scalability trilemma and deliver scalable blockchain applications without sacrificing security through a combination of smart contracts and cryptographic verification.

As a proposed “Layer 2” scaling solution (i.e., not an upgrade to base blockchain layer), it targets applications where it is not necessary or even desirable to record every transaction to a blockchain, such as daily coffee purchases.

The general intuition within the Ethereum research community is that these more mundane blockchain transactions might be better recorded to application-specific “side chains,” where assets are locked up on the main chain, replicated on a parallel blockchain, and then transacted under a more efficient consensus mechanism, such as DPoS; fallback to the root chain with less efficient consensus rules (but greater security) is then only utilized for high-value transactions or to establish finality after certain checkpoints.

The goal of the Plasma framework is to reap such massive scalability benefits of side chains while optimizing “fall back” safety to assets locked in the root chain in the event that side chain consensus fails or is overpowered (risking theft of user funds).

Employing an interactive exit mechanism to detect malicious behavior, plasma chains are not quite side chains, which lose their state in the event of failure. When a plasma chain breaks, state is exited but remains intact; as a basic guarantee, the root chain utilizes mathematically verifiable methods to handle disputes and reward the correct party with their funds. Strong security guarantees are therefore a crucial and distinguishing feature of Plasma designs: digital assets that cannot be double-spent, withheld, and are always redeemable on the root chain.

In this way, solutions developed under the Plasma framework seek to offer blockchain security and finality for more mainstream use cases. For example, a cross-border payment networks or gaming platform might issue digital assets as ERC721s (non-fungible tokens) on the Ethereum root chain to take advantage of its network security but then get much greater day-to-day transaction throughput for these assets on a plasma ‘child chain’ running under, e.g., “Proof of Stake” or “Proof of Authority” consensus.

Elaborating on this framework for building more scalable blockchain applications, Ethereum researchers have already branched Plasma into a variety of specifications to serve different applications and project needs. As discussed, the essence of the framework is that a Plasma Chain must be as secure as the root chain. Beyond that, Plasma designs typically involve exits (user submits transaction history proving ownership of assets with collateral) and subsequent challenge periods, where others, incentivized to claim the exit collateral as a bounty, can challenge such exits by submitting a contrary proof.

On January 3, 2018, Vitalik Buterin, Joseph Poon and David Knott released specifications for a “minimal viable plasma implementation” (commonly, “Plasma MVP”). Essentially, the Plasma MVP specification aims to provide plasma’s basic security properties “in a very simplified way,” such as to enable scalable payments, “though it leans heavily on users being willing to immediately exit as soon as they detect any kind of malfeasance.” While the Plasma MVP is designed for token transfers, it can be adapted for ERC721s and general state transitions and potentially scale to more than 1,000 tps (Ethereum researcher, Karl Floersch has noted that “later versions” of MVP design may scale to “millions” of tps).

On March 9, 2018, Vitalik Buterin introduced “Plasma Cash” at the Ethereum Community Conference, a specification which aims to increases Plasma security and usability with unique identifiers for funds deposited on a plasma chain, essentially turning each deposit into a non fungible “coin” with an independent serial number and transaction history. In other words, each deposit is treated like an indivisible bill, much like the familiar denominations of $10, $20, etc. for physical cash, and users only store data about coins they own.

Among other benefits, this construction allows for simpler fund withdrawals with “much less per-user data checking,” i.e., more compact proofs on a coin’s history by only requiring users to validate for the ones they own and are actively watching (and not entire chain of transactions for all, contra Plasma MVP). On March 14, 2018, Ethereum researcher Karl Floersch released a full specification for a Plasma Cash chain. Plasma researcher, Georgios Konstantopoulos, has also released a comprehensive document covering Plasma Cash topics and research on initial implementations (including gaming use-cases via LOOM Network development).

In June 2018, “More Viable Plasma” (commonly, “MoreVP”) was introduced on ethresear.ch by Kelvin Fichter and Ben Jones, a design which, among other things, seeks to make security and UX improvements to the MVP design by removing confirmation signatures and making withdrawals cheaper.

On November 1, 2018, Quantstamp, a blockchain security company, announced that it had completed a security audit of a Plasma MVP implementation designed by blockchain project, OmiseGO; a similar audit of a MoreVP implementation is also planned as of this response.

Current Plasma designs are not without drawbacks: for example, (i) in the worst case, Plasma MVP requires every plasma chain user to exit within a short period of time (limiting throughput, as number of UTXOs that can be safely withdrawn is also the number of UTXOs that can be safely supported on a Plasma chain); further, (ii) when users withdraw funds from a plasma chain, they’re required to wait for a period of time before those funds become available on the Ethereum root chain.

A number of proposals, however, are designed for these problems, and include protocols for “mass exits” that allow thousands of UTXOs to be exited at the same time, and “fast withdrawals” as a way for users to “sell” their withdrawals in order to avoid waiting.

EVM support on Plasma is an active area of research and discussion. Right now, it is difficult to create a Plasma chain that can run more general smart contracts like Ethereum for the following reasons (as outlined in an August 2018 post by Plasma researcher Kelvin Fichter):
(1) It’s not always clear who gets to move a contract from the Plasma chain to the root chain; 
(2) If anyone can modify the state of the contract, then anyone can block an exit; and 
(3) Validating EVM state changes inside the EVM is hard.

However, a potential (but still highly preliminary) solution known as “Plasma VM” involves breaking smart contracts down to a level where these issues might not matter as much.

Specifically, Plasma VM proposes reframing authority to move a contract from the Plasma chain to the root chain using “mini smart contracts”; in other words, instead of worrying about “who gets to move a contract from the Plasma chain to the root chain,” Plasma VM stipulates that it might be more clear who’s responsible for moving stuff to the root chain if, instead of moving the entire contract, everyone were moving their own “mini smart contracts” that can only be modified by their respective owners.

There are over 100 Plasma-related topics being actively discussed on ethresear.ch, and LearnPlasma.org provides comprehensive summaries of current research and implementations.

### 9. Has a proof of stake consensus mechanism been tested or validated at scale? If so, what lessons or insights can be learned from the experience?

Answer:

### 10. Relative to a proof of work consensus mechanism does proof of stake have particular vulnerabilities, challenges, or features that make it prone to manipulation? In responding consider, for example, that under a proof of stake consensus mechanism, the chance of validating a block may be proportional to staked wealth.

Answer:

### 11. There are reports of disagreements within the Ether community over the proposed transition to a proof of stake consensus model. Could this transition from a proof of work to a proof of stake verification process result in a fragmented or diminished Ether market if the disagreements are not resolved?

Answer:

### 12. What capability does the Ethereum Network have to support the continued development and increasing use of smart contracts?

Answer:

## Governance

### 13. How is the governance of the Ethereum Network similar to and different from the governance of the Bitcoin network?

Answer:

### 14. In light of Ether’s origins as an outgrowth from the Ethereum Classic blockchain, are there potential issues that could make Ether’s underlying blockchain vulnerable to future hard forks or splintering?

Answer:

## Markets, Oversight and Regulation

### 15. Are there protections or impediments that would prevent market participants or other actors from intentionally disrupting the normal function of the Ethereum Network in an attempt to distort or disrupt the Ether market?

Answer:

### 16. What impediments or risks exist to the reliable conversion of Ether to legal tender? How do these impediments or risks impact regulatory considerations for Commission registrants with respect to participating in any transactions in Ether, including the ability to obtain or demonstrate possession or control or otherwise hold Ether as collateral or on behalf of customers?

Answer:

### 17. How would the introduction of derivative contracts on Ether potentially change or modify the incentive structures that underlie a proof of stake consensus model?

Answer:

### 18. Given the evolving nature of the Ether cash markets underlying potential Ether derivative contracts, what are the commercial risk management needs for a derivative contract on Ether?

Answer:

### 19. Please list any potential impacts on Ether and the Ethereum Network that may arise from the listing or trading of derivative contracts on Ether.

Answer:

### 20. Are there any types of trader or intermediary conduct that has occurred in the international Ether derivative markets that raise market risks or challenges and should be monitored closely by trading venues or regulators?

Answer:

### 21. What other factors could impact the Commission’s ability to properly oversee or monitor trading in derivative contracts on Ether as well as the underlying Ether cash markets?

Answer:

### 22. Are there any emerging best practices for monitoring the Ethereum Network and public blockchains more broadly?

Answer:

## Cyber Security and Custody

### 23. Are there security issues peculiar to the Ethereum Network or Ethereum- supported smart contracts that need to be addressed?

Answer:

### 24. Are there any best practices for the construction and security of Ethereum wallets, including, but not limited to, the number of keys required to sign a transaction and how access to the keys should be segregated?

Answer:

### 25. Are there any best practices for conducting an independent audit of Ether deposits?

Answer:
