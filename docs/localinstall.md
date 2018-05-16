
fabric crated using tools scripts

code based on

https://hyperledger.github.io/composer/tutorials/developer-tutorial

1 - composer archive create -t dir -n .

2 - composer runtime install --card PeerAdmin@hlfv1 --businessNetworkName tutorial-network

3 - composer network start --card PeerAdmin@hlfv1 --networkAdmin admin --networkAdminEnrollSecret adminpw --archiveFile tutorial-network@0.0.1.bna --file networkadmin.card

4 - composer card import --file networkadmin.card

5 - composer network ping --card admin@tutorial-network

6 - composer-rest-server -c admin@tutorial-network -p 80 -n "never"
