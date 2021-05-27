# Blockchain-with-wallet-Homework

### Dependencies List
* PHP must be installed on your operating system.
* bit Python Bitcoin library.
* web3.py Python Ethereum library.

### Installations
* You will need to clone the hd-wallet-derive tool.
* You will need the Blockchain_TX_Installation
* You will need the go-etheruem-tools

## Description
This project uses the HD-wallet-derive tool to allow for fast derivation and convenient transactions for the supported coins (Only BTC-TEST and ETH). 

    1. The function wallet.py/derive_wallets() allows you to generate a custom number of keys all linked to a single mnemonic.
    
    2. It currently points to an enviromental file called keys.env where you can find the test mnemonic used for this project.
    
    3. The function wallet.py/priv_key_to_account converts the private key (which can be accessed by referring to the coins           dictionary created after the derive_wallets function) to an account object that can interact directly with the Blockchain and send transactions. This function needs the following parameters:
        *coin -- the coin type (defined in constants.py).
        *priv_key -- the privkey string will be passed through here.
        
    4. The functions create_tx and send_tx work together to first generate the object for an unsigned transaction (in create_tx) and then signs it with the account object's private key to make the transaction valid. Both of these return the raw_tx. These functions need the following parameters: 
        *coin -- the coin type (defined in constants.py).
        *account -- the account object from priv_key_to_account.
        *to -- the recipient address.
        *amount -- the amount of the coin to send.
       
 
## Commands to Transact

### BTCTEST Transaction
To execute a transaction after you have generated the account object, call the send_tx function as follows: send_tx(coins[BTCTEST][0][3], BTCTEST, *recipient's address*, *amount*)

Once the transaction has been executed, use a block explorer to verify that the transaction went through.

### ETH
To execute a transaction after you have generated the account object, call the send_tx function as follows: send_tx(coins[ETH][0][3], ETH, *recipient's address*, *amount*)

Once the transaction has been executed, use the TxStatus to verify that the transaction went through.

