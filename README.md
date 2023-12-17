# Final Project for the Solana Bootcamp

In this application we have created a Pokemon Trading Card NFT.

### Step 1: Build the contract
Open a terminal window from the terminal tab above and navigate to the generated directory using the 
command “cd **program**” (the folder name where you have Cargo.toml) and type the command 

**``` cargo build-sbf ```**

### Step 2: Set your config file
If there are no errors, type the command: 

**```solana config set --url devnet```**

This command will set our config file to connect to devnet, where we will deploy.

### Step 3: Get devnet tokens
Deploying a contract will require some tokens, you get devnet tokens using the command

**```solana airdrop 1```**

You can get request as many airdrops as you need, after that you can check your balance with command 

**```solana balance```** 

### Step 4: Build and Deploy the Contract
Once we have the build, from the generated directory, type the following command for deployment

 **```solana program deploy target/deploy/nft_pokemon.so```** 

After completing the deployment, you will get a program ID. 

_Copy and save this program ID so we can configure the client library._

### Step 5: Download Dependencies
In order to run this code, we need to actually install these dependencies in our workspace. 
In order to do that, open a terminal, navigate to the **program_client** directory (which contains package.json), 
and type the command 

**```yarn install```** 

This will install the _node_modules_ dependencies.

### Step 6: Install SPL Token Library
This contract also relies on @solana/spl-token; this package needs to be installed manually by executing 

**```yarn add @solana/spl-token```**

### Step 7: Run app.ts
Now we are ready to actually test our NFT contract. 
Execute the client by typing the following command

**```npx ts-node app.ts <YOUR_PROGRAM_ID>```**

### Step 8: Explore the Output
In your terminal you should see an output similar to the one below.

<img width="811" alt="Screen Shot 2023-12-09 at 4 04 29 PM" src="https://github.com/XxBeyonderxX/Solana-Bootcamp-Final-Project-/blob/main/Screenshot%202023-12-17%20155400.png">
<img width="811" alt="Screen Shot 2023-12-09 at 4 04 29 PM" src="https://github.com/XxBeyonderxX/Solana-Bootcamp-Final-Project-/blob/main/Screenshot%202023-12-17%20155428.png">
<img width="811" alt="Screen Shot 2023-12-09 at 4 04 29 PM" src="https://github.com/XxBeyonderxX/Solana-Bootcamp-Final-Project-/blob/main/Screenshot%202023-12-17%20155445.png">
<p/>

1. After the minting, we will see that we actually have an NFT with a supply of 1. 
It contains a Pokemon Card, which is has an element of fire and from 1989. Notice that mint holds the mint address that is printed in the first line of the output. Also, assocAccount is storing the public key of John Doe ATA. 

2. After transfer, mint is the same, as it should be since the minter of the NFT did not change. Only the current holder is updated which is why the assocAccount is now Jane Doe ATA. 

3. After the burn, mint is still the same but now the assocAccount is undefined, proving that no one can own this NFT. Also now, the supply of our NFT is 0, since we had 1 NFT and we have
burned it in the last function. 


**Congrats 🎉 you have successfully tested our NFT contract in Solana.**





 