# WhoPays
A contract-based dapp/bot to create groups in which users can keep track of their payments for a group through commands with a new chatbot / dapp. 
 
Use cases:
- When people go on vacation with a group of people and everybody pays some parts of the vacation (dinner, going out, events)
- A group of people living together where individuals buy groceries for the whole group
- You’re planning an event (lets say bachelor party!) and the friends who you’re organizing it with have multiple different expenses e.g. gas usage, food, drinks.
 
In essence it is a simple way for friends to keep track of who paid what during a trip, holiday or other period of time. 
 
Users can add and resolve payments through status commands which get send to a contract on the blockchain.  At the end of a duration when the contract needs to be resolved the creator can use a command to close the contract. The contract will calculate how much each user has to pay or receive. The contract will let the Status app know how much each user has to pay and can create Ether requests for this. When everyone has added their payments to the contract, the contract will send Ether to the users who still have to receive some. After that the contract is resolved.

# Status Hackathon Entry
This is a project created for the Status Hackathon entry. More information can be found here: https://hackathon.status.im/

# Helpful commands

## When opening Status or reconnecting device, perform the following steps:
  
  ## Run the testRPC node
  testrpc -p 8546 

  ## Open ports
  adb reverse tcp:8546 tcp:8546 && adb reverse tcp:8080 tcp:8080 && adb reverse tcp:3000 tcp:3000

  #deploy app on windows
  status-dev-cli add '{\"whisper-identity\": \"who-pays\", \"bot-url\": \"http://localhost:8080/bot/bot.js\", \"name\": \"WhoPays\"}' --ip 192.168.1.46;

  ## Switch to this testRPC node on the phone
  status-dev-cli switch-node "http://192.168.1.20:8546" --ip 192.168.1.46

  ## Migrate contracts
  truffle migrate --reset

  ## Truffle serve
  truffle serve

  ## Enable watching
  status-dev-cli watch $PWD "who-pays" --ip 192.168.2.3


