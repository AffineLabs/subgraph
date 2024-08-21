Forked from: https://github.com/mitosis-org/evm-linea-subgraph

## How to Add a New Contract

- Add details in `subgraph.yaml`. Follow the existing contracts. Get inspiration from here: https://github.com/mitosis-org/evm-linea-subgraph/blob/main/subgraph.yaml
- Add the contract ABI in `abis` folder if needed. Normally, it's not needed for ERC20 tokens.
- Then run the commands below.

## How to Run

- Install dependencies: `yarn install`
- Generate types: `yarn codegen`
- Build: `yarn build`

## How to Deploy

- First install Goldsky's CLI and Log in.
  - Install Goldsky CLI: `curl https://goldsky.com | sh`
  - Run `goldsky` and follow the instructions to log in.
- Run `goldsky subgraph deploy affine-subgraph/<version> --path .` **Make sure to add a new version.**
- Finally update the `prod` tag with the new version: https://docs.goldsky.com/subgraphs/tags
  - This way the prod tag will point to the latest version and we won't have to update the subgraph URL in our Linea Integration Repository.
  - Run `goldsky subgraph tag create affine-subgraph/<version> --tag prod` to update the prod tag.

More: https://docs.goldsky.com/subgraphs/deploying-subgraphs

## Our Goldsky Project

https://app.goldsky.com/project_clzblgfi61ub601wncxx3bbit/dashboard/subgraphs

## Our Subgraph

https://api.goldsky.com/api/public/project_clzblgfi61ub601wncxx3bbit/subgraphs/affine-subgraph/prod/gn

## Linea Incentive Program

Check readme file here: https://github.com/delta-hq/l2-lxp-liquidity-reward

We already have our subgraph integrated there. So we normally don't have to do anything there unless we want to whitelist new assets.
In that case you might have to update the `const assetWhitelist = ["ultraETH", "ultraETHs"];` in `adapters/affine/src/index.ts` file and create a PR in the repository.

Finally you might have to submit this form to whitelist the new assets: https://forms.gle/DJ2975hZwhz32t5r6
