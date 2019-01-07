
# INSTALACAO DOCKER LOCALHOST


Instalar o Fabric 1.2

mkdir ~/fabric-dev-servers && cd ~/fabric-dev-servers

curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz

tar -xvf fabric-dev-servers.tar.gz

cd ~/fabric-dev-servers

export FABRIC_VERSION=hlfv12

./downloadFabric.sh


https://hyperledger.github.io/composer/latest/installing/development-tools.html


git clone https://github.com/plucena/nosluz3


1 - composer archive create -t dir -n .

2 - composer network install -c PeerAdmin@hlfv1 -a tutorial-network@0.0.1.bna 

3 - composer network start -c PeerAdmin@hlfv1  -n tutorial-network -V 0.0.1 -A admin -S adminpw

4 -composer card import -f ./admin@tutorial-network.card

5 - composer network ping -c admin@tutorial-network

6 - composer-rest-server -c admin@tutorial-network -p 80 -n "never"
