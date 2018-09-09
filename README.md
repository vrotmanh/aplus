# Want to see what we've built through the eyes of our end-users? Check out the a+plus marketplace: [Check Aplus](https://aplus-frontend.herokuapp.com/)

# A+plus
A+plus: work smarter. A decentralized course note marketplace, curated by experts, run by smart contracts. 

A+plus is a decentralized course note marketplace that allows university students to make their notes available for sale. Others may purchase those notes, with payment settled via smart contract (SC). A token curated registry of experts (the “A+plus Expert List”), as well as other users, provide attestations to reflect the quality and credibility of marketplace-listed course notes that they feel are particularly useful and valuable.   

# A+plus DDEX

[Click here to check the repo](https://github.com/vrotmanh/aplus-ddex)
This repo contains the smart contracts of the Decentralized Exchange Market and the ERC20 Token
+ [AplusEscrows](https://github.com/vrotmanh/aplus-ddex/blob/master/contracts/AplusEscrows.sol)
[Contract in Ropsten](https://ropsten.etherscan.io/address/0x1f1298f6b99034fbee1db00ddadd06258bb6b368)

+ [AplusListings](https://github.com/vrotmanh/aplus-ddex/blob/master/contracts/AplusListings.sol)
[Contract in Ropsten](https://ropsten.etherscan.io/address/0xae73ddac98cb901defe802904172495396b486ce)

+ [AplusFaucet](https://github.com/vrotmanh/aplus-ddex/blob/master/contracts/faucetContracts/AplusFaucet.sol)
[Contract in Ropsten](https://ropsten.etherscan.io/address/0xA90C8007Caf00fC9bf8178F25e40F6b48E26DCCA)


# A+plus UI

[Click here to check the repo](https://github.com/passabilities/aplus-frontend)
This repo contains the UI code. Which is a rect + redux frontend app that integrates the Linnia Protocol to store and manage data plus the interaction with the TCR, A+plus DDEX and A+plus ERC-20 Token.

# A+plus TCR and Token

For the TCR we used a common TCR repo and deploy, the code is here
[Click here to check the repo](https://github.com/skmgoldin/tcr)

+ Aplus ERC-20 Token
[Contract in Ropsten](https://ropsten.etherscan.io/address/0xA90C8007Caf00fC9bf8178F25e40F6b48E26DCCA)

+ TCR
[Contract in Ropsten](https://ropsten.etherscan.io/address/0xb9d7152FAF3685732d5D67baDc4fC58af0E65a81)

# A+plus User Experience Explanation

Alice is a very good student and has great notes. She also would love to earn some money selling them.
Alice goes to A+plus website, upload her notes to the Linnia Protocol (an open-source Decentralized Data Protocol) and list them to sell in the A+plus DDEX. She choose a price for which she is willing to sell her notes, and then a Listing was created in the AplusListings SC.

Bob is very behind for his exam and is desperate to find good notes to save his ass. He goes to A+plus website and found notes for a very affordable price that are validates buy many experts. (These happen to be Alice's Notes, but Bob doesn't know it's her)

A+plus contains a TCR list of experts. People with subject matter expertise that can verify that notes are good notes of different subjects. This attestations also occur using the Linnia Protocol. 

Bob decides to purchase this set of notes.
He sends the ETH, which creates an Escrow in the AplusEscrows SC. This way the Escrow SC keep the money until the seller send the actual note.

Now Alice receives a notification that smeone wants to acquire her notes.
She enters A+plus website and approves the transaction. In order to do that, the frontend retrieves the original notes from IPFS and asks Alice to use her Linnia Private Encryption Key in order to decrypt the data.

After that, using the Linnia Public Encryption Key that Bob provides the notes are encrypted again and stored in Linnia.

Now Alice can claim the money from the AplusEscrows SC which will check that the notes where already sent using the LinniaPermissions contract.

Bob can go and decrypt the notes using his Linnia Encryption Keys. After that he receives some Aplus Tokens.
With this tokens Bob can vote in the TCR if the notes where good or bad. This way the TCR can remove someone from the list if they attestate for bad notes.
