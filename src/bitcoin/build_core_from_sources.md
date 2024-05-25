## Build Bitcoin-Core from Sources

In this article, we'll walk you through the steps to build bitcoin-core from sources on an Ubuntu PC.

### Install dependencies

Next, you'll need to clone the Bitcoin Core repository from GitHub. Run the following commands 
to clone the repo and checkout the latest release (as of this writing, version 24.0.1):

```shell
sudo apt update
sudo apt upgrade
sudo apt install nano git 
sudo apt install -y build-essential libtool autotools-dev automake pkg-config
sudo apt install -y libevent-dev libboost-dev libsqlite3-dev
sudo apt install -y libminiupnpc-dev libnatpmp-dev libzmq3-dev systemtap-sdt-dev
sudo apt install -y libqrencode-dev 
```

This will update the Ubuntu package list and install the necessary packages for building Bitcoin Core.

### Clone Bitcoin repo

Next, clone the Bitcoin Core repository from GitHub by entering the following commands:

```shell
cd 
git clone https://github.com/bitcoin/bitcoin.git
cd bitcoin
git checkout tags/v24.0.1
```

This will download the Bitcoin Core source code and switch to the v24.0.1 tag.

### Install Berkeley DB

Bitcoin Core requires a specific version of Berkeley DB (version 4.8) to function properly. 
Run the following commands to install Berkeley DB:

```shell
./contrib/install_db4.sh `pwd`
export BDB_PREFIX='/home/pythcoiner/bitcoin/db4'
```

Note that you should replace /home/pythcoiner with your own home directory path.

### Build Bitcoin

Now we can build Bitcoin Core from sources. Run the following commands in the terminal:

```shell
cd ~/bitcoin
./autogen.sh
./configure BDB_LIBS="-L${BDB_PREFIX}/lib -ldb_cxx-4.8" BDB_CFLAGS="-I${BDB_PREFIX}/include" --without-gui
make -s -j8
```

The -j option with a number following it (in this case, -j8) is used to specify the number of cores 
to use during the compilation process. In this case, make (the program used to compile Bitcoin Core) 
is being instructed to use 8 cores (-j8) to speed up the compilation process.

This may take some time to complete, depending on your system's processing power.

### Firewall setting

The Bitcoin network operates on a peer-to-peer basis, which means that nodes in the network need to 
communicate with each other in order to propagate transactions and blocks.

Port 8332 is used for the JSON-RPC interface, which allows programs to communicate with the Bitcoin 
daemon using the Remote Procedure Call (RPC) protocol. The JSON-RPC interface is used by wallets and 
other applications to query the Bitcoin node for information about the blockchain, to send and receive 
transactions, and to perform other operations, it is not recomended to open this port to the public, 
but some people can decide to acces it from their local network.

In addition to private Bitcoin nodes, there are also public Bitcoin nodes that are designed to be accessible by anyone 
on the internet. These nodes are typically run by individuals or organizations that want to contribute to the 
decentralization and security of the Bitcoin network by providing a publicly accessible node for other users 
to connect to.

Public Bitcoin nodes typically have port 8333 open in order to allow other nodes on the network to connect to them. 
By providing a publicly accessible node, these users help to ensure that the Bitcoin network remains robust and 
resistant to attacks, as the more nodes there are on the network, the more difficult it becomes for an attacker to 
compromise a significant portion of the network.

Port 8333 is used for the Bitcoin peer-to-peer network protocol. This protocol is used by Bitcoin nodes to discover 
and connect to other nodes in the network, to propagate transactions and blocks, and to synchronize their copies of 
the blockchain with other nodes.

If you want to allow incoming connections to the Bitcoin Core daemon through the firewall, run the following commands 
in the terminal:

```shell
sudo apt install -y ufw
sudo ufw allow OpenSSH
sudo ufw allow 8332
sudo ufw allow 8333
```

Overall, running a public Bitcoin node is a valuable contribution to the health and security of the Bitcoin network, 
and can be a rewarding experience for those with the technical expertise to do so. However, it's important to take 
appropriate security measures to protect the node from attack, and to be aware of the potential risks and challenges 
involved in running a public node.

### Install bitcoind service

Now that we have built Bitcoin Core, we can install it as a systemd service. Run the following commands in the terminal:

```shell
cd src
sudo cp bitcoin{d,-cli} /usr/bin/
cd
mkdir .bitcoin && cd .bitcoin
nano bitcoin.conf
```

The command `cd src` is used to navigate to the `src` directory within the cloned Bitcoin repository . The `src` 
directory contains the source code for the Bitcoin Core client.

The command `sudo cp bitcoin{d,-cli} /usr/bin/` is used to copy the compiled binaries for the Bitcoin daemon 
(bitcoind) and command line interface (bitcoin-cli) to the `/usr/bin/` directory, which is a system-wide directory for 
executable programs. The `{d,-cli}` syntax is a shorthand way of copying both the `bitcoind` and `bitcoin-cli` binaries 
in a single command.

The command `cd` is used to navigate back to the user's home directory, and the command `mkdir .bitcoin && cd .bitcoin` 
is used to create a new directory called `.bitcoin` in the home directory, and then navigate into that directory.

Finally, the command `nano bitcoin.conf` is used to create and open a new file called `bitcoin.conf` in the `.bitcoin` 
directory using the Nano text editor. This file is used to configure the settings for the Bitcoin Core client, such as 
network and wallet settings, and is necessary for the client to run properly. The user can add and edit settings in 
this file as needed:

```shell
listen=1
server=1
daemon=1

rpcuser=pythcoiner
rpcpassword=maximalist
rpcallowip=0.0.0.0/0
rpcbind=0.0.0.0
```

Save the file and exit the editor.

Here's an explanation of each of the settings in the `bitcoin.conf` file, you can :

`listen=1`: This setting allows the Bitcoin Core client to listen for incoming connections from other nodes on the 
network. By default, Bitcoin Core clients only connect to a small number of other nodes for security reasons, but 
enabling listening allows other nodes to connect to your client as well, making it a more active participant in the 
network.

`server=1`: This setting indicates that the client should operate as a full node and serve incoming requests from 
other nodes. This is necessary if you want to use the client to support other Bitcoin applications, such as wallets or 
exchanges.

`daemon=1`: This setting tells the client to run in the background as a daemon, rather than as a foreground process. 
This is useful for servers or other systems that need to run the client continuously.

`rpcuser=pythcoiner` and `rpcpassword=maximalist`: These settings define the username and password for remote procedure 
calls (RPC) to the client. RPC is a protocol used for communication between different applications, and it's used by 
many Bitcoin applications to communicate with the client. The username and password are used to authenticate the 
connection and ensure that only authorized applications can access the client's data. By default bitcoin core will use 
cookie authentication instead.

`rpcallowip=0.0.0.0/0`: This setting allows RPC connections to come from any IP address. This is a potentially risky 
setting because it opens up the client to connections from any machine on the internet, so it should only be used if 
you trust all of the machines that might connect to the client.

`rpcbind=0.0.0.0`: This setting specifies the IP address on which the client should listen for incoming RPC connections. 
`0.0.0.0` means that the client should listen on all available network interfaces. This is necessary if you want to 
allow remote connections to the client from other machines.

These are only few example of the possible settings of bitcoin core, you can find more details about all the possible 
settings for Bitcoin Core in the official documentation available on the Bitcoin Core website.

The documentation provides a comprehensive list of all configuration options, including their purpose and syntax. It 
also includes recommendations and best practices for setting up a Bitcoin node.

Here's the link to the official [documentation](https://bitcoincore.org/en/doc/0.21.0/)

Next, create a systemd service file by running the following command:

```shell
sudo nano /etc/systemd/system/bitcoind.service
```

Copy and paste the following text into the file:

```shell
[Unit]
Description=Bitcoin daemon
After=network.target

[Service]
ExecStart=/usr/bin/bitcoind -daemon -datadir=/home/pythcoiner/.bitcoin -conf=/home/pythcoiner/.bitcoin
RuntimeDirectory=bitcoind
User=pythcoiner
Type=forking
PIDFile=/home/pythcoiner/.bitcoin/bitcoind.pid
Restart=on-failure
RestartSec=3

PrivateTmp=true
ProtectSystem=full
NoNewPrivileges=true
PrivateDevices=true

[Install]
WantedBy=multi-user.target
```

After creating the service file, the next step is to reload the systemd daemon and enable and start the Bitcoin 
Core service:

```shell
sudo systemctl daemon-reload
sudo systemctl enable --now bitcoind.service
```

The daemon-reload command reloads the systemd daemon to read the new configuration file for the bitcoind service.

The enable command enables the bitcoind service to start automatically at boot time, and the --now option starts the 
service immediately.

With these steps complete, your Bitcoin Core node is up and running on your Ubuntu PC. You can now check your node is 
running well with this command:

```shell
bitcoin-cli -getinfo
```

You can also have a check at this [video](https://www.youtube.com/watch?v=9MG7doxRu2I).
