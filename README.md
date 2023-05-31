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

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* [![lightsail][lightsail-shield]][lightsail-url]
* ...


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

Through this tutorial, we are going to set up VPS(Virtual Private Server) on Amazon LightSaild - Linux Debian ver.10.8, and how to make secure connection to the server through SSH & transfer files as well as basic Linux commands to be able to setup your oCash Mining Pool successfully.
<br/>
> Feel free to explore other VPS providers, and choose whichever provider is suitable for your budget, UI, or your own preference. There are 100's of providers available. Check <a href="https://www.google.com/search?q=vps+provider+list&sxsrf=APwXEde1H7TPezGQCqAOomKFr6natjwx0w%3A1685476325270&source=hp&ei=5VN2ZM_bDLTg0PEP0tqzmAo&iflsig=AOEireoAAAAAZHZh9b0zuxO7LNaFgpSCOnqRyCT8pGRg&ved=0ahUKEwiP4pDN6J3_AhU0MDQIHVLtDKMQ4dUDCAs&uact=5&oq=vps+provider+list&gs_lcp=Cgdnd3Mtd2l6EAMyBQgAEIAEMgYIABAWEB4yCAgAEIoFEIYDMggIABCKBRCGAzIICAAQigUQhgMyCAgAEIoFEIYDOgQIIxAnOhMILhCKBRCxAxCDARDHARDRAxBDOgcIABCKBRBDOg0ILhCKBRDHARDRAxBDOhEILhCABBCxAxCDARDHARDRAzoUCC4QgAQQsQMQgwEQxwEQ0QMQ1AI6DgguEIMBENQCELEDEIoFOggIABCKBRCRAjoICAAQgAQQsQM6CwguEIAEELEDEIMBOgsILhCDARCxAxCABDoLCAAQgAQQsQMQgwE6CwguEIAEELEDENQCOgUILhCABDoQCC4QigUQsQMQxwEQ0QMQQzoLCAAQigUQsQMQgwE6BwgjEOoCECc6DQguEIoFEMcBEK8BECc6BwgjEIoFECc6CwguEIMBELEDEIoFOgsILhCABBDHARDRAzoKCAAQigUQsQMQQzoNCAAQigUQsQMQgwEQQzoRCC4QgAQQsQMQgwEQxwEQrwE6BAgAEAM6CwguEIoFELEDEIMBOgsILhCABBDHARCvAToICAAQFhAeEA9QAFi3OGDXOWgJcAB4AYABygSIAe8VkgEIMjAuNS41LTGYAQCgAQGwAQo&sclient=gws-wiz" target="_blank">Google's serached "VPS Provider List" results</a>, and many of them provides promotions such as $100-$300 credit, 3 month free trial, etc. I choose AWS LightSail since I'm familiar with other AWS Services, and it has 3 month free tiral promos.  

## Prerequisites

> Feel free to skip over any of following setps if you already completed. 

### GitHub Account ![required-shield]
In order to clone the git repository, we need a GitHub ID & Password. If you don't have one yet, please sign up <a href="https://github.com/" target="_blank">here</a>.
<br/>
### AWS IAM Set up ![recommended-shield]
Before we are setting up VPS instance, Please create AWS account(`root` user) Sign up AWS account <a href="" target="_blank">here</a> if you don't have one. Then we are going to set up IAM user instead of using `root` account.
1. Login in as `Root User` with your Email address
2. Search IAM in the search bar and click `users' on the left sidebar.
3. Follow steps to create `IAM user` and Logout and Login back using `IAM user` that we just created.

### AWS LightSail Set Up ![required-shield]
This step we are going to setup VPS instance. One you login to <a href="" target="_blank">AWS Console </a> you can simply type `LightSail' on the searchbar or Find link <a href="" target="_blank">here</a>
1. Create Instance
* Select Instance Location
* Select a Platform(Linux vs Windows)
* Select a bluprint
> For this tutorial, we will host a static website for the demonstrate purpose, so we select `Linux OS Debian v10.8` only; However, feel free to choose whichever OS you are confortable with and a blueprints for applications listed below. 
2. Attach Static IP
3. Open Ports

### Purchase & Connect Domain ![recommended-shield]
In order to provide easy accesss for miners to your mining pool, purchasing your own domain is recomened.
1. Purchase your domain name
> There are many domain registration service providers. Pick any of providers here and create your own unique, eye-catching, and easy-to-remmeber domain name. ex)<a href="https://ocash.network" target="_blank">`ocash.network`</a>
> For this tutorial, we use <a href="https://domains.google/" target="_blank">Google Domains</a>
* Login your Google account
* Search domain name that you wish for
* Select alternates if it's already exit
* Make purchase

3. Connect to your LightSail Instance
* open `oCach-pool-debian` instance
* ...
### MobaXterm ![optional-shield]
> This is optional session. Feel free to skip over if you have prefer using `AWS CLI` SCP file transfer and connect to the server through LightSail instance dashboard.

#### What is MobaXterm?
MobaXterm is a software toolbox for a secure connection to remote server / remote computing.<br/>
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


## Installation
### Utility Packages
### Git
### Go Ethereum
### Docker

## TLS Configurations
### Testing
### Production

## Run oCash Mining Pool

## Web UI
### Static Site




This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/github_username/repo_name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3
    - [ ] Nested Feature

See the [open issues](https://github.com/github_username/repo_name/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

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
