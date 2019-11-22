<br />
<p align="center">
  <a href="https://github.com/josephfont/jambotext">
    <img src="logo_lg.png" alt="Logo" width="200" height="200">
  </a>

  <h1 align="center">Jambo Texts</h1>

  <p align="center">
    A simple but powerful SMS service for reliable phone number verification, sms broadcast and automated sms services through http requests
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
  * [Generating Access Tokens](#Generate-Access-Token)
  * [Phone Number Verification](#Phone-Number-Verification)
* [Issues](#Issues)
* [License](#license)
* [Contact](#contact)

<!-- ABOUT THE PROJECT -->
## About The Project

The Jambo Texts API is an SMS broadcast server that allows companies to be able to 
**send automated sms messages to their users** in order to achieve the following:
`phone number verification`, `http-triggered sms messages`, `sms broadcasts`

<!-- GETTING STARTED -->
## Getting Started

First off, you need to create an account on the [Jambo Texts Website](https://jambotexts.web.app). Here you will be given the required credentials to interract with the API such as your `organisation code` and `password`. You also can get help from our customer-care representatives once you are logged in.
### Generating Access Tokens

1. Generate an access token by sending a http **post** request to the following url containing your `organisation code` and `password` in your body.
```sh
https://jambotexts.web.app/access_token
```
Depending on the programming language you are using, the body should look relatively similar to the code sample below:
```javascript
{
 "organisationCode": "121212",
 "password":"123456"
}
```
2. Grab the access token labelled `extra`, from the response that you get from a successful run of the above step. The response body will be in the following format below:
```javascript
{
    "responseCode": 200,
    "response": "success",
    "extra": "awtxswer3f4f"
}
```
**Please note:** The access token will be valid for only **60 seconds** for you to be able to use it to initialize a command.

### Phone Number Verification
1. Generate an access token from following the instructions. The access token is a **12 digit code** used to authorise the process below.

2. Initialize a verification request to have a phone number verified by sending a post request to the following url containing the `phone number to be verified` and your `access token`:
```sh
https://jambotexts.web.app/phone_verification
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
An sms will be sent out to their phone number once the above step completes successfuly. You should then present your user with an input option to enter the **4 digit** code they will receive on their phone number. Do a string compare to verify that the code they entered was the one you received from the response above. 
Congrats, You are done! Enjoy

<!-- ROADMAP -->
## Issues

See the [open issues](https://github.com/josephfont/jambotexts/issues) for a list of proposed features (and known issues).



## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Jambo Texts - therealfont@gmail.com

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
