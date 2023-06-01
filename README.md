[![github][github-lastcommit-shield]][repo-url]
[![github-followers][github-followers-shield]][repo-url]
[![github-fork][github-fork-shield]][repo-url]
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
    oCash is a crypto currency that empower oLand metaverse by @overlinenetwork.
    <br />
    <a href="https://github.com/github_username/repo_name"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/github_username/repo_name">View Demo</a>
    |
    <a href="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/ssues">Report Bug</a>
    |
    <a href="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/issues">Leave Comments</a>
  </p>
</div>

<a name="readme-top"></a>




## Before We Start

This tutorial is for setting up a `cloud based oCash Mining Pool` over AWS LightSail VPS instance.
If you intend to set the mining pool VPS on your local device, please follow <a href="https://medium.com/@uanid/how-to-install-the-ocash-pool-169dd21c32a2" target="_blank">this</a> tutorial provided by JSY <a href="https://medium.com/@uanid/how-to-install-the-ocash-pool-169dd21c32a2" target="_blank">(@yunjuseong3)</a>
<br/>
> This tutorial will explain steps as simple as possible for those of whom are new to the mining world including myself. Please report any bugs, or comments along with instruction steps. Your valued feedbacks will help #oland Community. 


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
* ...


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

Throughout this tutorial, we are going to set up Linux VPS(Virtual Private Server) on `Amazon LightSail`, and walk through how we make secure connection to the server through `SSH` & transfer files using `SFTP` as well as basic `Linux commands` to be able to setup your oCash Mining Pool successfully. Also, for the demonstration purposes, we will host a `static website` and connect `custom domains`. 

> Feel free to explore other VPS providers, and choose whichever provider is suitable for your budget, UI, or your own preference. There are 100's of providers available. Check <a href="https://www.google.com/search?q=vps+provider+list&sxsrf=APwXEde1H7TPezGQCqAOomKFr6natjwx0w%3A1685476325270&source=hp&ei=5VN2ZM_bDLTg0PEP0tqzmAo&iflsig=AOEireoAAAAAZHZh9b0zuxO7LNaFgpSCOnqRyCT8pGRg&ved=0ahUKEwiP4pDN6J3_AhU0MDQIHVLtDKMQ4dUDCAs&uact=5&oq=vps+provider+list&gs_lcp=Cgdnd3Mtd2l6EAMyBQgAEIAEMgYIABAWEB4yCAgAEIoFEIYDMggIABCKBRCGAzIICAAQigUQhgMyCAgAEIoFEIYDOgQIIxAnOhMILhCKBRCxAxCDARDHARDRAxBDOgcIABCKBRBDOg0ILhCKBRDHARDRAxBDOhEILhCABBCxAxCDARDHARDRAzoUCC4QgAQQsQMQgwEQxwEQ0QMQ1AI6DgguEIMBENQCELEDEIoFOggIABCKBRCRAjoICAAQgAQQsQM6CwguEIAEELEDEIMBOgsILhCDARCxAxCABDoLCAAQgAQQsQMQgwE6CwguEIAEELEDENQCOgUILhCABDoQCC4QigUQsQMQxwEQ0QMQQzoLCAAQigUQsQMQgwE6BwgjEOoCECc6DQguEIoFEMcBEK8BECc6BwgjEIoFECc6CwguEIMBELEDEIoFOgsILhCABBDHARDRAzoKCAAQigUQsQMQQzoNCAAQigUQsQMQgwEQQzoRCC4QgAQQsQMQgwEQxwEQrwE6BAgAEAM6CwguEIoFELEDEIMBOgsILhCABBDHARCvAToICAAQFhAeEA9QAFi3OGDXOWgJcAB4AYABygSIAe8VkgEIMjAuNS41LTGYAQCgAQGwAQo&sclient=gws-wiz" target="_blank">Google's serached "VPS Provider List" results</a>, and many of them provides promotions such as $100-$300 credit, 3 month free trial, etc. I choose AWS LightSail since I'm familiar with other AWS Services, and it has 3 month free tiral promos.  

## Prerequisites

> Feel free to skip over any of following setps if you already completed. 

### GitHub Account ![required-shield]
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
Before we are setting up VPS instance,  Sign up AWS account(`root` user) <a href="" target="_blank">here</a> if you don't have one yet. Then we are going to set up IAM user instead of using `root` account.

1. Login in as `Root User` with your Email address
2. Search IAM in the search bar and click `users' on the left sidebar.
3. Click on `Add Users`, Then Type `User name` and `Password`
4. Select `Add user to group`, then click `Create group`
5. Give a `User group name`, serach & select "AdministratorAccess". Then create user group
6. Review and click `Create user`
7. Return to users list then copy down 12 digits `Account ID`
8. Logout and Login back using `Account ID` `IAM user` `password` that we just created.

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/9dfa7c8c-eac7-4c6c-96b2-f11faa9c1bd5" width="11%"></img> <img 
src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/73449a82-748f-4021-85b3-f0729551aad6" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/cf6c9853-7381-462d-bb1d-6a1ec558ee29" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/7747371b-5f07-484e-8af4-c3018a93e308" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/bc8df107-02de-4dd1-a096-f85cd88fafbf" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/06e2efea-f076-4a88-abf7-e35385ae4378" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/712c7062-5425-4f3c-ab68-d3f03b31262e" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/72080b6e-4b35-4051-99f2-241c121d0306" width="11%"></img> 

### AWS LightSail Set Up ![required-shield]
This step we are going to setup VPS instance. One you login to <a href="" target="_blank">AWS Console </a> you can simply type `LightSail' on the searchbar or Find the link <a href="" target="_blank">here</a>
1. Create Instance
   - Select Instance Location
   - Select a Platform(Linux vs Windows)
   - Select a bluprint

> For this tutorial, we will host a static website for the demonstrate purpose, so we select `Linux OS Debian v10.8` only; However, feel free to choose whichever OS you are confortable with and a blueprints for applications listed below. 

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/f6de655d-d20d-4682-8526-88f38529e37d" width="11%"></img> 

2. Attach Static IP
3. Open Ports

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/329df9da-04f3-4d84-bbf0-ca1ac5c89997" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/f5dec8be-a60e-4d03-9b6f-e428cc180a2e" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/13dd2fec-9ea7-4d68-827f-c77e4d450594" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/994b5601-1b5e-4db4-adba-53365fbb4e2b" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/7fe74ab7-d06e-43d7-80a5-943a0127602b" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/72ac728a-cf5e-4a13-a21f-aa538a140521" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/4bbfa80b-41a8-4558-abe2-ce3839bb18cc" width="11%"></img> 


### Purchase & Connect Domain ![recommended-shield]
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
   - Add custom record, `Host name` as "empty" `Type` as "A" then, `Data` as  `your VPS Public IP address`
   - Add custom record, `Host name` as "WWW" `Type` as "A" then, `Data` as  `your VPS Public IP address`

  > When its succeessfully updated custom record, it will take 1-3 mins to reflect changes.
  
  > FYI, once you type your domain in the web browser, <u>the page won't be displayed since we haven't set up `web server` yet</u>
  
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/5129c17b-285e-44f7-a537-5b49ce91f32f" width="11%"></img> 
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/bdbed861-f7f7-4bbc-a65d-7d7619b168da" width="11%"></img> 


<p align="right">(<a href="#readme-top">back to top</a>)</p>
<br/>

### MobaXterm ![optional-shield]
> This is optional session. Feel free to skip over if you have prefer using `AWS CLI` SCP file transfer and connect to the server through LightSail instance dashboard.
<br/>

#### What is MobaXterm?
MobaXterm is a software toolbox for a secure connection to remote server / remote computing.
- We will be focused on `SSH Connection` and `SFTP`(Secured File Transfer Protocol)
- `SSH Connection` : Make direct connection to remote server using SSH without opening LightSail Dashboard.
- `STFP`: Transfer files between AWS LightSail sever and Windows(MAC)

#### Before We make Connections
1. Download MobaXterm HomEditon v23.1 `Installer Edition` or `Portable Edition` can be found <a href="" targer="_blank">here</a>
2. Open AWS LightSail instance dashboard and download `SSH Key(.pem)`

> Make sure your server opens `port 22` and place `SSH Key` file in a secure place

#### SSH Connection
1. Open MobaXterm & Click `Session`
2. Fill out "Remote host" as your server's `Public IP address`, "Specify username" as your `IAM User`, then Select `Port 22`
3. Click `SSH` then, Select `Advanced SSH settings`
5. Check "Use private key", then select `SSH key(.pem)` file.
6. Click Ok

#### SFTP Connection
1. Open MobaXterm & Click `Session`
2. Fill out "Remote host" as your server's `Public IP address`, "Specify username" as your `IAM User`, then Select `Port 22`
3. Click `SFTP` then, Select `Advanced Sftp settings`
4. Check "Use private key", then select `SSH key(.pem)` file.
6. Click Ok

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Installation
### Utility Packages
### Git
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

### Go Ethereum
### Docker
#### Step1
Remove old version of `docker`, `docker.io`, and `docker-engine` that may already installed previously.
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
#### Step2
Install Docker using the Repository on Debian10
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
Verify the installation by checking version of the Docker
```
docker -v
```
or with a Hello World Image
```
docker run hello-world
```

> If system arises `Permission denied` error during the steps, run the following command then continue the rest of the steps.

```
sudo usermod -a -G docker $USER
```


## TLS Configurations
### Testing
### Production

Install CertBot
```
sudo apt-get install certbot
```
Generate Key
```
sudo certbot certonly --manual --preferred-challenges dns --email <your email> --domains <your domain>
```
> ex) sudo certbot certonly --manual --preferred-challenges dns --email pineapple@gmail.com --domains ocash.network

Follow instruction to add DNS TEXT Record to your domain prodivder, (Googld Domains in our case) with given `Host Name` as `_acme-challenge.<YOUR_DOMAIN>` and data as given string. Then press `Enter` to continue.

> Note that we need to select type as `TXT`, and add `_amc-challenge` on `Host Name`. Google Domains will automatically append .<YOUR_DOMAIN> in the end. ex) `_acme-challenge.ocash.network` 
> If validation keep failed, you need to double check DNS Record. Everytime re-run the command, it will generate new testing key so that you need to update DNS Record.

convert the key to PKCS12 format using
```
sudo openssl pkcs12 -export -out pool-cert.pfx -inkey /etc/letsencrypt/live/<your domain>/privkey.pem -in /etc/letsencrypt/live/<your domain>/fullchain.pem
```
the PKCS12 key is in file `pool-cert.pfx` located at `/home/<username>`

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/984d6a68-13b6-4c52-adb5-96ee95f1f86d" width="11%"></img>
<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c980c52a-127d-4b78-bb2c-d36b00fc9d26" width="11%"></img> 

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/77dced4a-f177-4fb8-a1c4-07cdb5b03633" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c2b3f086-c24a-4f47-be9b-4893250dbab1" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/05d992fe-f4fe-40f0-b9a9-f03cdc995d0b" width="11%"></img> 

<img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/d9c5fec2-8ed7-401c-acf8-578663d35eb9" width="11%"></img> <img src="https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial/assets/134893455/c278b688-f2a1-4db6-9d91-3544ad7acd1d" width="11%"></img> 


#### Certbot Hooks


## Run oCash Mining Pool

## Web UI
### Static Site


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

[required-shield]:https://img.shields.io/badge/required-red
[recommended-shield]:https://img.shields.io/badge/recommended-green
[optional-shield]:https://img.shields.io/badge/optional-yellow

[github-fork-shield]:https://img.shields.io/github/forks/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial?style=social
[github-stars-shield]:https://img.shields.io/github/stars/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial?style=social
[github-followers-shield]:https://img.shields.io/github/followers/PineappleBingoPlayer?style=social
[github-lastcommit-shield]:https://img.shields.io/github/last-commit/pineapplebingoplayer/ocash-mining-pool-setup-tutorial
[twitter-shield]:https://img.shields.io/twitter/follow/PineappleBingo_?label=Follow&style=social
[lightsail-shield]:https://img.shields.io/badge/AWS-LightSail%20--%20Linux%20O%2FS%20Debian10-yellow

[repo-url]:https://github.com/PineappleBingoPlayer/ocash-mining-pool-setup-tutorial
[twitter-url]:https://twitter.com/PineappleBingo_
[lightsail-url]:https://aws.amazon.com/lightsail

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/github_username/repo_name.svg?style=for-the-badge
[contributors-url]: https://github.com/github_username/repo_name/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/github_username/repo_name.svg?style=for-the-badge
[forks-url]: https://github.com/github_username/repo_name/network/members
[stars-shield]: https://img.shields.io/github/stars/github_username/repo_name.svg?style=for-the-badge
[stars-url]: https://github.com/github_username/repo_name/stargazers
[issues-shield]: https://img.shields.io/github/issues/github_username/repo_name.svg?style=for-the-badge
[issues-url]: https://github.com/github_username/repo_name/issues
[license-shield]: https://img.shields.io/github/license/github_username/repo_name.svg?style=for-the-badge
[license-url]: https://github.com/github_username/repo_name/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/linkedin_username
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
