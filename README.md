# SubSquid
A Complete Guide to Participate in SubSquid Testnet

1. Get a Ubunut VPS :
   - Ram : 4GB
   - vCPU : 2

2. Install Docker : [TapHere](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

- check below ss for which cmd to use
- use them one by one
![image](https://github.com/piethor/SubSquid/assets/81746500/cbbe2e3d-beb0-4dcd-baee-94d54ddb04c2)

3. Install Node.js : [TapHere](https://github.com/nodesource/distributions#installation-instructions)

- Follow the SS and Install it
- ![image](https://i.imgur.com/iroazXA.png)

4. Start a Screen : `screen -R c1`
5. Installing SingleProSquid :

- `sudo apt install npm`
- `mkdir ~/global-node-packages`
- `npm config set prefix ~/global-node-packages`
- `export PATH="${HOME}/global-node-packages/bin:$PATH"`
- `npm install --global @subsquid/cli@latest`
- `sqd --version`
  
[if `sqd --version` doesnt work, try this, if it works then skip]
- `curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash`
- `source ~/.profile`
- `nvm install node`

After that : 
- `sqd init my-single-proc-squid -t https://github.com/subsquid-quests/single-chain-squid`
- After that Open your Server in SFTP and Paste your singleProc.Key in the following location : 
`/home/ubuntu/my-single-proc-squid/query-gateway/keys/`

then do these cmd : 
- `cd my-single-proc-squid`
- `sqd up`

- Only if `sqd up` doesnt work try this : `sudo docker compose up -d`
then do this : 
- `npm ci`
- `sqd build`
- `sqd migration:apply`
- `sqd run .`

  and After 5-10 Min Check Your Status in SubSquid Website
