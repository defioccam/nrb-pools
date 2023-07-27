# Draft Proposal: Expanding Rocketpool's Market Reach with No-RPL-Bonded Megapools

---

We propose changes to the Rocketpool protocol aimed at expanding the total addressable market (TAM) of Rocketpool Node Operators. In addition to the options they currently have, Node Operators would be able to
- Lock RPL tokens in a vault for fees
- Run a new type of pool that trades off RPL price volatility for borrowed-ETH rewards


### Some Personal Background
As a Node Operator with an RPL collateral ratio under 10%, I won't be starting new minipools  despite having idle ETH I'd like to stake. Going into rETH is not an option for me as the tax liabilities triggered would dwarf the current (low) APR. I've looked into starting new validators as a solo staker, but was put off by the nitty-gritty of doing so. And there's no way I'm buying more RPL after seeing the volatility RPL exhibits.

The current UX is unfriendly to those of us who aren't interested in speculating on RPL and just want to stake their ETH using Rocketpool's tried-and-true framework. Truth is, with [Megapools](https://gist.github.com/kanewallmann/60575b2ac0008a53f517e1932a66d8ea) set to vastly improve the cost-effectiveness of staking incremental ETH, I'd willingly forego a large portion of my 14-15% cut of borrowed-ETH rewards if doing so would shield me from RPL volatility while allowing me to stake my idle ETH with Rocketpool's best-in-class.

- Software
- Dashboards
- Smoothing-pool
- Rescue-node
- Community
- Lindy

I think there are others like me in the node operator market. See for example,

- https://dao.rocketpool.net/t/as-the-price-of-rpl-fell-some-problems-were-exposed/1967/8
- https://dao.rocketpool.net/t/as-the-price-of-rpl-fell-some-problems-were-exposed/1967/9


How can Rocketpool expand its TAM and capture our business?

## Proposal Outline:
1. **Establish an RPL Vault**: RPL holders have the option to lock RPL tokens in a vault.
1. **Establish a No-RPL-Bonded (NRB) Megapool**: As the name suggests, this megapools does not require RPL to be bonded.
4. **NRB-pool queue**: When an NRB pool is started, a chit representing the intended amount of borrowed-ETH goes into a queue. The queue advances at the rate of 1000 ETH per day. Once an NRB's chit has cleared the queue, the NRB pool's bonded-ETH is moved to the minipool queue (though it probably won't be called that once megapools are a thing)  
4. **Vault Cut of Borrowed-ETH rewards**: 9% of an NRB megapool's borrowed-ETH rewards goes to the vault as a Vault Fee.
4. **NRB Operator Cut of Borrowed-ETH rewards**: NRB megapool operators receive 5% of borrowed-ETH rewards.
10. **Vault Fee is sent to the rETH contract**: The vault fee is simply added on to the ETH sent to the rETH contract whenever the operator takes a distribution from the smoothing pool, their fee distributor, or their NRB megapool.
12. **Vault Fee is Claimed as rETH**: Depositors into the vault can claim their share of the vault fee as rETH at the current protocol rETH/ETH exchange rate at the end of each epoch.
5. **Vault RPL is Ineligible to Vote**: RPL locked in the Vault is ineligible to vote on formal proposals.


## Notes:

1. The current tokenomics do not offer a clean separation of roles---one needs to either be lucky or be an RPL tokenomics/market-dynamics maven to profitably operate a Rocketpool node. This proposal creates space within the Rocketpool umbrella for a pure play node operator role that's competitive with solo-staking. The provision of such a role will expand Rocketpool's TAM.
2. Because NRB operators do not bond RPL, there's no need for RPL inflation to compensate for decreased capital efficiency. Indeed, NRB pools can play a central role in Rocketpool's path to sustainable inflation.
3. A 9% Fee on borrowed-ETH rewards is roughly double the take rate of LDO holders. So, theoretically speaking, if NRB megapools were the only minipools available, RPL could sustain the same marketcap as LDO with roughly half the amount of borrowed-ETH.
4. The 5% Node Operator cut on borrowed-ETH is intended to nudge would-be solo-stakers to stake with Rocketpool.

## Open Questions:
- Do the Vault and Node operator fees (9% and 5% of borrowed-ETH respectively) seem right? Ideally these rates would be adjustable by the pDAO and the adjustments would apply to all NRB minipools (not just new ones). Unfortunately, making this so poses a technical challenge: When borrowed-eth rewards are distributed, how do we ensure that borrowed-ETH rewards are taxed at the fee rate prevalent when the rewards accrued?

## Next Steps:

1. **Community Discussion**: We encourage the Rocketpool community to review this proposal and provide feedback.

2. **Technical Analysis**: A technical feasibility study is needed to understand the potential impacts and complexities of the proposed changes.

3. **Formal Proposal**: If the community and technical analysis support the proposal, it can move to the formal proposal stage for voting.5. **Locked RPL is Eligible to Vote**: RPL locked in the Vault is eligible to vote on a formal proposal (e.g. on Snapshot) if the RPL
    - Was locked at the time the proposal was posted
    - Will remain locked for 2 weeks past the end of voting

