# eth-todo
Smart contracts are the code on the blockchain. 
They are the building blocks of the blockchain applications
Smart contracts that contain the tasks in the todo list
They are written in solidity 
Code is immutable 

Node.js 
Ganash is a personal blockchain (local blockchain) that can be accessed online
 a personal block is like a real bc network accessible to everyone that runs on a computer
Can run smart contracts, run tests, scripts against is 
Run other apps to interact with blockchain 

Use truffle framework to build ethereum smart contracts with solidity 
npm install -g truffle@5.0.2
Tools that allow you to develop, test deploy smart contracts 

Metamask extension for chrome - connect to blockchain with personal account to interact with smart contract to be developed 

We create a new directory - mkdir eth-todo-list
Check truffle version to make sure we're on the correct version 
Initialize new truffle project with "truffle init"
Create a package.json file to pull out dev dependencies - touch package.json
Get dependencies from open source git repo
"Npm install" to install dependencies

Creating the smart contract file that we are going to build the todo list 
Contract directory(comes with truffle to handle migrations to the network)
Create new file todolist.sol
Declare version of solidity - pragma solidity ^0.5.0
Declare contract with contract queuer - contract TodoList{ 
Uint taskCount}
To keep track of out list we use state variables - uint taskCount;
State variables are written to the blockchain 
They rep state of sc on blockchain 
They change when taskCount changes 
Public keyword gives functions to be able to use 

JSON representation of our smart contract is created for us when we compile (truffle compile)

To put smart contract on blckchain edit truffle-config file 




Now that we are connected to the blockchain 
We add a new file to the migrations tab and copy and paste code in the initial migration labelled/named - 2_deploy_contracts.js - 
When you put a contract on blockchain you are changing the state so you need a migration to do that 
Migration numbers tell truffle what order to run in 
Migration file gets the smartcontract on blockchain 
"Truffle migrate"
Deploying sc to bc costs gas 

Truffle console 
todoList = await TodoList.deployed()
This creates a copy of the smart contract deployed to the network and assigns it to variable 
The "await" is to factor in the asynchronized network which means wait for finished result and then assign to variable 
So the todoList shows our smart contract 

At this point we have created a smart contract, created a truffle project, connected to bc and put the sc on bc and talk to it 


Listing the tasks 
List tasks in the smart contract 
List tasks in the console 
List tasks in the client side application 
List in test


Solidity is statically typed language 
Uint - unsigned integer (non negative)

We put our tasks in a storage on the blockchain after initializing them in the struct
We can use the a state variable like taskCount 
We create a state variable called tasks and make it a mapping not a integer
mapping(uint => Task) task;
Uint - id 
Task - struct
Public gives you access to sol read functions 

To be able to populate the todo list so when its called on client side it has stuff in there
We have to add task to list when sc is deployed 
We can do that with a constructor function 
It will be called when the sc is run for the first time 
We can add default task 
Solidity doesn’t let you loop through to list all tasks out when you call out function 
The mapping is a dynamic size and there is no way to know how big it is so you cant iterate over or return the entire thing 
We have to reference 1 by 1 
Which is why we have the taskCount 
To access the default task we put "task = await todoList.task()
Task

We can create directory src and put the following files in 
Html file 
App.js file 
Bs config file  - browser synch configuration. Used as a part of lightserver (package.json)
Web server to run client side app
Needs to know where directories are.

In index.html we get that from the git repo 
![image](https://user-images.githubusercontent.com/37093536/157572947-6d40f9dc-49c4-43a1-a268-ccff8571d6b6.png)
To do app build with smart contract in solidity and deployed on blockchain 
