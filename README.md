
# A guide to run [PINGPONG](https://www.pingpong.build/) app (mine)
<br>

![cover](https://github.com/PR0CESSS/pingpong-node/blob/main/media/cover.png)
<br>
We are running this node on an **Ubuntu Linux server** (VPS), The PINGPONG app has a GUI on macOS and Windows so you'll be fine probably if you want to mine on those.
<br>
<br>
<h1 align="center">Table of content</h1>
<br>
<br>

+ About The Project
+ Requirements
+ Dependencies
+ Main Guide
+ Self-Custody Option Guide (Mining 0G, AIOZ and Grass)
+ Errors and Misc
<br>
<br>


<h1 align="center">About The Project</h1>
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

<h1 align="center">Requirements</h1>
<br>

![requirements](https://github.com/PR0CESSS/pingpong-node/blob/main/media/hardware_requirements.png)
<br>
<br>

<h1 align="center">Dependencies</h1>
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

<h1 align="center">Main Guide</h1>

<br>

+ **Step One**: Login

Go to [PINGPONG](https://harvester.pingpong.build/login) site and log in

<br>

+ **Step two**: Add Devices

In the **Devices** tab add a new device and give it a name
![add_devices](https://github.com/PR0CESSS/pingpong-node/blob/main/media/add_devices.png)

<br>

+ Set your running strategy:
>**Usage Priority**: Prioritize using your devices for program tasks while utilizing idle resources for mining. Perfect for personal devices in use!
>**Mining Priority**: Prioritize using your device's full computing resources for maximum efficiency in mining. Perfect for idle devices!

Copy the device ID, We will be using it when we run the app on the server
Note that if don't copy it the first time when you make the device, you need to regenerate the device ID to be able to copy it again, It's recommended to save it somewhere safe after creating the device.

<br>

+ **Step Three**: Download the PINGPONG app

Download the Linux version of the app:
```console
wget https://pingpong-build.s3.ap-southeast-1.amazonaws.com/linux/latest/PINGPONG
```

<br>

+ **Step four**: Run the PINGPONG App

Run the following command in Linux and paste in your Device key:
```console
chmod +x ./PINGPONG && ./PINGPONG --key your_device_key
```
