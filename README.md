# E-Voting System Using Blockchain Technology

A decentralised voting system based on [Ethereum blockchain](https://ethereum.org/dapps/) technology.


## ABOUT
A blockchain-based voting system that preserves voter privacy and increases accessibility, while keeping the voting system transparent, secure, and cost-effective. The system implements a voting framework that utilizes ethereum’s blockchain and smart contracts to achieve voter administration and auditable voting records. The implementation was deployed on ethereum’s test network to demonstrate usability, scalability, and efficiency.


## System Workflow

A brief explanation on the basic workflow of the application.

- Admin will create a voting instance by launching/deploying the system in a blockchain network (EVM), then create an election instance and start the election with the details of the election filled in (including candidates for voters to vote).
- Then the likely voters connect to the same blockchain network register to become a voter. Once the users successfully register, their respective details are sent/displayed in the admins' panel (i.e. verification page).
- The admin then will check if the registration information (blockchain account address, name, and phone number) is valid and matches with his record. If yes, then the admin approves the registered user making them eligible to take part and cast their respective vote in the election.
- The registered user (voter) following the approval from the admin casts their vote to the candidate of interest (from the voting page).
- After some time, depending on the scale of the election the admin ends the election. As that happens the voting is closed and the results are displayed announcing the winner at the top of the results page.


### Requirements

- [Node.js](https://nodejs.org)
- [Truffle](https://www.trufflesuite.com/truffle)
- [Ganache](https://github.com/trufflesuite/ganache-cli) (Cli)
- [Metamask](https://metamask.io/) (Browser Extension)


#### Getting the requirements

1. Download and install **NodeJS**

   Download and install NodeJS from [here](https://nodejs.org/en/download/ "Go to official NodeJS download page.").

1. Install **truffle** and **ganache-cli** using node packager manager (npm)

   ```shell
   npm install -g truffle
   npm install -g ganache-cli

1. Install **metamask** browser extension

   Download and install metamask from [here](https://metamask.io/download "Go to official metamask download page.").


## Set Up Instructions

Open ganache and select quick start ethereum.

Open your browser and configure metamask. Create a wallet and store your```Secret Recovery Phrase``` in a safe place.


#### Connecting metamask and ganache
1. In metamask, go to settings > networks > add network. You can also get to this by clicking the metamask extension pinned on your browser > clicking the profile picture > settings > networks > add network
2. Give your network any name of choice. 
3. For New RPC URL go to ganache where you'll copy the RPC server url and paste in Metamask. 
4. Chain ID for ganache is 1337. 
5. You can name currency symbol as "ETH" and save. 


#### Importing an account from ganache to metamask
1. Open ganache and select show keys on any account. The show keys button is the key icon.
2. Copy the private key and click done.
3. Open the metamask menu which can be accessed by clicking the profile picture and select import account.
4. Paste the private key copied from ganache and click import.


### Configuring the project for development

1. Clone this repository

   ```shell
   git clone https://github.com/GoddumuriRaju/dVoting.git
   cd dVoting
   ```

2. Run local Ethereum blockchain

   ```shell
   ganache-cli
   ```
  
   > Note: Do not close `ganache-cli` (the blockchain network needs to be running all the time)

3. Configure metamask on the browser with the following details

   New RPC URL: `http://127.0.0.1:8545` *(use `port: 7545` for **ganache gui**, update it in the file:`truffle-config.js` as well)*

   Chain ID: `1337`

4. Import account(s) using private keys from ganache-cli to the metamask extension on the browser

5. Deploy smart contract to the (local) blockchain network (i.e ganache-cli)

   ```shell
   # on the dVoting directory
   truffle migrate
   ```

   > Note: Use `truffle migrate --reset` for re-deployments

6. Launch the development server (frontend)

   ```shell
   cd client
   npm install
   npm start
   ```
The project will open in the browser and metamask will ask you to select an account. Select the account we had imported earlier.
