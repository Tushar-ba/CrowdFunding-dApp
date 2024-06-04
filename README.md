cd client
npm install or npm install force 
After this create a .evn file inside the client folder by doing npm install dotenv then create these fields 
NEXT_PUBLIC_API_BASE_URL = "http://localhost:3000/api"
NEXT_PUBLIC_PROVIDER_URL = "You can get the provider url from the Alchemy api"
NEXT_PUBLIC_CONTRACT_ADDRESS = "this you will get once u deploy the contract"
NEXT_PUBLIC_PRIVATE_KEY = ""

after this cd ..
cd smart-contract
then npm install 
then create a .env file inside the smart-contract folder using the "npm install dotenv"  then create these fields inside that 
ACCOUNT_PRIVATE_KEY=""
PROJECT_ID="this you will get from alchemy api"

make sure your hardhat config file looks like this for the deployment

require("@nomicfoundation/hardhat-toolbox");
require('dotenv').config();

/** @type import('hardhat/config').HardhatUserConfig */
module.exports = {
  solidity: "0.8.19",
  networks: {
    sepolia: {
      url: `https://eth-sepolia.g.alchemy.com/v2/${process.env.PROJECT_ID}`,
      accounts: ['0x' + process.env.ACCOUNT_PRIVATE_KEY]
    }
  }
};




