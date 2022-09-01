### Use the provider to display token details

### Determine to use provider or signer, for readonly provider

### Contract Instance takes in , "contract address, abi, provider or signer"

### To view contract details - ContractInstance.FunctionName(args)

for example
function nameOfOwner() public view returns(address) {return OwnerAddress}

const nameOfOwner = await ContractInstance.nameOfOwner()

### UI Updates

####  Display Token Details
- Set the tokenTemplate as a function to receive dynamic data - tokenTemplate
- Create a function to get the data from the blockchain - getTokenDetails
- Create a global init Function to set the result of getTokenDetails function to the tokenTemplate;
- Set the innerHTML of tokensDetails(inside html file) to the result of tokenTemplate

#### Send Token To another Wallet

- Connect to metamask - with connectWallet() function
- Call the sendToken Function
    this instantiate the contract interface wit the signer
    - get the decimals of the token by calling getDecimals function
    - convert the amt to be send to a bigNumber format - with new etherjs.utils.parseUnits(amt, decimal)
    - send the send transaction with the transfer method - contract.transfer(address, parseUnit)
    - wait for the transaction to mine with the .wait() on the last async operation
- update the ui accordingly.
 
