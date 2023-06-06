[![github][github-lastcommit-shield]][repo-url]
[![github-followers][github-followers-shield]][github-followers-url]
[![github-fork][github-fork-shield]][github-fork-url]
[![github-stars][github-stars-shield]][repo-url]
[![twitter][twitter-shield]][twitter-url]

<!-- PROJECT LOGO -->
<div align="center">
  <a href="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial">
    <img src="images/10420-removebg.png" alt="Logo" width="200" height="200">
  </a>
  <h5>oFriends#10420</h5>
  <h2 align="center">oCash Mining Pool Setup Tutorials</h2>

  <p align="center">
    oCash is a crypto currency that empower oLand metaverse by <a href="https://twitter.com/overlinenetwork">@overlinenetwork</a>
    <br />
    <!--     <a href="https://github.com/github_username/repo_name"><strong>Explore the docs »</strong></a> -->
    <br />
    <br />
    <a href="https://ocash.network" target="_blank">View Demo</a>
    |
    <a href="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/ssues">Report Bug</a>
    |
    <a href="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/issues">Leave Comments</a>
  </p>
</div>

<a name="readme-top"></a>




## Before We Start

This tutorial is for setting up a `cloud based oCash Mining Pool` over AWS LightSail VPS instance.
If you intend to set the mining pool VPS on your local device, please follow <a href="https://medium.com/@uanid/how-to-install-ocash-mining-pool-full-version-2a5ebf587d35" target="_blank">this</a> tutorial provided by @uanid
<br/>
> This tutorial is derivative version of <a href="https://github.com/overliner/ocash-mining-pool" target="_blank">ōCash Mining Pool by @overlinenetwork </a>.
> We will walk through the steps as simple as possible for those of whom are new to the mining world including myself. Please report any bugs, or comments along with instruction steps. Your valued feedbacks will help #oland Community. 


## Table of Contents
<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## Built with

> For the demonstration purpose, We will host a static website; 

* [![lightsail][lightsail-shield]][lightsail-url]
* [![html][html-shield]][html-url]


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

Throughout this tutorial, we are going to set up Linux VPS(Virtual Private Server) on `Amazon LightSail`, and walk through how we make secure connection to the server through `SSH` & transfer files using `SFTP` as well as basic `Linux commands` to be able to setup your oCash Mining Pool successfully. Also, for the demonstration purposes, we will host a `static website` and connect `custom domains`. 

> Feel free to explore other VPS providers, and choose whichever provider is suitable for your budget, UI, or your own preference. There are 100's of providers available. Check <a href="https://www.google.com/search?q=vps+provider+list&sxsrf=APwXEde1H7TPezGQCqAOomKFr6natjwx0w%3A1685476325270&source=hp&ei=5VN2ZM_bDLTg0PEP0tqzmAo&iflsig=AOEireoAAAAAZHZh9b0zuxO7LNaFgpSCOnqRyCT8pGRg&ved=0ahUKEwiP4pDN6J3_AhU0MDQIHVLtDKMQ4dUDCAs&uact=5&oq=vps+provider+list&gs_lcp=Cgdnd3Mtd2l6EAMyBQgAEIAEMgYIABAWEB4yCAgAEIoFEIYDMggIABCKBRCGAzIICAAQigUQhgMyCAgAEIoFEIYDOgQIIxAnOhMILhCKBRCxAxCDARDHARDRAxBDOgcIABCKBRBDOg0ILhCKBRDHARDRAxBDOhEILhCABBCxAxCDARDHARDRAzoUCC4QgAQQsQMQgwEQxwEQ0QMQ1AI6DgguEIMBENQCELEDEIoFOggIABCKBRCRAjoICAAQgAQQsQM6CwguEIAEELEDEIMBOgsILhCDARCxAxCABDoLCAAQgAQQsQMQgwE6CwguEIAEELEDENQCOgUILhCABDoQCC4QigUQsQMQxwEQ0QMQQzoLCAAQigUQsQMQgwE6BwgjEOoCECc6DQguEIoFEMcBEK8BECc6BwgjEIoFECc6CwguEIMBELEDEIoFOgsILhCABBDHARDRAzoKCAAQigUQsQMQQzoNCAAQigUQsQMQgwEQQzoRCC4QgAQQsQMQgwEQxwEQrwE6BAgAEAM6CwguEIoFELEDEIMBOgsILhCABBDHARCvAToICAAQFhAeEA9QAFi3OGDXOWgJcAB4AYABygSIAe8VkgEIMjAuNS41LTGYAQCgAQGwAQo&sclient=gws-wiz" target="_blank">Google's serached "VPS Provider List" results</a>, and many of them provides promotions such as $100-$300 credit, 3 month free trial, etc. I choose AWS LightSail since I'm familiar with other AWS Services, and it has 3 month free tiral promos.  

## Prerequisites

> Feel free to skip over any of following setps if you already completed. 

### GitHub Account ![required-shield]
------
Step1. Create Account: 
In order to clone the git repository, we need a GitHub ID & Password. If you don't have one yet, please sign up <a href="https://github.com/" target="_blank">here</a>.

Step2. Create `Personal Access Token`:
1. Login Github
2. Click on Github account icon -> `Settings` -> `Developer Settings`
3. Click `Personal Access Token(PST)` -> Tokens(Classic)
4. Select `Expiration Day` and Select `Scopes`
5. Click `Generate Token`

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/8705ac56-bfad-41e7-ae98-98f15f765de5" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/fcf3bd17-c0e6-40bc-a317-967bdd03b3c1" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/dada5ad1-a9e3-44e6-b061-b5f98784beaf" width="11%"></img> 


### AWS IAM Set up ![recommended-shield]
------
Before we are setting up VPS instance,  Sign up AWS account(`root user`) <a href="" target="_blank">here</a> if you don't have one yet. Then we are going to set up `IAM user` instead of using `root user`.

1. Login in as `Root User` with your Email address
2. Search IAM in the search bar and click `users' on the left sidebar.
3. Click on `Add Users`, Then Type `User name` and `Password`
4. Select `Add user to group`, then click `Create group`
5. Give a `User group name`, serach & select "AdministratorAccess". Then create user group
6. Review and click `Create user`
7. Return to users list then copy down 12 digits `Account ID`
8. Logout and Login back using `Account ID` `IAM user` `password` that we just created

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/9dfa7c8c-eac7-4c6c-96b2-f11faa9c1bd5" width="11%"></img> <img 
src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/73449a82-748f-4021-85b3-f0729551aad6" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/cf6c9853-7381-462d-bb1d-6a1ec558ee29" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/7747371b-5f07-484e-8af4-c3018a93e308" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/bc8df107-02de-4dd1-a096-f85cd88fafbf" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/06e2efea-f076-4a88-abf7-e35385ae4378" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/712c7062-5425-4f3c-ab68-d3f03b31262e" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/72080b6e-4b35-4051-99f2-241c121d0306" width="11%"></img> 

### AWS LightSail Set Up ![required-shield]
------
This step we are going to setup VPS instance. One you login to <a href="" target="_blank">AWS Console </a> you can simply type `LightSail' on the searchbar or Find the link <a href="" target="_blank">here</a>
1. Create Instance
   - Select Instance Location
   - Select a Platform(Linux / Windows)
   - Select a bluprint

> ![important-shield] Please select minimum 1GB Memeory to be able to install Go package without an issue.

> For this tutorial, we will host a static website for the demonstrate purpose, so we select `Linux OS Debian v10.8` only; However, feel free to choose whichever OS you are confortable with and a blueprints for applications listed below. 


<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/f6de655d-d20d-4682-8526-88f38529e37d" width="11%"></img> 

2. Attach Static IP
3. Open Ports

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/329df9da-04f3-4d84-bbf0-ca1ac5c89997" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/f5dec8be-a60e-4d03-9b6f-e428cc180a2e" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/13dd2fec-9ea7-4d68-827f-c77e4d450594" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/9cd7ffeb-73f5-4147-a1d9-e5284aae8250" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/7fe74ab7-d06e-43d7-80a5-943a0127602b" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/72ac728a-cf5e-4a13-a21f-aa538a140521" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/4bbfa80b-41a8-4558-abe2-ce3839bb18cc" width="11%"></img> 


### Purchase & Connect Domain ![required-shield]
------
In order to provide easy accesss for miners to your mining pool, purchasing your own domain is recomened.
1. Purchase your domain name
> There are many domain registration service providers. Pick any of providers here and create your own unique, eye-catching, and easy-to-remmeber domain name. ex)<a href="https://ocash.network" target="_blank">`ocash.network`</a>
> For this tutorial, we use <a href="https://domains.google/" target="_blank">Google Domains</a>
      
   - Login your Google account
   - Search domain name that you wish for
   - Select alternates if it's already exit
   - Make a purchase

2. Connect your domain
   - Open <a href="https://domains.google/" target="_blank">Google Domains</a>
   - Select your domain name
   - Click `DNS` then, `Manage Custom Record` 
   - Add custom record, `Host name` as ""(Empty) `Type` as "A" then, `Data` as  `your VPS Public IP address(Static IP)`
   - Add custom record, `Host name` as "WWW" `Type` as "A" then, `Data` as  `your VPS Public IP address(Static IP)`

  > When its succeessfully updated custom record, it will take 1-3 mins to reflect changes.
  
  > FYI, once you type your domain in the web browser, <u>the page won't be displayed since we haven't set up `web server` yet</u>
  
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/5129c17b-285e-44f7-a537-5b49ce91f32f" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/bdbed861-f7f7-4bbc-a65d-7d7619b168da" width="11%"></img> 


<p align="right">(<a href="#readme-top">back to top</a>)</p>
<br/>

### MobaXterm ![recommended-shield]
------
> Feel free to skip this secection if you have/prefer using other softwares for `SSH` connection and `STFP` file transfer.
<br/>

#### What is MobaXterm?
MobaXterm is a software toolbox for a secure connection to remote server / remote computing.
- We will focus on `SSH Connection` and `SFTP`(Secured File Transfer Protocol)
  - `SSH Connection` : Make direct connection to remote server using SSH without opening LightSail Dashboard.
  - `STFP`: Transfer files between AWS LightSail VPS and local machine(Windows/Mac.

#### Before We make Connections
1. Download MobaXterm HomEditon v23.1 `Installer Edition` or `Portable Edition` can be found <a href="https://mobaxterm.mobatek.net/download-home-edition.html" targer="_blank">here</a>
2. Open AWS LightSail instance <a href="https://lightsail.aws.amazon.com/ls/webapp/home/instances" targer="_blank">dashboard</a> and download `SSH Key(.pem)`

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/4543a7c5-9415-4142-95ce-3023ae3a21cc" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/ba49fd6a-bcb1-45a5-b9ad-01fddf4c2b89" width="11%"></img> 

> Make sure your server opens `port 22` and place `SSH Key` file in a secure place

#### SSH Connection
1. Open MobaXterm & Click `Session`
2. Fill out `Remote host` as your server's `Public IP address`, `Specify username` as your `IAM User`, then select `Port 22`
3. Click `SSH` then, Select `Advanced SSH settings`
5. Check `Use private key`, then select `SSH key(.pem)` file downloaded from AWS Instance Dashboard
6. Click `Ok`

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/0fc469b2-4e6f-4fb2-9dad-e260183a25c6" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c9b7100b-f2af-4f41-8a85-cedafa226567" width="11%"></img> 


#### SFTP Connection
1. Open MobaXterm & Click `Session`
2. Fill out `Remote host` as your server's `Public IP address`, `Specify username` as your `IAM User`, then select `Port 22`
3. Click `SFTP` then, Select `Advanced Sftp settings`
4. Check `Use private key`, then select `SSH key(.pem)` file downloaded from AWS Instance Dashboard
6. Click `Ok`

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/0fc469b2-4e6f-4fb2-9dad-e260183a25c6" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/6c10ae09-65eb-401a-8af3-3eb8f1918eb3" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/93143527-d0e1-48ac-93bc-266c17505042" width="11%"></img> 

> After we make a serue connection to the server, we can easily transfer files between local computer and cloud Server by simply drag & drop. Also, we can select and open files from server panel, then It will open up a text editor to edit & save to the cloud server directly. It will make easier for us to update `.env` and `config.json`file for the configuration which we will walk through later in this tutorial. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Installation
### 1. Utility Packages
------
Install essential packages:
```
sudo apt install build-essential
```

### 2. Git
------
Update APT package management tools:
``` 
sudo apt update
```
Download and Install Git:
```
sudo apt install git
```
Verify the installation:
```
git --version
```
### 3. Golang
------
Part1:Installation
Install Go 1.20.4:
> Check out the latest release<a href="https://go.dev/dl/" target="_blank"> here </a>
```
sudo wget https://golang.org/dl/go1.20.4.linux-amd64.tar.gz
```
Verify downloaded tarball version with the SHA256:
```
sha256sum go1.20.4.linux-amd64.tar.gz
```
Extract `go1.20.4.linux-amd64.tar.gz` Go tarball file to the ‘/usr/local’ directory:
```
sudo tar -C /usr/local -xzf go1.20.4.linux-amd64.tar.gz
```
Change the owner and group of this directory to root recursively:
```
sudo chown -R root:root /usr/local/go
```
Part2:Configuration
Make new directory for Go:
```
mkdir -p $HOME/go/{bin,src}
```
Adding Global variable $GOPATH and `ctrl+x` to close then, save and close:
```
nano ~/.profile
```
```
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
export PATH=$PATH:$GOPATH/bin:/usr/local/go/bin
```

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/2f397257-04e1-4105-98b3-9b998ffb09e7" width="18%"></img> 

Reload environmental variable with command:
```
. ~/.profile
```
Verify newly added path: 
```
echo $PATH
```
output:
<pre>
admin@ip-xxx-xx-xx-xx:~$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/home/admin/go/bin:/home/admin/go/bin:/usr/local/go/bin
admin@ip-xxx-xx-xx-xx:~$
</pre>

Verify the installation:
``` 
go version
```
output:
<pre>
admin@ip-xxx-xx-xx-xx:~$ go version
go version go1.20.4 linux/amd64
admin@ip-xxx-xx-xx-xx:~$
</pre>

### 4. Go-Ethereum
------
#### Step1. Installation
We are going to install go-ethereum from git repository. Check <a hfef="https://geth.ethereum.org/docs/getting-started/installing-geth" target="_blank">here</a> to find out more options.

```
git clone https://github.com/ethereum/go-ethereum.git
```
```
cd go-ethereum
```
```
make geth
```
> Note: If Go build exits with “signal: killed”, please check your server memory. Minimum 1GB Memory required to install package successfully.

#### Step2. Update
Change directory from home to go-ethereum:
```
cd go-ethereum 
```
```
git pull
```
```
make geth
```

#### Step2. Create geth account
1. Open profile file and add export path then `Ctrl+X` to Save & Close:
```
nano ~/.profile
```
```
export PATH=$HOME/go-ethereum/build/bin:$PATH
```
2. Reload environmental variable with command:
```
. ~/.profile
```
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/139562e2-0c78-4139-b160-7e0e488c4ac1" width="11%"></img> 

3. Create geth account with following command:
```
geth account new
```
ex)
<pre>
$ geth account new
Your new account is locked with a password. Please give a password. Do not forget this password.
Passphrase:
Repeat passphrase: 
Address: {168bc315a2ee09042d83d7c5811b533620531f67}
</pre>

> System will require a password for your geth account. Type password or create one <a href="https://www.lastpass.com/features/password-generator" target="_blank">here</a> 

> More geth commands list by typing `geth help`

Once geth account created, the account is stored in following path by geth in file
  - For Linux `~/.ethereum/keystore`
  - For Mac: `~/Library/Ethereum/keystore`
  - For Windows: `%APPDATA%Ethereum/keystore`
  
 > where `~` is your home folder. 

4. Open Notepad and copy & paste your password and save the file as `password.txt`
5. Create `~/.ethereum/password` folder and upload `password.txt` file `using MobaXterm SFTP`
6. Download `geth account file` as a backup and place in a secure place

> Keystore Path: `/home/admin/.ethereum/keystore` <br/>
Password.txt Path: `/home/admin/.ethereum/password/password.txt`

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/0100af46-2c37-402f-9f95-1ff3b4a590b4" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/af2ab9b1-6a8f-4ab8-909c-9247d7590012" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/29ba05a1-19ab-45ce-86c3-421a69322c54" width="11%"></img> 


### 5. Docker
------
#### Installation
Remove old version of `docker`, `docker.io`, and `docker-engine` that may already installed previously:
```
sudo apt-get purge docker lxc-docker docker-engine docker.io
```
Update defuault repository:
```
sudo apt-get update
```
Install required dependencies:
```
sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common
```
Install Docker using the Repository on Debian10:
```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
```
Add the docker repository to your system:
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian buster stable"
```
Update Repository:
```
sudo apt-get update
```
Install Docker Engine:
```
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
Check the status:
```
sudo systemctl status docker
```
output: <pre>
admin@ip-xxx-xx-xx-xxx:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Sat 2023-06-03 22:12:45 UTC; 18s ago
     Docs: https://docs.docker.com
 Main PID: 2588 (dockerd)
    Tasks: 7
   Memory: 33.7M
   CGroup: /system.slice/docker.service
           └─2588 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
</pre>
Verify the installation by checking version of the Docker:
```
docker -v
```
Output: <pre>
dmin@ip-xxx-xx-xx-xxx:~$ docker -v
Docker version 24.0.2, build cb74dfc
</pre>
Verify the installation by running `Hello World Image`:
```
docker run hello-world
```

> ![important-shield] If system arises `Permission denied` error during the steps, run the following command to grant the permission then `exit` command to logout and re-login back:

```
sudo usermod -a -G docker $USER
```
Repeat `docker run hello-world` will display following output:
<pre>
admin@ip-xxx-xx-xx-xxx:~$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
719385e32844: Pull complete 
Digest: sha256:fc6cf906cbfa013e80938cdf0bb199fbdbb86d6e3e013783e5a766f50f5dbce0
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
</pre>

## Running oCash Mining Pool
### Step1. Clone the mining pool repo.
-----
clone the pool git repository:
```
git clone https://github.com/overliner/ocash-mining-pool.git
```
output:
<pre>
admin@ip-xxx-xx-xx-xxx:~$ git clone https://github.com/overliner/ocash-mining-pool.git
Cloning into 'ocash-mining-pool'...
remote: Enumerating objects: 25, done.
remote: Counting objects: 100% (25/25), done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 25 (delta 10), reused 22 (delta 8), pack-reused 0
Unpacking objects: 100% (25/25), done.
admin@ip-xxx-xx-xx-xxx:~$ 
</pre>

move to the repository clone:
```
cd ocash-mining-pool
```
output:
<pre>
admin@ip-xxx-xx-xx-xxx:~$ cd ocash-mining-pool
admin@ip-xxx-xx-xx-xxx:~/ocash-mining-pool$ 
</pre>

copy template configuration example files(`.env.example, `config.example.json`) to actual ones(`.env`, `config.json`):
```
cp .env.example .env && cp config/config.example.json config/config.json
```

### Step2. Update .env/config.json
-----

* .env
  - Open `.env` file from `MobaXterm`.
  - Replace `POOL_ADDRESS` with `geth account address`.
  - Replace `KEYSTORE_DIR_PATH` with `"/home/admin/.ethereum/keystore"`.
  - Replace `KEYSTORE_PASSWORD_FILE_PATH` with `"/home/admin/.ethereum/password"`.
  - Replace `POOL_TLS_CERT_PATH` after we complete <a href="">TLS Configuration steps</a> below.

> Type `geth account list` to check wallet address that we created from <a href="">this steps</a>.

> By default, Keystore file stored in `~/.ethereum/keystore` in Linux. If you updated the path, you need to specify the exact path and update on `docker-compose.yml` lineNo.67 as well.<br/>

> Make sure to upload `password.txt` file that we previsouly created from <a href="">this steps</a> to `"/home/admin/.ethereum/password"` path. Otherwise, we need to specify it and update on `docker-compose.yml` lineNo.68 as well.

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/52e8ca05-f382-4c8d-bfc8-7b7e09552139" width="11%"></img> 

* config.json
  - Open `config.json` file located in `/home/admin/ocash-mining-pool/config/` from `MobaXterm`
  - On lineNo.72, Replace `<pool ocash address>` with `geth account address`.
  - On lineNo.76, Replace `<rewards ocash address>` with `geth account address` for now.
 
> `<pool ocash address>` is the only needed one for basic setup, must match `POOL_ADDRESS` in .env

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/757a0d94-f786-40b3-909d-ed0c60f80e52" width="11%"></img> 

* Make sure Keystore file in the directory you filled in `.env`
* Make sure Password file in the directory you filled in `.env`
* Double check the permission gratned on `keystore` and `password` files.

### Step3 Run Docker Container
------
run the container(s):
```
docker compose up
```

### Step4 Test
------

<br/>
<br/>


## TLS Configurations ![recommended-shield]
### Testing Setup
------
#### Step1. Install mkcert
Update package & install necessary utility:
```
sudo apt update
```
```
sudo apt install wget curl libnss3-tools
```
Download the latest release of mkcert: 
```
curl -s https://api.github.com/repos/FiloSottile/mkcert/releases/latest | grep browser_download_url | grep '\linux-amd64' | cut -d '"' -f 4 | wget -i -
```
Rename the downloaded file and move it to `/usr/bin/ folder`:
```
sudo mv mkcert-v*-linux-amd64 /usr/bin/mkcert
```
Make the file executable:
```
sudo chmod +x /usr/bin/mkcert
```
Verify the installation by checking mkcert version:
```
mkcert --version
```
output:
<pre>
...
Saving to: ‘mkcert-v1.4.4-linux-amd64’

mkcert-v1.4.4-linux-am 100%[==========================>]   4.57M  --.-KB/s    in 0.03s   

2023-06-03 23:22:12 (138 MB/s) - ‘mkcert-v1.4.4-linux-amd64’ saved [4788866/4788866]

FINISHED --2023-06-03 23:22:12--
Total wall clock time: 0.3s
Downloaded: 1 files, 4.6M in 0.03s (138 MB/s)
admin@ip-xxx-xx-xx-xxx:~$ sudo mv mkcert-v*-linux-amd64 /usr/bin/mkcert
admin@ip-xxx-xx-xx-xxx:~$ sudo chmod +x /usr/bin/mkcert
admin@ip-xxx-xx-xx-xxx:~$ mkcert --version
v1.4.4
admin@ip-xxx-xx-xx-xxx:~$ 
</pre>

#### Step2. Generate Certificate
```
mkcer -install
```
output:
<pre>
admin@ip-xxx-xx-xx-xxx:~$ mkcert -install
Created a new local CA 
The local CA is now installed in the system trust store! ⚡

admin@ip-xxx-xx-xx-xxx:~$ 
</pre>

```
mkcert -cert-file pool-cert.pem -key-file pool-cert.key <POOL_PUBLIC_IP_ADDRESS>
```
> Replace `<POOL_PUBLIC_IP_ADDRESS>` with your `server's public static IP Addresss`

output:
<pre>
admin@ip-xxx-xx-xx-xxx:~$ mkcert -cert-file pool-cert.pem -key-file pool-cert.key 54.173.92.14

Created a new certificate valid for the following names 
 - "<POOL_PUBLIC_IP_ADDRESS>"

The certificate is at "pool-cert.pem" and the key at "pool-cert.key" ✅

It will expire on 4 September 2025 

admin@ip-xxx-xx-xx-xxx:~$ 
</pre>

<!-- 
`pool-cert-self-signed.pfx` 
-->
<br/>

```
openssl pkcs12 -export -out pool-cert-self-signed.pfx -inkey pool-cert.key -in pool-cert.pem
```

output: 
<pre>
admin@ip-xxx-xx-xx-xxx:~$ openssl pkcs12 -export -out pool-cert-self-signed.pfx -inkey pool-cert.key -in pool-cert.pem
Enter Export Password:
Verifying - Enter Export Password:
admin@ip-xxx-xx-xx-xxx:~$ 
</pre>

> choose a password or leave `blank` for `no password`


### Production Setup
------

Install CertBot
```
sudo apt-get install certbot
```
Generate Key
```
sudo certbot certonly --manual --preferred-challenges dns --email <your email> --domains <your domain>
```
> Update `<your email>` / `<your domain>` to yours

Server displays instruction for DNS challenge:
<pre>
Please deploy a DNS TXT record under the name
_acme-challenge.<your domain> with the following value:
7EDYcJQxiBxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Before continuing, verify the record is deployed.
Press Enter to Continue
</pre>

Follow instruction to add DNS TEXT Record to your domain prodivder, (<a href="https://domains.google.com/" target="_blank">Googld Domains</a> in our case)
  - Open `Googld Domains` -> Select your Domain -> Click `DNS` -> `Manage Custom Record`
  - Add new Custom DNS Record with given `Host Name` as `_acme-challenge.<YOUR_DOMAIN>` 
  - Add `Data` as given string then `Save` 
  - press `Enter` to continue on your server to pass the DNS challenge. 

> Note that we need to select `type` as `TXT`, and add `_amc-challenge` in the `Host Name` field. Google Domains will automatically append `.<YOUR_DOMAIN>` in the end. ex) `_acme-challenge.ocash.network`, and the `Data` will be wrapped with double quotation marks.

> If the verification failed, you need to double check DNS Record, then repeat the process until you pass the challenge. Everytime re-run the command, it will generate new testing value so that you need to update DNS Record.  

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c2b3f086-c24a-4f47-be9b-4893250dbab1" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c278b688-f2a1-4db6-9d91-3544ad7acd1d" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/d9c5fec2-8ed7-401c-acf8-578663d35eb9" width="11%"></img> 

After pass the challenge, we now convert the key to PKCS12 format using:

```
sudo openssl pkcs12 -export -out pool-cert.pfx -inkey /etc/letsencrypt/live/<your domain>/privkey.pem -in /etc/letsencrypt/live/<your domain>/fullchain.pem
```

> Update `<your domain>` to yours

the PKCS12 key is in file `pool-cert.pfx` located at `/home/<username>` ex) `/home/admin`


<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/984d6a68-13b6-4c52-adb5-96ee95f1f86d" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c980c52a-127d-4b78-bb2c-d36b00fc9d26" width="11%"></img> 

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/77dced4a-f177-4fb8-a1c4-07cdb5b03633" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/05d992fe-f4fe-40f0-b9a9-f03cdc995d0b" width="11%"></img> 


#### Certbot Hooks
> Currently we skip this part. Will update this section shortly...


## Web UI
### Static Site
Step1. Install `Ngnix` Web Server
```

```
Step2. Give a read/write `permission` to current user
```

```
Step3. Upload `index.html` file to `/home/<user>/www/`


<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- USAGE EXAMPLES -->
## Usage

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- CONTACT -->
## Contact

Your Name - [@twitter_handle](https://twitter.com/twitter_handle) - email@email_client.com

Project Link: [https://github.com/github_username/repo_name](https://github.com/github_username/repo_name)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* []()
* []()
* []()

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- Label -->
[required-shield]:https://img.shields.io/badge/required-red
[recommended-shield]:https://img.shields.io/badge/recommended-green
[optional-shield]:https://img.shields.io/badge/optional-yellow
[important-shield]:https://img.shields.io/badge/Important-orange

<!-- Social-->
[github-fork-shield]:https://img.shields.io/github/forks/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial?style=social
[github-stars-shield]:https://img.shields.io/github/stars/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial?style=social
[github-followers-shield]:https://img.shields.io/github/followers/PineappleBingoPlayer?style=social
[github-lastcommit-shield]:https://img.shields.io/github/last-commit/pineapplebingoplayer/ocash-mining-pool-setup-tutorial
[twitter-shield]:https://img.shields.io/twitter/follow/PineappleBingo_?label=Follow&style=social

<!-- Built with -->
[lightsail-shield]:https://img.shields.io/badge/AWS-LightSail%20--%20Linux%20O%2FS%20Debian10-yellow
[html-shield]:https://img.shields.io/badge/HTML-orange

[repo-url]:https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial
[github-followers-url]:https://github.com/PineappleBingoPlayer?tab=followers
[github-fork-url]:https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/fork
[twitter-url]:https://twitter.com/PineappleBingo_

[lightsail-url]:https://aws.amazon.com/lightsail
[html-url]:https://www.w3schools.com/html/

[product-screenshot]: images/screenshot.png
