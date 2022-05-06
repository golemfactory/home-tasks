# SIMPLE AUCTION

Your task is to implement a simple auction system using blockchain technology. NFT owners should be able to put their NFT on an auction where other users will be bidding for them with GLMs.

Please implement a smart contract with following capabilities:

1. **StartAuction**

   Can be called by any address. Initializes auction of NFT owned by caller.

   _Suggested params:_

   - NFT implementing EIP 721
   - minimum amount required to complete the auction
   - block number indicating when the auction will finish

   \
   One address can start only one auction at the time.

1. **CancelAuction**

   Finishes the auction without completing transfer. If NFT's ownership was moved to the auction contract it should be returned to it's owner. 

   Can be called only if there are no bids.

1. **CompleteAuction**

   Can be called only after the block number defined in StartAuction has already been mined.

   If maximum bid is lower than minimum amount defined in StartAuction, NFT is returned to owner and the auction is closed.

   Otherwise NFT should be transferred to the highest bidder and his bid should be transferred to auction owner.

1. **Bid**

   Sets the current bid value for given address in GLM. (total bid amount should be locked in contract. If given address outbids it’s previous bid then additional GLMs should be added to contract’s treasury)

   Current bid needs to be higher than the previous bid.

   Cannot bid after auction is finished (after block with particular number is mined).

1. **Pass**

   Can be called only if someone else outbids the caller's previous bid. Returns locked funds to the caller's address.

1. **Claim**

   Can be called only if the auction is finished. Returns locked funds to the caller's address.

The contract should be implemented using Solidity. Using additional libraries like OpenZeppelin is absolutely ok.

# Deployment

Deploy smart contract on Polygon’s Mumbai. Provide simple application (js, python, c#, java, rust …) demonstrating interactions with the smart contract.

Please upload source code of the smart contract and aforementioned application to a your github account into a separate repository.

# Demo

Please provide readme file with instructions how your code can be run and tested.

Attach additional file with description of several test scenarios.

\
_Optional_

If that's possible please record a short demonstration video showcasing your code and it's usage.

# Miscellaneous

_GLM token on Mumbai testnet_
https://mumbai.polygonscan.com/token/0x2036807B0B3aaf5b1858EE822D0e111fDdac7018
