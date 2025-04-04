# Hands-On with zkVerify: Wallets, Testnets, and Nodes

# Setting up a wallet
There are currently two recommended wallet options -  Talisman and SubWallet. We will be going ahead and setting up a wallet with Talisman. Talisman provides a secure and user-friendly platform for managing assets, interacting with dApps, and exploring both the Polkadot and Ethereum ecosystems. It also comes with support for a variety of networks, NFT management, and hardware wallets, Talisman presents itself as a holistic wallet solution.

# Follow the instructions below to set up your Talisman wallet:
- Click on https://www.talisman.xyz/ and click on the “Download Wallet” button.
- Next, click on the “Add to Chrome button” to add the wallet extension to your Chrome. Please make sure you are using Chrome for this tutorial.
- Now after adding the wallet, it will prompt you to the new window. Click on the “Get Started” button to continue.
- You will be asked to choose a strong password now. Please set a strong password and click on the “Continue” button. If prompted to agree to privacy policies please click on the “I Agree” button.
- Once you’re done, click on the “New Polkadot Account” button to create a new account.
- You will be asked to give a name to your account. So, give any name to your account. We gave it zkVerify and click on the “Create” button.
- You will be prompted to save your seed phrase. Make sure you save your seed phrase properly as it's very crucial. Verify your seed phrase next and complete the verification.
- Once that is done, congratulations!!! You have successfully set up your wallet!!

# Get $ACME zkVerify testnet tokens
- To get testnet $ACME token:Go to zkVerify Test Token Faucet.
- Connect your wallet and click on "Claim Token", you should be able to receive $ACME.

# Proof Submission Tutorial

Before we startIf you are using Mac or Linux, feel free to skip this section and directly jump onto the ‘Clone Repository’ section. But in case you are using Windows, you need to install Windows subsystem for Linux (or WSL). You can do so by using the simple command:
<pre>wsl --install</pre>
<pre>git clone https://github.com/0xmetaschool/zkverify-proofverification.git</pre>
<pre>cd zkverify-proofverification</pre>
<pre>npm install -g snarkjs@latest</pre>
<pre>curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh</pre>
<pre>git clone https://github.com/iden3/circom.git</pre>
<pre>cd circom
cargo install --path circom
cd ..</pre>
<pre>sudo chmod +x circuit_setup.sh
./circuit_setup.sh
</pre>
<pre>git clone https://github.com/HorizenLabs/snarkjs2zkv.git
cd snarkjs2zkv
npm install
</pre>
<pre>node snarkjs2zkv convert-proof <path_to_proof.json> -o proof_zkv.json
</pre>
<pre>node snarkjs2zkv convert-vk <path_to_verification_key.json> -o verification_key_zkv.json
</pre>
<pre>node snarkjs2zkv convert-public <path_to_public.json> -o public_zkv.json -c bn128
</pre>

After completing these steps, you will see three new files generated in snarkjs2zkv called proof_zkv.json, public_zkv.json, and verification_key_zkv.json

# Sending the Proof to zkVerify For Verification

- Firstly, head over to this link - https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestnet-rpc.zkverify.io#/extrinsics
- Once you are there, you will be asked to connect to the wallet. After you are connected, you will see a screen like below. Then, select your account from the option provided.
- Next, you need to choose settlementGroth16Pallet and submitProof
- Now, in the vkOrHash section, choose Vk instead of Hash.
- Next, we will need to return to the JSON files we generated during the previous lesson. First, let’s go to the verification_key_zkv.json file and paste the fields from that file. Make sure that you do not 
  include the quotes.
- For gammaAbcG1, we need to add an item as we have two fields by pressing on ‘Add item’ and then adding both of them
- The next step is to go to the file proof_zkv.json and paste copy a, b, and c inputs from the file and paste them in the respective fields
- The last and final step is to go to public_zkv.json file and copy and paste in the last field. Now our final stage of submission before submitting the transaction

# Submit the transactions

- Click on the ‘Submit transaction’ button and you will see a page where you can sign and submit the transaction.
- You now need to ‘Approve’ the transaction with your Talisman wallet. After you approve the transaction, wait for a few seconds as your transaction is getting completed. Once your transaction is completed, you will get a notification from Talisman wallet.
- Convert your address to the new format: a. Go to https://polkadot.js.org/apps/#/utilities b. Paste your Talisman wallet address into the conversion tool. c. Copy the new converted address format.
- Now that your transaction is complete and you have your converted address, paste the new address into the explorer - https://testnet-explorer.zkverify.io/v0
- Now if you click on your Extrinsic ID, you can see your transaction

# That’s a wrap

Congratulations on successfully submitting your proof!!

