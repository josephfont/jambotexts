<br />
<p align="center">
  <a href="https://github.com/josephfont/jambotext">
    <img src="logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Jambo Texts</h3>

  <p align="center">
    SMS api for reliable phone-verification, sms broadcast and http endpoint-triggered sms services
    <br />
    <a href="https://github.com/josephfont/jambotexts"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <!--a href="https://github.com/github_username/repo">View Demo</a>
    ·
    <a href="https://github.com/github_username/repo/issues">Report Bug</a>
    ·
    <a href="https://github.com/github_username/repo/issues">Request Feature</a-->
  </p>
</p>



<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)
* [pricing](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## About The Project

The Jambo Texts API is an SMS broadcast server that allows companies to be able to 
**send automated sms messages to their users** in order to achieve the following:
`phone number verification`, `http-triggered sms messages`, `sms broadcasts`

<!-- GETTING STARTED -->
## Getting Started

First off, you need to create an account on the [Jambo Texts Website](https://jambotexts.web.app). Here you will be given the required credentials to interract with the API such as your `organisation code` and `password`. You also can get help from our customer-care representatives once you are logged in.

### Phone Number Verification

You can interract with the api through http requests by following the following instructions.

1. Generate an access token by sending a http **post** request to the following url containing your `organisation code` and `password` in your body.
```sh
https://www.jambotexts.com/access_token
```
Depending on the programming language you are using, the body should look relatively similar to the code sample below:
```javascript
{
 "organisationCode": "121212",
 "password":"123456"
}
```
**Please note:** The access token will be valid for only **60 seconds** for you to be able to use it to initialize a command.

2. Initialize a verification request to have a phone number verified by sending a post request to the following url containing the `phone number to be verified` and your `access token`:
```sh
https://www.jambotexts.com/phone_verification
```
Depending on the programming language you are using, the body should look relatively similar to the code sample below:
```javascript
{
 "accessToken": "awtxswer3f4f",
 "recepientNumber":"123456"
}
```
Make sure the phone number is formatted in the above format. Otherwise, the request will not be successful.

3. Grab the verification code labelled `extra`, from the response that you get from step 2 above. The response body will be in the following format below:
```javascript
{
    "responseCode": 200,
    "response": "success",
    "extra": "89QH"
}
```
You should then present your user with an input option to enter the **4 digit** code they will receive on their phone number. Do a string compare to verify that the code they entered was the one you received from the response above. 

<!-- ROADMAP -->
## Issues

See the [open issues](https://github.com/josephfont/jambotexts/issues) for a list of proposed features (and known issues).



## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Jambo Texts - [@huruplay](https://twitter.com/huruplay) - therealfont@gmail.com

Project Link: [https://github.com/josephfont/jambotexts](https://github.com/josephfont/jambotexts)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=flat-square
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=flat-square
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=flat-square
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=flat-square
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=flat-square
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
