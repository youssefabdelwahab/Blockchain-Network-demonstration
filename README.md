# Blockchain-Network-demonstration

Today i will show you how to be richest man to ever exsist by mining Etheruem coins and send yourself so much money so that you can buy whatever you want whereever you want
!DISCLAIMER! 
- this is not financial advice

LETS GO! 

- Step 1: 

You need to set up the tools that will use inorder to do this succeefully

In this step we will install: 

**MyCrypto** which is a GUI wallet to store your coins 

**Geth** which is the mining software so we can mine ETH
- make sure you make a new folder called Blockshain tools and store the geth files in it because we will use it in the future.


![My Crypto](Pictures/Screenshot%202021-05-04%20183536.png) 
![Geth](Pictures/Screenshot%202021-05-04%20183704.png)

- Step2: 

Now we will Run Git Bash as **Administrator** and cd into our geth file

- if you dont do this it wont work

- Step 3:

**Sanity check** 
Your directory must look like this to run commands in the geth file
![](Pictures/Screenshot%202021-05-04%20191221.png) 

Make sure you have a notebook oopen to save certain information 

- Now we will create our first node using this command
./geth --datadir node1 account new

Make a password and put it in your notebook

then save the public address in your notebook as well 

- Now we will create our first node using this command
./geth --datadir node2 account new

Make a password and put it in your note book

then save the public address as well 

![](Pictures/Screenshot%202021-05-04%20150547.png)

- Step 4

Now we will run a command that will allow us to create a new gensis and configure it 

1. type ./puppeth 
2. Name your network 
3. Choose 2 to configure new gensis and then Enter 
4. Choose 1 to import already exsisting gensis 
5. Click 2 for POA 

![](Pictures/Screenshot%202021-05-04%20150651.png)

- Step 5 

Now we will put the accounts that will be funded by the mining process

1. When it asks which accounts are allowed to seal paste your node 1 and node 2 accounts 
2. When it asks which accounts should be prefunded? paste your node 1 and node 2
3. Type no when it asks for precompiling addresses
4. Select a random numerical chain - ID and make sure to write it in your notebook 
5. Now when it asks you what would like to do? Click 2 Because we already created a exsisting gensis 
6. Now select 2 Export genesis configuration
7. Click enter 
8. Now click control C to exit

![](Pictures/Screenshot%202021-05-04%20151337.png)

- Step 6 

Now we will initialize our nodes to save them in our directory

1. Type this command to init node 1 ./geth init networkname.json --datadir node1 and click enter 
2. Type this command to init node2 ./geth init networkname.json --datadir node2 and click enter

![](Pictures/Screenshot%202021-05-04%20151638.png)

- Step 7 
Now we will start our node 1 to mine using this command: 

./geth --datadir node1 --unlock "XXXXXXXXXXXXXXXXXXXXXXXXXX" --mine --rpc --allow-insecure-unlock

instead of the XXXXXXXXXXXXXXXXXXXXXXXXXXXX - write the node1 address that you saved earlier

**The prompt will ask you for a password , type the password of node 1 that you saved earlier (dont worry if you dont see the letters its like that for secuirty) and then click enter** 

The command will exectue and if you scroll down you will find on the right a line that says **P2P Network** copy the line after the = sign and put it in your notebook. This line will be used to allow node 1 to communicate with node 2 during mining. 

![](Pictures/Screenshot%202021-05-04%20152609.png) 

Now we will open a new git bash window and cd into our geth file like previously 

Once done that we will type this command to start node 2

instead of XXXXXXXXXXXXXXXXXXXXXXXXXXXXxxx type the node 2 address 
instead of $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$ type the P2P line you copied from node 1

./geth --datadir node2 --unlock "XXXXXXXXXXXXXXXXXXXX" --mine --port 30304 --bootnodes "$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$" --ipcdisable --allow-insecure-unlock

**The prompt will ask you for a password , type the password of node 1 that you saved earlier (dont worry if you dont see the letters its like that for secuirty) and then click enter**

![](Pictures/Screenshot%202021-05-04%20152844.png)

- Step 8 

Now we will set up our wallet that will recieve the mined ETH coins

1. go to my crypto and on the left corner you will see 'Change Network'
2. Click on 'Change Network' and scroll down to 'Add Custom Node'

You should see this pop up 
![](Pictures/Screenshot%202021-05-04%20153200.png)

3. In the node name type your network name that you choose previoulsy 
4. For network choose 'Custom'
5. Type the same node name for network name
6. for currency type ETH 
7. for chain id type the ID that you choose previously 
8. for URL type this 'http://127.0.0.1:8545" not 8543 as in the picture above
9. Click on save and use custom node
10. Now you will look in the middle of the screen and choose Keystore file 
11. Navigate to where your node1 file is in your geth file 
12. Open node 1 and click on keystore 
13. Type the password of node 1 to create the wallet

![](Pictures/Screenshot%202021-05-04%20153357.png)

You should the see how rich you are on the side (should have a very large number or some number of ETH under account balance) if not then plz restart everything and delete the node 1 and node 2 and json files in your geth folder and stop the mining process and close the git bash and restart. :( i know (dont cry) 

- Step 9 
Now we will send transctions from node 1 to node 2 

1. click on "Send Ether and Tokens"
2. in address type the address of node 2 
3. in amount choose how much you want to send (be generous) 
4. send transactions 

![](Pictures/Screenshot%202021-05-04%20153546.png) 

once you click on send transactions this should pop up click send 

![](Pictures/Screenshot%202021-05-04%20153613.png)

If done correctly you should see this message on the bottom of the screen

![](Pictures/Screenshot%202021-05-04%20153650.png)

Now on the dropdown scroll and choose "Recent Transactions"

you should see that your transaction is **pending**

![](Pictures/Screenshot%202021-05-04%20153808.png)

- Step 10 

Now we must validate our Transaction , remember this is a decentraslized network so we gotta validate everything that comes through by mining.

1. Open a new git bash prompt and navigate to the geth file with your nodes 

We will now restart the mining process again 

2. Type this command and wait till it asks for the password and type your password 

instead of XXXXXXXXXXXXXXXXXXXXXXXXXXXXxxx type the node 1 address 

./geth --datadir node1 --unlock "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" --mine --rpc --allow-insecure-unlock

![](Picutres/Screenshot%202021-05-04%20153918.png) 

To check if it has recieved the transaction  you must have a line that says "Signed Must wait for others" and commit new mining work and the gas and fee should match the numbers when you look at recent transactions prompt in step 9  

You can see in the following pic gas = 21000 and fees = 0.00042 which match the previ

![](Pictures/Screenshot%202021-05-04%20154017.png) 

Now we must open a new git bash prompt and navigate into our geth file and restart node 2 using this command 

instead of 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' type your node 2 address 
instead of $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$ type the P2P line you already have copied 

./geth --datadir node2 --unlock "XXXXXXXXXXXXXXXXXXXX" --mine --port 30304 --bootnodes "$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$" --ipcdisable --allow-insecure-unlock

**after pressing enter it should ask for you password , type it and press enter again dont worry if you dont see your password** 

You should see a line that says 'imported new chain segment' this is the mined transaction that you sent 

![](Picutres/Screenshot%202021-05-04%20154201.png) 

- Step 11 

Now if you go back to your My Crypto and see recent transactions you should see that the tranaction is successfull

![](Pictures/Screenshot%202021-05-04%20154243.png) 


- Step 12 

Now go to this websites 

https://www.porsche.com/canada/en/aboutporsche/e-performance/
https://stockx.com/air-jordan-1-retro-high-white-university-blue-black

Buy me 1 Porsche Taycan 
Buy me Size 10 Jordan 1 UNC 

as gift for teaching  you this 

email youssefabdelwahab10@gmail.com for shipping information



















 







