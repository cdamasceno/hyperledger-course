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

# DOWNLOAD SAMPLE PROJECT 
```
 curl https://github.com/plucena/senior/sampleproject.zip
 unzip sampleproject
 cd xxxx
```



# INSTANTIATE IBM BLOCKCHAIN AS A SERVICE 

```
Login to https://console.bluemix.net
Access https://console.bluemix.net/catalog/services/blockchain then hit create, choose Starter Plan (FREE)
```
![BAAS](https://cdn-images-1.medium.com/max/1600/1*OwZiPHH00uUO0ALStas1Ew.gif)


# DOWNLOAD BLOCKCHAIN CONNECTION CREDENTIALS 

1. Launch your blockchain service, and click on connection profile, and view as raw JSON
2. Scroll all the way down until you see “registrar” and then under “enrollId” will be “enrollSecret”. Copy this secret, we will need it for the next step

![BAAS](https://cdn-images-1.medium.com/max/1600/1*5xSoM5S2KfJGf9T-tzYAzA.gif)

3. Go back and instead of viewing as raw JSON, download the connection profile.
rename the downloaded JSON file to ‘connection-profile.json’


4. Move the connection-profile.json file to the Composer-Project directory on your local machine

5. Using the enrollSecret from the previous step issue this command to create a business network card for the certificate authority (CA). This command assumes my enrollSecret is ‘123456789’, but yours is likely different.

```
composer card create -f ca.card -p connection-profile.json -u admin -s *123456789*
composer card import -f ca.card -c ca
```



# COMPILE THE CODE
```
    ./buildbanana.sh
```



