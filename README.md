# bloxberg Bootnode

The bloxberg bootnode plays a crucial role in the network by enabling new nodes to find and connect with existing peers. It enhances network stability, security, and management by serving as a reliable entry point. With its help, the bloxberg blockchain network maintains a robust and well-connected ecosystem.

The blockchain connects to other nodes via UDP and TCP port 30303, so it is important this port is open via your firewall beforehand.

In the docker-compose.yml you will also see the ports 8545 (JSON-RPC API) and 8546 (Web-Socket). These can be used to interact with blockchain via means of your local node but don't need to be accessible over the internet.

The above ports are already in use if you are currently running the Validator node. If so, you can visit bootnode.yml and modify the port number to 30304,8547,8548. and make sure to open port 30304 via your firewall.

# Setup Process

1. Clone the repository to the server you are hosting the bootnode.
2. CD into the './bootnode' folder and edit the bootnode.toml file with your text editor. Change the nat: setting to your external IP. Once done, save this file
3. Change the password in bootnode.pwd to a secure password.
4. Go back into the parent directory and run 'sudo ./setup.sh'.
5. Once complete, run 'docker-compose -f bootnode.yml up' This will start the bootnode. Ensure it is syncing and then you can close it with Ctrl+C.
6. Lastly, run 'docker-compose -f bootnode.yml up -d' to daemonize the node.
