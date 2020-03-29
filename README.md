# FCO2ken

## Contracts

FCO2ken has two core Solidity contracts: the ledger contract. which tracks the minting and retiring of FCO2kens (`fco2ken.sol`) and a storage contract (`fco2kenData.sol`), which holds - most importantly - an ownable FCO2ken price value.

### fco2ken.sol

- `mint(string memory ipfsHash, uint256 amountTokens) public onlyOwner()`: allows the owner to create new CO2kens
- `withdraw() public onlyOwner()`: allows the owner to withdraw monies received to the contract
- `offsetCarbon(uint256 payment) public`: allows anyone to pay a dollar-denominated value into the contract to offset carbon
- `offsetCarbonTons(uint256 tons) public`: allows anyone to pay a ton CO2 denominated value into the contract to offset carbon

### fco2kenData.sol

- `setCO2kenPrice(uint256 _co2kenPrice) public onlyOwner()`: allows the owner to set the price of CO2kens

### polluter.sol

Contains the `Green` contract that can be inherited by others to make available the `offset()` modifier.

- `offset(uint256 offsetThreshold)`: a modifier that accepts a threshold parameter to offset all accumulated carbon emissions of the function once it is crossed (batching)

Also contains the `Polluter` contract which `is Green` to demonstrate modifier functionality.

### Contract Addresses

**Rinkeby**

FCO2kenData - *Add rinkeby addy later*

FCO2ken (for demo) - *add later addy for demo contract*

Polluter (is Green) - *add later addy for demo contract*

WEENUS (test ERC20) - collect test WEENUS by visiting https://rinkeby.etherscan.io/token/<CONTRACT_ADDRESS_ON_RINKEBY>#writeContract connecting web3 wallet and write to `drip()`

## The Graph 

### Setup and Deployment
To setup and deploy subgraph run the following commands:

>npm run codegen

>graph auth https://api.thegraph.com/deploy/ GRAPH_AUTH_TOKEN

>graph deploy --debug --node https://api.thegraph.com/deploy/ --ipfs https://api.thegraph.com/ipfs/ benesjan/CO2ken

### Requesting data
The Graph uses GraphQL API.
To get a balance of purchased CO2kens for address "0xaa81ca5483020798f1a8834e1fb227e1c02c8ede"  run:
>curl -X POST -H "Content-Type: application/json" --data '{ "query": "{ userBalances(id: \"0xaa81ca5483020798f1a8834e1fb227e1c02c8ede\") { balance } }" }' https://api.thegraph.com/subgraphs/name/benesjan/co2ken
