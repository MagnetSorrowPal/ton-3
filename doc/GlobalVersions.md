# Global versions
Global version is a parameter specified in `ConfigParam 8` ([block.tlb#593](https://github.com/newton-blockchain/ton/blob/master/crypto/block/block.tlb#L593)).
Various features are enabled depending on the global version.

## Version 4

### New TVM instructions
* `PREVMCBLOCKS`, `PREVKEYBLOCK`
* `HASHSTART`, `HASHEND`, `HASHENDST`, `HASHINFO`, `HASHAPPU`, `HASHAPPI`, `HASHAPPS`, `HASHAPPB`
* `ECRECOVER`
* `SENDMSG`
* `SETBOUNCEONACTIONPHASEFAIL`

### c7 tuple
**c7** tuple extended from 10 to 14 elements:
* **10**: code of the smart contract.
* **11**: value of the incoming message.
* **12**: fees collected in the storage phase.
* **13**: information about previous blocks.

### Action phase
* If "send message" action fails, the account is required to pay for processing cells of the message.
* Optional bounce on action phase failure (enabled by `SETBOUNCEONACTIOINPHASEFAIL`).