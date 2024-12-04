# Coop Factory

The Coop Factory is a factory contract for creating Coop contracts.

## Deployments

## Deployed Contracts (Base Sepolia)

- Coop Implementation: `0xe5399ccb7c599210e7c46de1b01d6f06bf350f20`
- CoopFactoryImpl: `0x20be2931f6ca9115d2ccc4592eb58f9c8c1c559c`
- CoopFactory Proxy: `0xd16653637e739480c9b387c5cdd8d5ff6935c97c`

## Usage

1. Deploy the Coop implementation contract using the following command:

   ```
   forge script script/DeployCoopFactory.s.sol:DeployCoopFactory --rpc-url $RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY -vvvv
   ```

   Replace `RPC_URL`, `PRIVATE_KEY`, and `ETHERSCAN_API_KEY` with your actual values.

2. Deploy the Coop contract, passing the address of the CoopFactoryImpl as the `_logic` parameter.
3. For each 1155 token sale, call `setSaleV2()` with the appropriate parameters.
4. Users can mint tokens using the `mint()` function during the sale period.
5. After the sale ends and meets conditions, call `launchMarket()` to enable secondary trading.

## Important Functions

- `deploy()`: Set up a new memecoin.
- `buy()`: Allow users to buy tokens during the sale.
- `sell()`: Allow users to sell tokens during the sale.

For detailed information on function parameters and usage, please refer to the contract documentation.

## Contract Structure

- `CoopFactory.sol`: The main implementation contract containing all the logic for the Coop factory.
- `Coop.sol`: A proxy contract that delegates calls to the implementation contract, allowing for upgrades.

For more details on implementation, please refer to the contract source code and comments.
