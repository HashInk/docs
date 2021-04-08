# docs

## **Hashink**: Connecting Stars and Fans through NFT'd autographs.
https://hashink.app
https://twitter.com/hashinkapp


## ABSTRACT

Ink is a dapp for fans to request and purchase autographs from their stars and allow them to sign and send them digitally by using NFT technology. 


## ROADMAP

### Version 1 (barebones)
* Signer Signup form [email, price, avatar, signature]
* magic.link (?)
* Minimum backend to store celebrity image, their autograph, etc
* Requester metamask connect
* Users can request an autograph.
* Celeb can sign an autograph.
* User can view their autograph's gallery.
* User and celeb payments work through their wallets.
* Requests and celebrities (critical data like price or response time) stored on-chain.
* Should come back to this at some point.

### Version 2 (Replace with version name)
* “Celeb” profiles created manually
* Users can request an autographed photo.
* Celebs and users can pay with FIAT (Circle integration)
* What token are we using? (I thinking using USDC and DAI would be best, otherwise we can consider using something like DePay)
* Search function
* Filtering

### Version 3 (Replace with version name)
* Setup Python bot to ‘@’ signers
* Layer 2 (?)
* User reviews


## ARCHITECTURE

###Technologies

* Smart Contracts: Solidity + HardHat
* Query layer: The Graph
* Frontend: React + TypeScript (Next.js for fullstack capabilities)
  * Backend: When needed, resort to Python
* Framework: flask vs django?
* Database. PostgreSQL
* External Storage: Pinata
* Authentication: Magic
* Hosting: Heroku

### Data Storage
Question: What are we going to store on-chain and off-chain?

### Deployment
Question: Where are we going to deploy our product?

### Environments
Question: Are we going to use different environments and different development branches?

## TECHNICAL (STATE OF THE ART)

* ERC-721
* EIP-2981
* ERC-20
* Cameo
* Nifty.ink

## Royalties

Royalties are tricky because we have to either;

  1) implement our own royalty system and marketplace (current best solution)
  2) implement zora or another protocol’s system
  3) wait for the ERC20-royalty standard to be ready

Existing platforms that have royalties implemented:

* Rarible: <link to github>
* Zora: <link to github>
* Opensea: <link to github>

Existing non-marketplace projects that have royalties implemented are:

*Mintable (https://twitter.com/mintable_app/status/1340494751192137728)
*…? 



## RELEVANT TECHNOLOGY

### NFTs

### Royalties

Currently, a range of marketplaces (Rarible, OpenSea, Zora,...) offer their own system for royalties (where any secondary sale that is made, the creator gets X% back of that sale), although, none of them work on any marketplace outside of their own.
It exists the EIP-2981 (NFT Royalties Standard) which is a standardized way to handle royalty payments for ERC-721 tokens, but it’s only a proposal and it’s not approved yet.

Question: Royalties implementation?

What technical solution are we going to apply to offer payment of royalties on our product?

  1. Develop our own system for royalties. This gives us a lot of flexibility but forces us to develop a marketplace where users can sell their NFTs. It also implies that if the NFTs are sold on other marketplaces, the creators will not receive the royalty.
  2. Implement the EIP-2981 standard in our ERC-721 contract. This also implies developing a marketplace since this standard is not yet supported in any marketplace since it has not been approved. It also has the problem that if the NFT is sold on another marketplace, the creator will not receive the royalty payment.
  3. Perform the mint of the token in another marketplace such as Zora or Rarible. This implies that the token will not be created in our contract. It is also not a cross-marketplace solution.

Question: Do we want to charge a fee on secondary sales?

This decision may affect the previous point. If we want to charge a fee in secondary sales, the solution of performing the mint of the token in another marketplace does not serve us since we will not have control of the transfers.

### Authentication

Question: Do signers need to sign up?

Question: How are we going to verify the authenticity of celebrity accounts?

The idea is for the celebrity to publish their Ethereum address on their official Twitter account. But this process can have security problems if your profile is hacked.

### Payments

Question: What currency are we going to use to pay for the autographs? 

Options: ETH or a stablecoin like USDC. If we use ether, the balance will be stored in our contract. If we use a token, the balance will be stored in the token’s contract. If we use USDC we will be more prepared to integrate with Circle Protocol since it uses USDC to send payments to bank accounts.


## TECHNICAL ISSUES

### IPFS and general technical issues

https://thedefiant.io/do-you-really-own-your-nft-chances-are-you-dont/

### Requests…

Ideally a user should not have to pay funds to request an autograph. Is there no way to escrow the funds? Use an oracle service if we have to (not exactly sure how this would work though). It immediately shuts a lot of consumers out.

### Screen size

Signing an autograph on a phone is hard to personalize given the size of available space...


## UI/UX


## TOKEN MODEL


## USER STORIES

This section defines our User Stories. This collection is going to define our product.

* Celebrity POV
  * A celeb wants to register to sell autographs.
  * A celeb wants to view pending requests.
  * A celeb wants to sign a pending request.
  * A celeb wants to get paid once an autograph is signed.
  * A celeb wants to be notified when a request is created.
  * A celeb wants to update his profile.
* User POV
  * A user wants to register to request autographs.
  * A user wants to see celebrities available to sign with price and response time.
  * A user wants to request an autograph.
  * A user wants to request an autograph with a photo.
  * A user wants to see his pending requests to be signed.
  * A user wants to remove a request and get the money back.
  * A user wants to be notified when a request is signed.
  * A user wants to see his autograph gallery.
  * A user wants to sell an autograph.
