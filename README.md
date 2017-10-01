# Hyperledger_Exercise

Steps to replicate issue
1. Run docker ps to make sure no containers are up
2. cd to basic network folder
3. Run the following command to generate 2 peers into the config folder 
```
../bin/cryptogen generate --config=./crypto-config.yaml
```

4. Run the following commands to generate artifacts - 1 orderer and 2 channels
```
../bin/configtxgen -profile TwoOrgsOrdererGenesis -outputBlock config/genesis.block
../bin/configtxgen -profile OneOrgChannel1 -outputCreateChannelTx config/channel1.tx -channelID mychannel1
../bin/configtxgen -profile OneOrgChannel2 -outputCreateChannelTx config/channel2.tx -channelID mychannel2
```
5. cd to fabcar directory
6. Start the *startFabric.sh* script which calls basic network's *start_2p2c.sh* script




