# senior hyperledger development quick start


# SUPORTED OPERATING SYSTEMS
- UBUNTU : Ubuntu Linux 14.04 / 16.04 LTS ONLY !!!
- MAC OS X 10.12+

# INSTALL NODE.JS, DOCKER AND DOCKER HYPERLEDGER IMAGES 

UBUNTU
    curl -O https://hyperledger.github.io/composer/unstable/prereqs-ubuntu.sh
    chmod u+x prereqs-ubuntu.sh
    ./prereqs-ubuntu.sh
    
MAC OS
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
    touch .bash_profile
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
    nvm —-version
    nvm install --lts
    nvm use --lts
    node --version
    
    
# INSTANTIATE BLOCKCHAIN AS A SERVICE -

Login to https://console.bluemix.net/dashboard/apps/
