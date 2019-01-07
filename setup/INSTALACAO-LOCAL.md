
# INSTALAÇÃO DO HYPERLEDGER FABRIC E DO COMPOSER COMPUTADOR/SERVIDOR LOCAL

Requisitos gerais 

-  Recomendavel 8 GB de RAM local ou na VM

- A ferramenta de desenvolvimento Composer só funciona no  Ubuntu Linux 14.04 / 16.04 LTS (both 64-bit), ou Mac OS 10.12 ou mais novo. Caso não tenha estes como seu sistema operacional recomendamos fazer uma instalação numa VM - http://br.releases.ubuntu.com/16.04/

- A instalcação deve ser feita como usuario comum. Não funciona como root. Usar seu usuario. Ou criar um usuario novo. Exemplo:

    adduser blockchain

    usermod -aG sudo blockchain

# Instalando os pre-requisitos 

O Hyperledger roda como Docker e o Composer depende do node e de varias bibliotecas criptográficas. Um unico script instala todas as dependencias necessárias:

    curl -O https://hyperledger.github.io/composer/latest/prereqs-ubuntu.sh

    chmod u+x prereqs-ubuntu.sh

    ./prereqs-ubuntu.sh

fazer logout da sessão

# Instalar o Fabric 1.2

fazer login em nova sesão

    mkdir ~/fabric-dev-servers && cd ~/fabric-dev-servers

    curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz

    tar -xvf fabric-dev-servers.tar.gz

    cd ~/fabric-dev-servers

    export FABRIC_VERSION=hlfv12

    ./downloadFabric.sh



# Instalar o Composer

instalação obrigatoriamente como usuario comum.  root não funciona

    npm install -g composer-cli@0.20

    npm install -g composer-rest-server@0.20

    npm install -g generator-hyperledger-composer@0.20

    npm install -g yo


# Gerando as chaves de acesso do Fabric ao Composer

   cd ~/fabric-dev-servers
    
    export FABRIC_VERSION=hlfv12
    
    ./startFabric.sh
    
    ./createPeerAdminCard.sh

    composer card list
    

# Testar um projeto

    git clone https://github.com/plucena/composer-example
    
    cd composer-example
    
    composer archive create -t dir -n .

    composer network install -c PeerAdmin@hlfv1 -a tutorial-network@0.0.1.bna 

    composer network start -c PeerAdmin@hlfv1  -n tutorial-network -V 0.0.1 -A admin -S adminpw

    composer card import -f ./admin@tutorial-network.card

    composer network ping -c admin@tutorial-network

    composer-rest-server -c admin@tutorial-network -p 80 -n "never"
