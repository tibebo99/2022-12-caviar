# Caviar contest details

- Total Prize Pool: \$36,500 USDC
  - HM awards: \$25,500 USDC
  - QA report awards: \$3,000 USDC
  - Gas report awards: \$1,500 USDC
  - Judge + presort awards: \$6,000
  - Scout awards: \$500 USDC
- Join [C4 Discord](https://discord.gg/code4rena) to register
- Submit findings [using the C4 form](https://code4rena.com/contests/2022-12-caviar-contest/submit)
- [Read our guidelines for more details](https://docs.code4rena.com/roles/wardens)
- Starts December 13, 2022 20:00 UTC
- Ends December 20, 2022 20:00 UTC

## C4udit / Publicly Known Issues

The C4audit output for the contest can be found [here](add link to report) within an hour of contest opening.

*Note for C4 wardens: Anything included in the C4udit output is considered a publicly known issue and is ineligible for awards.*

# Caviar

[Caviar](https://goerli.caviar.sh) is a fully on-chain NFT AMM that allows you to trade every NFT in a collection (from floors to superrares). You can also trade fractional amounts of each NFT too.
It's designed with a heavy emphasis on composability, flexibility and usability.

## Index

- [Specification](./docs/SPECIFICATION.md)

- [Testing](./docs/TESTING.md)

- [Security considerations](./docs/SECURITY.md)

## Getting started

```
yarn
forge install
forge test --gas-report
```

## Contracts overview

| Contract           | LOC | Description                                                           |
| ------------------ | --- | --------------------------------------------------------------------- |
| Caviar.sol         | 26  | Factory contract that creates pairs and maintains a registry          |
| Pair.sol           | 212 | Pair contract that contains ERC20 AMM, NFT wrapping and NFT AMM logic |
| LpToken.sol        | 15  | ERC20 token which represents liquidity ownership in pair contracts    |
| SafeERC20Namer.sol | 65  | Helper contract that fetches the name and symbol of an ERC20/ERC721   |

## Deployments

**Goerli: ([demo app](https://goerli.caviar.sh))**

| Contract              | Address                                                                                                                      |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Caviar                | [0x4442fD4a38c6FBe364AdC6FF2CFA9332F0E7D378](https://goerli.etherscan.io/address/0x4442fD4a38c6FBe364AdC6FF2CFA9332F0E7D378) |
| FBAYC                 | [0xC1A308D95344716054d4C078831376FC78c4fd72](https://goerli.etherscan.io/address/0xC1A308D95344716054d4C078831376FC78c4fd72) |
| Pair (Rare FBAYC:ETH) | [0x7033A7A1980e019BA6A2016a14b3CD783e35300a](https://goerli.etherscan.io/address/0x7033A7A1980e019BA6A2016a14b3CD783e35300a) |
| LP Token (FBAYC:ETH)  | [0x96E6B35Cc73070FCDB42Abe5a39BfD7f16c37cFc](https://goerli.etherscan.io/address/0x96E6B35Cc73070FCDB42Abe5a39BfD7f16c37cFc) |


## Scoping Details
```
- If you have a public code repo, please share it here:  https://caviar.sh
- How many contracts are in scope?:   3
- Total SLoC for these contracts?:  250
- How many external imports are there?: 5  
- How many separate interfaces and struct definitions are there for the contracts within scope?:  3
- Does most of your code generally use composition or inheritance?:   Yes
- How many external calls?:   5
- What is the overall line coverage percentage provided by your tests?:  100
- Is there a need to understand a separate part of the codebase / get context in order to audit this part of the protocol?:  false
- Please describe required context:   
- Does it use an oracle?:  false
- Does the token conform to the ERC20 standard?:  Yes
- Are there any novel or unique curve logic or mathematical models?: Nothing novel - using uni v2 style curves
- Does it use a timelock function?:  Yes
- Is it an NFT?: No
- Does it have an AMM?:   Yes
- Is it a fork of a popular project?:   false
- Does it use rollups?:   false
- Is it multi-chain?:  false
- Does it use a side-chain?: false
```
