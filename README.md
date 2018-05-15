# senior hyperledger development quick start


# SUPORTED OPERATING SYSTEMS
- UBUNTU : Ubuntu Linux 14.04 / 16.04 LTS ONLY !!!
- MAC OS X 10.12+

# INSTALL NODE.JS, DOCKER AND DOCKER HYPERLEDGER IMAGES 

UBUNTU

```     
    curl -O https://hyperledger.github.io/composer/unstable/prereqs-ubuntu.sh
    chmod u+x prereqs-ubuntu.sh
    ./prereqs-ubuntu.sh
```

    
MAC OS
```
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
    touch .bash_profile
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
    nvm —-version
    nvm install --lts
    nvm use --lts
    node --version
```
 
# INSTALL COMPOSER 
```
npm install -g --unsafe-perm composer-cli@0.19.4
npm install -g --unsafe-perm composer-rest-server@0.19.4

```



# INSTANTIATE IBM BLOCKCHAIN AS A SERVICE 

```
Login to https://console.bluemix.net
Access https://console.bluemix.net/catalog/services/blockchain then hit create, choose Starter Plan (FREE)
```
![BAAS](https://cdn-images-1.medium.com/max/1600/1*OwZiPHH00uUO0ALStas1Ew.gif)


# DOWNLOAD SAMPLE PROJECT 
```
 curl https://github.com/plucena/senior/sampleproject.zip
 unzip sampleproject
 cd xxxx
```

# COMPILE THE CODE
```
    ./buildbanana.sh
```



