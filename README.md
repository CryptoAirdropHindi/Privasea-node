# Privasea-node


- First pull the docker image using the following command
```
docker pull privasea/acceleration-node-beta:latest
```
- Create a directory and navigate to it
```
mkdir -p ~/privasea/config && cd ~/privasea
```
- Run the below command to get a new wallet keystore
- Here you need input a password after running the below command, make sure to remember it for future use and also note down the `node address` as well
```
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```
- Move the keystore file to a new file
```
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```
- Now visit this [Privanetix Dashboard](https://deepsea-beta.privasea.ai/privanetixNode)
- Connect a wallet where you will recieve reward and then give the node any name, set up commission (I will use 1%), and then enter the `node address` you note down in above step and then click on **Set up my node** option
- Now run the below command to start your `Privasea Privanetix Node`, Make sure to replace **ENTER_YOUR_KEYSTORE_PASSWORD** with your **Keystore Password**, you provided in the above steps
```
KEYSTORE_PASSWORD=ENTER_YOUR_KEYSTORE_PASSWORD && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```

- Now follow the guide from **Step 3 (Manage my Privanetix node)** from [this docs](https://www.privasea.ai/privanetix-node)
