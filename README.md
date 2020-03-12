# CO2ken

## Contract Addresses

**Rinkeby**

CO2kenData - 0x127AE08f45d687dA7887ceA369F2f4D95cb9baf2

CO2ken (for demo) - 0x6a1B0C693DD4AA99bA8E93247AA221Fb30525Cfe

Polluter (is Green) - 0x57AaFA7eA3D66e2C9540d455BDBe093De9DB6bf4

WEENUS (test ERC20) - collect test WEENUS by visiting https://rinkeby.etherscan.io/token/0xaff4481d10270f50f203e0763e2597776068cbc5#writeContract connecting web3 wallet and write to `drip()`

## Subraph setup and deployment
To setup and deploy subgraph run the following commands:

>npm run codegen

>graph auth https://api.thegraph.com/deploy/ GRAPH_AUTH_TOKEN

>graph deploy --debug --node https://api.thegraph.com/deploy/ --ipfs https://api.thegraph.com/ipfs/ benesjan/CO2ken