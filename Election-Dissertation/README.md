
Please follow the steps to set up the dissertation project.

## Dependencies
Make sure that the following dependecies are installed. 
Metamask  
NodeJS 
Ganache  
Truffle 
Visual Studio (optional)

## Step 1. Please copy the project URL.

`open this link - https://github.com/KapilAminbhavi93/Dissertation.git`

## Step 2. Please install the following dependencies on either Visual Studio Terminal or Windows Terminal. If Linux is an option, then diretly install the dependencies in the terminal.

$ cd election
$ npm install

Make sure that the NodeJS version and the Truffle version on your system is the same. 
To avoid problems, I am attaching the code to fix this problem. 

compilers: {
    solc: {
        version: "0.4.24" // ex:  "0.4.20". (Default: Truffle's installed solc)
  }
  } 

the above code has to be added in the `truffle-config.js` file or `truffle.js`. It has to be added at the end.

## Step 3. Please Open Ganache 
Open the Ganache file after installation. 
Click on Quickstart Ethereum.
You will see the accounts provided by Ganache with fake Ethers. 
This is the local blockchain running for the project.
Remember the port number on which it is running.(RPC server section)


## Step 4. Election.sol file must be deployed.

Please enter the following command on the Terminal

`$ truffle migrate --reset`

It is necessary to migrate the smart contract if you accidently close Ganache or restart Ganache.

Next step is to migrate the contract again.

`$ truffle migrate`

Next step is to create an instance of the smart contract and the Web3. To do this, use the following commands

`$ truffle console`
`$ web3.eth.getAccounts().then(function(acc){ accounts = acc }) `
`$ Election.deployed().then(function(i){ app = i })`
`$ app.vote(1, { from: accounts[0] })`

## Step 5. Set up MetaMask

Create account on MetaMask using a password.
Copy and Paste the seed phrase in a text file.(It is very important for account retrieval)
Once Metamask is set up, create the network which will connect to the local blockchain.

Click on add network
Network Name : development
New rpc url : copy the one from the Ganache RPC server
Chain ID: 5777 (but check Ganache)
Currency Symbol : $
Click save.

The next step is to import account
Go to Ganache- click on the key symbol of any of the accounts. 
Copy the private key of that particular account and paste it in Metamask window of import account.
Account will be imported successfully.

## Step 6. Try running the Client-side application.
Please run the following command in the terminal.

`$ npm run dev`

Your browser will open the webpage with address http://localhost:3000

This will be the client-side application to vote. 
Click on any of the candidates and trying voting.
A metamask popup window will come to confirm the transaction
Click yes.
The vote will be submitted and the vote count will be seen.

To vote from another account, repeat step 5 process of importing an account and perform the same thing. 

