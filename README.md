 ░██████╗░█████╗░███████╗███████╗████████╗░█████╗░██╗░░██╗███████╗███╗░░██
 ██╔════╝██╔══██╗██╔════╝██╔════╝╚══██╔══╝██╔══██╗██║░██╔╝██╔════╝████╗░██
 ╚█████╗░███████║█████╗░░█████╗░░░░░██║░░░██║░░██║█████═╝░█████╗░░██╔██╗██
 ░╚═══██╗██╔══██║██╔══╝░░██╔══╝░░░░░██║░░░██║░░██║██╔═██╗░██╔══╝░░██║╚████
 ██████╔╝██║░░██║██║░░░░░███████╗░░░██║░░░╚█████╔╝██║░╚██╗███████╗██║░╚███
 ╚═════╝░╚═╝░░╚═╝╚═╝░░░░░╚══════╝░░░╚═╝░░░░╚════╝░╚═╝░░╚═╝╚══════╝╚═╝░░╚══

![GitHub version](https://img.shields.io/github/v/release/solidity-guru/safetoken?include_prereleases)
![GitHub release data](https://img.shields.io/github/release-date-pre/solidity-guru/safetoken)
![Github commits](https://img.shields.io/github/commits-since/solidity-guru/safetoken/v1.0-beta?include_prereleases)
![GitHub stars](https://img.shields.io/github/stars/solidity-guru/safetoken)
[![GitHub Issues](https://img.shields.io/github/issues/solidity-guru/safetoken)](https://github.com/solidity-guru/safetoken/issues)
![Github](https://img.shields.io/github/downloads/solidity-guru/safetoken/total?style=flat)
[![License](https://img.shields.io/github/license/solidity-guru/safetoken?style=flat)](https://opensource.org/licenses/MIT)
[![Discord](https://img.shields.io/discord/830637298109644820)](https://discord.gg/cUNrn8Urdw)

# Safetoken

This is a rewrite of Safemoon in the hope to:

- make it easier to change the tokenomics
- make it easier to maintain the code and develop it further
- remove redundant code
- fix some of the issues reported in the Safemoon [audit](https://www.certik.org/projects/safemoon)

Visit our [discord](https://discord.gg/zn86MDCQcM)

## Features

- Easy (transaction) fees management 
- Correctly implemented reflect finance (rfi) (with the right wallets excluded from rewards by default)
- Correctly implemented burn
- Address Safemoon audit issues (SSL-01, 02, 03, 05, 06, 11, 12)
- In-code separation of concerns
- Improved code readability + added comments

## Examples

Tokenomics with 5% to liquidity, 3% redistribution and 2% to charity

```solidity
address internal charityAddress = <wallet address>;

function _addFees() private {
    _addFee(FeeType.Rfi, 30, address(this) ); 
    _addFee(FeeType.Liquidity, 50, address(this) );
    _addFee(FeeType.External, 20, charityAddress );   
}
```

## Authors

ex. 0f0crypto

## Version History

 * v1.0beta
    * Initial release


## License

This project is licensed under the MIT License - see the LICENSE file for details
