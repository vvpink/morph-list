# morph-token list
 <b>About Token list</b>

The token list is a list of tokens managed by the maintainers of this repo. These tokens have been officially added to the Morph bridge. 
It's open for anyone to add a token to the list. However, it's important to understand that by adding a token to this list, we're not endorsing or vouching for the token in any way. We don't assess the quality, value, or the investment potential of these tokens.

<b>Review process and merge criteria</b>
Process overview
1. To include your token in the list, follow the steps provided below to create a PR.
2. Once a reviewer gives their approval to your PR, it will be merged automatically.


Note: The standard bridge does not support certain ERC-20 configurations: 
- Fee on transfer tokens
Some tokens take a transfer fee (e.g. STA, PAXG), some do not currently charge a fee but may do so in the future (e.g. USDT, USDC).

- Tokens that modify balances without emitting a Transfer event
Some tokens can change their balances in ways that don't trigger a "Transfer" event. This can happen with tokens like Ampleforth that rebase, tokens like Compound that airdrop governance tokens, or tokens that can be minted or burned.
Some smart contract systems store balance information for tokens (like Balancer and Uniswap-V2), and if the token's balances change without notice, these systems may work with outdated information.
In the case of Ampleforth, certain Balancer and Uniswap pools are designed to ensure that their stored balances get updated automatically when a rebase happens.
Final approval
To get your token approved and listed on the bridge UI, it has to follow a specific schema and pass our manual review.

<b>Adding a token to the list</b>

[Create a folder for your token]
Inside the data folder, create a new folder with the same name as your token symbol. For example, if your token symbol is "ETH," make a folder named "ETH."
Add a logo to your folder
Add a logo to the data folder you just created. It must be in SVG format and named logo.svg. Ensure the logo is at least 200x200 points (pt), but it's better if it's 256x256 points.

[Create a data file]
Add a file to your folder called data.json with the following format:
{
  "name": "Bridge Token List",
  "logoURI": "https://Morph.network/logo/bridge.png",
  "keywords": [
    "Morph",
    "bridge",
    "token"
  ],
  "tags": {
    "stablecoin": {
      "name": "stablecoin",
      "description": "Tokens that are fixed to an external asset, e.g. the US dollar"
    },
    "ethereum": {
      "name": "ethereum",
      "description": "Asset bridged from ethereum"
    }
  },
  "timestamp": "2023-09-21T08:49:46Z",
  "tokens": [
    {
      "chainId": "900",
      "address": "0x0000000000000000000000000000000000000000",
      "symbol": "ETH",
      "name": "Ethereum Token",
      "decimals": 18,
      "logoURI": "https://Morph.network/logo/eth_logo.png"
    },
    {
      "chainId": "53077",
      "address": "0xDeadDeAddeAddEAddeadDEaDDEAdDeaDDeAD0000",
      "symbol": "ETH",
      "name": "Ethereum Token",
      "decimals": 18,
      "logoURI": "https://Morph.network/logo/eth_logo.png"
    }
  ],
  "version": {
    "major": 0,
    "minor": 0,
    "patch": 0
  }
}

<b>Approve process</b>

[Create a pull request]
Start by creating a pull request (PR) with the changes you've made. For each token you want to add, please create a separate PR. Each PR should contain two new files within a new folder.  If you want to add multiple tokens, please open different PRs for each token.

[Wait for  automatical update]
Once your PR is approved and merged, the token list will update automatically to include your token. Please do NOT update the token list (Morph.tokenlist.json) directly. All token list updates will be handled automatically when PRs are merged into the master branch.  

[Note the update schedule]
Keep in mind that the bridge user interface (UI) is refreshed approximately every workday. So, it might take a day or up to three days if there's an update on Friday before your token becomes available there.