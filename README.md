# bitcoincom-solidity-swap

This repository contains smart-contracts for the swap between token A and token B or
token A to ETH / ETH to token A.


### Process and Testing

The package can be run as a CLI for testing purposes.

🔗 First start a local chain:

```
npm run chain
```

Then run test commands for contract deployment and testing


🚀 This command runs token tests:
```
npm run test-token
```


🌯 This command runs wrapped ether tests:
```
npm run test-wraps
```


🏭 This command runs swap router / swap factory tests:
```
npm run test-swaps
```

### Test coverage

🧪 To generate test-coverage report simply run this command (without starting local chain)

```
npm run test-coverage
```

🧪 expected-latest results:
```
---------------------|----------|----------|----------|----------|----------------|
File                 |  % Stmts | % Branch |  % Funcs |  % Lines |Uncovered Lines |
---------------------|----------|----------|----------|----------|----------------|
 contracts/          |     89.2 |       60 |    87.91 |    89.46 |                |
  IERC20.sol         |      100 |      100 |      100 |      100 |                |
  ISwapsCallee.sol   |      100 |      100 |      100 |      100 |                |
  ISwapsERC20.sol    |      100 |      100 |      100 |      100 |                |
  ISwapsFactory.sol  |      100 |      100 |      100 |      100 |                |
  ISwapsPair.sol     |      100 |      100 |      100 |      100 |                |
  ISwapsRouter.sol   |      100 |      100 |      100 |      100 |                |
  IWETH.sol          |      100 |      100 |      100 |      100 |                |
  SwapsFactory.sol   |    97.81 |       70 |      100 |    99.27 |            226 |
  SwapsHelper.sol    |      100 |      100 |      100 |      100 |                |
  SwapsLibrary.sol   |      100 |       55 |      100 |      100 |                |
  SwapsRouter.sol    |    73.13 |    51.92 |    60.71 |    72.86 |... 9,1074,1090 |
  Token.sol          |      100 |      100 |      100 |      100 |                |
  TransferHelper.sol |      100 |       50 |      100 |      100 |                |
  WrappedEther.sol   |      100 |      100 |      100 |      100 |                |
---------------------|----------|----------|----------|----------|----------------|
All files            |     89.2 |       60 |    87.91 |    89.46 |                |
---------------------|----------|----------|----------|----------|----------------|
```

⛽ expected gas:
```
·--------------------------------------------------------------------------|---------------------------|-------------|----------------------------·
|                   Solc version: 0.8.10+commit.fc410830                   ·  Optimizer enabled: true  ·  Runs: 200  ·  Block limit: 6718946 gas  │
···········································································|···························|·············|·····························
|  Methods                                                                                                                                        │
·················|·························································|·············|·············|·············|··············|··············
|  Contract      ·  Method                                                 ·  Min        ·  Max        ·  Avg        ·  # calls     ·  usd (avg)  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsERC20    ·  approve                                                ·      25721  ·      45233  ·      40756  ·           9  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsERC20    ·  transfer                                               ·      36681  ·      51669  ·      44175  ·           8  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsERC20    ·  transferFrom                                           ·      29180  ·      38139  ·      32170  ·           6  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsFactory  ·  createPair                                             ·     222566  ·     237566  ·     230069  ·           8  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsFactory  ·  setFeeTo                                               ·          -  ·          -  ·      28531  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsFactory  ·  setFeeToSetter                                         ·          -  ·          -  ·      28453  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsPair     ·  skim                                                   ·          -  ·          -  ·      74282  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  addLiquidity                                           ·     155079  ·     246004  ·     184085  ·           9  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  addLiquidityETH                                        ·     152712  ·     243964  ·     196852  ·           5  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  removeLiquidity                                        ·          -  ·          -  ·     158569  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  removeLiquidityETH                                     ·          -  ·          -  ·     182830  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapETHForExactTokens                                  ·          -  ·          -  ·     105658  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapExactETHForTokens                                  ·          -  ·          -  ·     110076  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapExactETHForTokensSupportingFeeOnTransferTokens     ·          -  ·          -  ·     114742  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapExactTokensForETH                                  ·          -  ·          -  ·     116161  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapExactTokensForETHSupportingFeeOnTransferTokens     ·          -  ·          -  ·     130196  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapExactTokensForTokens                               ·          -  ·          -  ·     111779  ·           1  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapExactTokensForTokensSupportingFeeOnTransferTokens  ·          -  ·          -  ·     104193  ·           2  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapTokensForExactETH                                  ·          -  ·          -  ·     128515  ·           1  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  SwapsRouter   ·  swapTokensForExactTokens                               ·          -  ·          -  ·     111806  ·           1  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  Token         ·  approve                                                ·      29394  ·      44394  ·      31894  ·          12  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  Token         ·  transfer                                               ·          -  ·          -  ·      36085  ·           1  ·          -  │
·················|·························································|·············|·············|·············|··············|··············
|  Deployments                                                             ·                                         ·  % of limit  ·             │
···········································································|·············|·············|·············|··············|··············
|  SwapsRouter                                                             ·          -  ·          -  ·    3670611  ·      54.6 %  ·          -  │
·--------------------------------------------------------------------------|-------------|-------------|-------------|--------------|-------------·
```


## Expected Values

💻 expected compiler version: ```0.8.14+commit.80d49f37```

💻 expected optimization option: ```Enabled: 200```


### SwapsFactory
🏭 expected creationCode hash:
```
0xbc30e6e4f811d2866d54f5a98e1e2d651c49affcc40982e1d659f4f48996ab20
```
SmartBCH Mainnet Address:
```
0x16bc2B187D7C7255b647830C05a6283f2B9A3AF8
```

### SwapsRouter
💎 expected creationCode hash:
```
0x2b77192643693a5af772dbb33423a22f5ef1fbb14876deb6520fc7f2dcfa160f
```
SmartBCH Mainnet Address:
```
0xF13541FaD443a4Bf4160B5c0F46aC5c735a908d3
```

### SwapsPair
💰 expected creationCode hash for SwapsPair:
```
0x3dbd765ec1bc309907d0abddbfa282061ea55586b6c9a81d5dbc66ced8644e48
```

### feeToSetter
👑 expected admin/multi-signature address:
```
0x138a09B1822450a2d6cbbf59C72aecbb475b0f5f
```

```
const token0 = "0x6B175474E89094C44Da98b954EedeAC495271d0F";
const token1 = "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2";
const factory = "0xee3E9E46E34a27dC755a63e2849C9913Ee1A06E2";

const initCode = "0x3d602d80600a3d3981f3363d3d373d3d3d363d737290367aa694703220516a35e68e3d339ee7d1935af43d82803e903d91602b57fd5bf3";

const initCodeHash = ethers.utils.solidityKeccak256(
    [
        'bytes'
    ],
    [
        initCode
    ]
);

const salt = ethers.utils.solidityKeccak256(
    [
        'address',
        'address'
    ],
    [
        token0,
        token1
    ],
);

const contractAddress = ethers.utils.getCreate2Address(
    factory,
    salt,
    initCodeHash,
);
```
