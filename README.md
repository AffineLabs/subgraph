Forked from: https://github.com/mitosis-org/evm-linea-subgraph

## How to Add a New Contract

- Add details in `subgraph.yaml`. Follow the existing contracts.
- Add the contract ABI in `abis` folder if needed. Normally, it's not needed for ERC20 tokens.
- Then run the commands below.

## How to Run

- Install dependencies: `yarn install`
- Generate types: `yarn codegen`
- Build: `yarn build`

## How to Deploy

- First install Goldsky's CLI and Log in.
- Run `goldsky subgraph deploy affine-subgraph/<version> --path .` Make sure to add a new version
- Finally update the `prod` tag with the new version: https://docs.goldsky.com/subgraphs/tags

More: https://docs.goldsky.com/subgraphs/deploying-subgraphs
