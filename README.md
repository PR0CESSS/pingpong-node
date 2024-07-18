
# A guide to run [PINGPONG](https://www.pingpong.build/) app (mine)
<br>

![cover](https://github.com/PR0CESSS/pingpong-node/blob/main/media/cover.png)

<br>

We are running this node on an **Ubuntu Linux server** (VPS), The PINGPONG app has a GUI on macOS and Windows so you'll be fine probably if you want to mine on those.

<br>
<br>

<h1 align="center">📃Table Of content📃</h1>

<br>
<br>

+ 💠About The Project💠
+ 💻Requirement💻
+ ⚡Dependencies⚡
+ ✅Main Guide✅
+ 🛑Errors and Misc🛑
<br>
<br>


<h1 align="center">💠About The Project💠</h1>
<br>

+ PINGPONG is building the largest DePIN liquidity and service aggregator.
<br>

+ PINGPONG steps in as the pivotal DePIN liquidity and service aggregator. We transform compute resources into a new form of liquidity and elevate the quality of DePIN services to energize the DePIN ecosystem.
<br>

+ Our mission is straightforward: **We're here to democratize access to compute resources through DePINFi**.
<br>

 + In the Supply side of DePIN, PINGPONG has 2 products that are going to be covered in this guide. **Aggregated & Dynamic Mining App** and **Omni-chain DePINFi Money Market**.
<br>
<br>


<br>
<br>

<h1 align="center">💻Requirements💻</h1>
<br>

![requirements](https://github.com/PR0CESSS/pingpong-node/blob/main/media/hardware_requirements.png)
<br>
<br>

<h1 align="center">⚡Dependencies⚡</h1>
<br>

+ The only dependency we need to run PINGPONG app is [Docker](https://www.docker.com/)
<br>

+ How to install docker on Linux:
<br>

1. Update your Linux packages:

```console
sudo apt-get update && sudo apt-get upgrade -y
```
<br>

2. Download Docker packages:

```console
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
<br>

3. Add docker to your packages:

```console
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
<br>

4. Update packages:

```console
sudo apt-get update
```
<br>

5. Install Docker:

```console
sudo apt-get install docker-ce
```
<br>

6. Start Docker:

```console
sudo systemctl enable docker

sudo systemctl start docker
```
<br>

7.  Give permission to Docker:

```console
sudo usermod -aG docker $USER
```
<br>

8. Test Docker:

```console
docker run test
```

<br>
<br>

+ Wget is also needed, although it is installeded by default on most servers, In case you need to install it:

```console
sudo apt-get install wget
```

<br>

<br>

<h1 align="center">✅Main Guide✅</h1>

<br>

**Aggregated & Dynamic Mining App** Guide:

<br>

+ **Step 1**: Login

Go to [PINGPONG](https://harvester.pingpong.build/login) site and log in

<br>

+ **Step 2**: Add Devices

In the **Devices** tab add a new device and give it a name
![add_devices](https://github.com/PR0CESSS/pingpong-node/blob/main/media/add_device.png)

<br>

+ Set your running strategy:
>**Usage Priority**: Prioritize using your devices for program tasks while utilizing idle resources for mining. Perfect for personal devices in use!
>**Mining Priority**: Prioritize using your device's full computing resources for maximum efficiency in mining. Perfect for idle devices!

+ Copy the device ID, We will be using it when we run the app on the server
Note that if don't copy it the first time when you make the device, you need to regenerate the device ID to be able to copy it again, It's recommended to save it somewhere safe after creating the device.

<br>

+ **Step 3**: Download the PINGPONG app

Download the Linux version of the app:
```console
wget https://pingpong-build.s3.ap-southeast-1.amazonaws.com/linux/latest/PINGPONG
```

<br>

+ **Step 4**: Run the PINGPONG App

+ Make a screen so the app can run even if you close the terminal:
```console
screen -S pingpong
```

<br>

+ Run the following command in Linux:
```console
chmod +x ./PINGPONG && ./PINGPONG --key your_device_key
```
Use your device ID from **Steo three** instead of `your_device_key`

+ Press `Ctrl + A + D` in order to detach from the screen (The app will be running in the background)

+ Also you can check the stats in your dashboard in the [PINGPONG](https://mining.pingpong.build/dashboard) site

![stats](https://github.com/PR0CESSS/pingpong-node/blob/main/media/stats.png)

<br>

+ **Stats guide**:

**Starting**: You are initiating and joining a decentralized network.

**Unconfigured**: This network needs you to enter specific information to launch. Click the settings button on the right to start filling in your configuration details. Please refer to Self-Custody Option Guide.

**Running**: Your project has joined the decentralized network and is running well. If you notice no changes in earnings, this is normal due to the network's minimum earnings display limit.

**Failed**: Your project has failed to run. Please check the cause of the failure and try restarting the network after resolving the issue.

**Unsupported**: Your computer's hardware does not meet the network's requirements, so this network cannot run. If you upgrade your hardware, you can exit PINGPONG and restart.

**Stopped**: You have stopped the network's running. Click the start button on the right to restart the network.

<br>
<br>

<h1 align="center">✅Omni-chain DePINFi Money Marke Guide✅</h1>

<br>

+ **0G Configuration Guide**:

+ <br>

**Step 1**: Get an account in MetaMask for 0G faucet. It will be used to run 0G and receive rewards.

<br>

**Step 2**: Visit the 0G [faucet website](https://faucet.0g.ai/), and enter your account address.

<br>

**Step 3**: Request AOGI token and wait for the faucet to succeed.

<br>

**Step 4**: Export the private key of this account:

![getting_private_key](https://github.com/PR0CESSS/pingpong-node/blob/main/media/getting_private_key.gif)

<br>

![getting_private_key_2](https://github.com/PR0CESSS/pingpong-node/blob/main/media/getting_private_key_2.gif)

<br>

![getting_private_key_3](https://github.com/PR0CESSS/pingpong-node/blob/main/media/getting_private_key_3.gif)

<br>

**Step 5**: Enter the key in your command line like below to complete the configuration and start:

```console
./PINGPONG config set --0g=your_private_key
```

```console
./PINGPONG stop --depins=0g
```

```console
./PINGPONG start --depins=0g
```

<br>

+ Replace `your_private_key` in the command obove

<br>

+ **AIOZ Configuration Guide**:

<br>

**Step 1**: Follow the [AIOZ official guide](https://docs.aioz.network/aioz-depin/aioz-nodes/cli-node) to generate a new mnemonic phrase and private key.

<br>

**step 2**: Copy the key value from the "priv_key" field in the command response. Ensure you store this data securely.

![aioz_config_response](https://github.com/PR0CESSS/pingpong-node/blob/main/media/aioz_config_response.png)

<br>

**Step 3**: Enter the key in your command line like below to complete the configuration and start:

```console
./PINGPONG config set --aioz=your_private_key
```

```console
./PINGPONG stop --depins=aioz
```

```console
./PINGPONG start --depins=aioz
```

<br>

+ Replace `your_private_key` in the command obove

<br>

+ **Grass Configuration Guide**:

<br>

**Step 1**: Open Developer tools.

>Click on the three vertical dots (menu) in the upper-right corner of your browser.
>Navigate to More tools.
>Click on Developer tools.

<br>

**Step 2**: Navigate to the Application tab.

>In the Developer Tools pane, click on the Application tab.
>If you don't see the Application tab, you might need to expand the pane or click on the double arrow (>>) to see more tabs.

<br>

**Step 3**: Locate LocalStorage.

>In the left-hand sidebar, under the Storage section, find and click on Local Storage.
>You will see a list of domains.
>Click on the domain https://app.getgrass.io.

<br>

**Step 4**: View LocalStorage data.

>In the right-hand pane, find the key named userId.

<br>

**Step 5**: Copy the value of userId.

> Double-click on the value field of userId to select it.
> Copy the value, Do not include the double quotes.

<br>

![grass](https://github.com/PR0CESSS/pingpong-node/blob/main/media/grass.png)

<br>

Step 6: Configure the key you obtained using the following command.



<h1 align="center">🛑Errors And Mics🛑</h1>

<br>

```console
./PINGPONG config set --grass=the_value_you_copied
```

```console
./PINGPONG stop --depins=grass
```

```console
./PINGPONG start --depins=grass
```

<br>


---

------------| If this guide was useful, Please consider giving it a ⭐ |------------
