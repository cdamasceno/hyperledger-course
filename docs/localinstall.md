
# INSTALACAO DOCKER LOCALHOST

https://hyperledger.github.io/composer/latest/installing/development-tools.html


git clone github.com/plucena/nozluz3


1 - composer archive create -t dir -n .

2 - composer network install -c PeerAdmin@hlfv1 -a tutorial-network@0.0.1.bna 

3 - composer network start -c PeerAdmin@hlfv1  -n tutorial-network -V 0.0.1 -A admin -S lalala

4 -composer card import -f ./admin@tutorial-network.card
5 - composer network ping --card admin@tutorial-network

6 - composer-rest-server -c admin@tutorial-network -p 80 -n "never"
