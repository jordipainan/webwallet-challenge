# Monujo

*Monujo* is the codename for the Vocdoni wallet.

The Vocdoni wallet is a web browser based wallet that allows to sign and send Vocdoni specific transactions and it is also compatible with EVM transactions.

The wallet is build on top of [dvote-js](https://github.com/vocdoni/dvote-js) and its initial purpose is to be integrated and used with the [vocdoni-ui](https://github.com/vocdoni/vocdoni-ui).

A tentative roadmap could be:
- [ ] Support Vocdoni transactions
- [ ] Support EVM transactions
- [ ] Support hardware wallets

### Main ideas

- Do not imagine something like metamask.
- Imagine something integrated in the vocdoni-ui, a npm package than you can import everywhere and can be integrated into any web application.
- For having a visual idea of how will look like for the user, go to [vocdoni.app](https://vocdoni.app) and create an organization/entity. Basically you are creating an ethereum wallet and the metadata of the organization is sent to a gateway that sends it to IPFS, a wallet is created in-memory on the browser (your private key is stored encrypted) using [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) and a backend automatically sends some Gnosis Chain tokens to the same address created. It is like a web2 user profile but it is supercharged with web3 capabilities.
- The idea is to make the usage of the wallet totally transparent to the end user unless some kind of expert mode is enabled.
- Note that this is the case where we are always interacting with Ethereum, but with the Ethless approach the wallet controls an [account](https://github.com/vocdoni/docs/blob/master/src/architecture/services/evm-less-vochain.md) that lives in the Vochain and we will be interacting directly with the the Vochain, still the Ethereum features are important for our own retrocompatibility and for keepeing our attachment to the EVM ecosystem. Vocdoni will always be Ethereum friendly.

## Bootstraping the development

1. [ ] Using the vocdoni.app UI codebase and dvote-js, create a Vochain account within the flow of creating an organization/entity.
2. [ ] In the entity's public page, retrieve the information of the Account: nonce, balance, delegates, infoURI.
3. [ ] In the update entity page, update the description of the entity and update the account infoURI on the vochain via SetAccountInfo transaction.

### Features (Vochain)

- [ ] Get network info (e.g chainID)
- [ ] Create account 
- [ ] Import account
- [ ] Export account
- [ ] Sign message
- [ ] Verify message
- [ ] Lock / Unlock account
- [ ] Send transactions
    - [ ] Get current transaction cost
    - [ ] Ajust the transaction cost
    - [ ] Get/Set account info
    - [ ] Get/Set account delegates
    - [ ] Send tokens
    - [ ] Create faucet payload
    - [ ] Collect faucet tx
    - [ ] Create process
    - [ ] Set process
- [ ] Multi-account support


### Features (Ethereum)

*TBD*

### Useful resources

- [Current wallet used in vocdoni.app](https://github.com/vocdoni/vocdoni-ui/blob/main/hooks/use-wallet.tsx)
