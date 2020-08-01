---
permalink: /docs/manual-website-interaction/
layout: single
title: "Manual Website Interaction"
excerpt: "How to use HakuNeko."
last_modified_at: 2020-07-30
toc: true
---

Manual website interaction may be useful in the following situations:

-   Check if the website is reachable and working correctly
-   Bypass the CloudFlare mitigation
-   Solve Captcha protection
-   Login personal account

CloudFlare Bypass
-----------------

Usually a manual CloudFlare bypass is not required because HakuNeko does this automatically for the selected website.

1.  Open the [website selection list](#source-selection)
2.  Click on the link in the top right corner of the website that requires manual interaction (e.g. MangaDex)
3.  Now wait until the CloudFlare check is complete and the website has been loaded
4.  You may even navigate to a random manga / chapter to ensure it is working now
5.  Close the window
6.  Downloading from the website shall now work again

![manual cloudflare bypass](/assets/images/documentation//manual-cloudflare-bypass.png)

Captcha Protection
------------------

1.  Open the [website selection list](#source-selection)
2.  Click on the link in the top right corner of the website that requires manual interaction (e.g. 9ANIME)
3.  Now wait until the website has been loaded
4.  Navigate to the manga / chapter that is protected by the Captcha and solve it
5.  Close the window
6.  Downloading from the website shall now work again

![manual captcha protection](/assets/images/documentation//manual-captcha-protection.png)

Account Login
-------------

Some selected websites provide an automatic login function that can be setup in HakuNeko’s settings. For those that don’t, you may try this manual login procedure (it is not guaranty to work).

1.  Open the [website selection list](Quick-Reference#3-source-selection)
2.  Click on the link in the top right corner of the website that requires manual interaction (e.g. Toomics)
3.  Now wait until the website has been loaded
4.  Login with your credentials through the website
5.  Close the window
6.  Downloading from the website may now use your account

![manual account login](/assets/images/documentation//manual-account-login.png)
